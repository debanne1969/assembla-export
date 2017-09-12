<h1 id="introduction">Introduction</h1>

<p>filesender is designed to send mails <strong>on behalf of</strong> an authenticated user but will by definition send those mails from a server outside the administrative domain of those authenticated users. This will introduce problems with receving sites using very strict anti-spam measures (i.e. strict SPF checking). This document describes one possible solution that can be implemented independent of filesender and is based on having the MTA using the Sender Rewrite Scheme as described on <a href="http://www.libsrs2.org/" target="_blank">http://www.libsrs2.org/</a></p>

<h1 id="requirements">Requirements</h1>

<ul>
	<li>Debian (Lenny) or Ubuntu server</li>
	<li>exim4 installed as MTA (default on Lenny)</li>
	<li>server (MTA) is configured to accept and handle <strong>incoming</strong> mail (either directly or through external spamfiltering solutions)</li>
</ul>

<h1 id="installation">Installation</h1>

<p>All steps need to be done as root.</p>

<h2 id="install_and_configure_srs">Install and configure SRS</h2>

<p>Install the required srs package:</p>

<pre>
apt-get install srs</pre>

<p>Create a startup script for the srsd daemon:</p>

<pre>
vi /etc/init.d/srsd</pre>

<p>with the following content:</p>

<pre>
#! /bin/sh

### BEGIN INIT INFO
# Provides:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; srsd
# Required-Start:&nbsp;&nbsp; &nbsp;
# Required-Stop:&nbsp;&nbsp;&nbsp; &nbsp;
# Should-Start:&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;
# Default-Start:&nbsp;&nbsp;&nbsp;&nbsp; 2 3 4 5
# Default-Stop:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 0 1 6
# Short-Description: SRS daemon
# Description:&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; SRS daemon
### END INIT INFO

set -e

# /etc/init.d/srsd: start and stop the srsd daemon

DAEMON=/usr/bin/srsd
USER=Debian-exim
SECRETFILE=/etc/srsd.secret
PIDFILE=/var/run/srsd.pid
SOCKETFILE=/tmp/srsd
SRSD_OPTS=&quot;--secretfile ${SECRETFILE}&quot;

test -x $DAEMON || exit 0

. /lib/lsb/init-functions

srsd_start() {
&nbsp;&nbsp;&nbsp; if start-stop-daemon --start --quiet --background \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; --chuid $USER \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; --pidfile $PIDFILE --make-pidfile \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; --exec $DAEMON \
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; -- $SRSD_OPTS
&nbsp;&nbsp;&nbsp; then
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; rc=0
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sleep 1
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; if ! kill -0 $(cat $PIDFILE) &gt;/dev/null 2&gt;&amp;1; then
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; log_failure_msg &quot;srsd daemon failed to start&quot;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; rc=1
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; fi
&nbsp;&nbsp;&nbsp; else
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; rc=1
&nbsp;&nbsp;&nbsp; fi
&nbsp;&nbsp;&nbsp; if [ $rc -eq 0 ]; then
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; log_end_msg 0
&nbsp;&nbsp;&nbsp; else
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; log_end_msg 1
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; rm -f $PIDFILE
&nbsp;&nbsp;&nbsp; fi
} # srsd_start


case &quot;$1&quot; in
&nbsp; start)
&nbsp;&nbsp; &nbsp;log_daemon_msg &quot;Starting srsd daemon&quot; &quot;srsd&quot;
&nbsp;&nbsp; &nbsp;if [ -s $PIDFILE ] &amp;&amp; kill -0 $(cat $PIDFILE) &gt;/dev/null 2&gt;&amp;1; then
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;log_progress_msg &quot;apparently already running&quot;
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;log_end_msg 0
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;exit 0
&nbsp;&nbsp; &nbsp;fi
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; srsd_start
&nbsp;&nbsp; &nbsp;;;
&nbsp; stop)
&nbsp;&nbsp; &nbsp;log_daemon_msg &quot;Stopping srsd daemon&quot; &quot;srsd&quot;
&nbsp;&nbsp; &nbsp;start-stop-daemon --stop --quiet --oknodo --pidfile $PIDFILE
&nbsp;&nbsp; &nbsp;log_end_msg $?
&nbsp;&nbsp; &nbsp;rm -f $PIDFILE
&nbsp;&nbsp; &nbsp;rm -f $SOCKETFILE
&nbsp;&nbsp; &nbsp;;;

&nbsp; restart)
&nbsp;&nbsp; &nbsp;set +e
&nbsp;&nbsp; &nbsp;log_daemon_msg &quot;Restarting srsd daemon&quot; &quot;srsd&quot;
&nbsp;&nbsp; &nbsp;if [ -s $PIDFILE ] &amp;&amp; kill -0 $(cat $PIDFILE) &gt;/dev/null 2&gt;&amp;1; then
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;start-stop-daemon --stop --quiet --oknodo --pidfile $PIDFILE || true
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;sleep 1
&nbsp;&nbsp; &nbsp;else
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;log_warning_msg &quot;srsd daemon not running, attempting to start.&quot;
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;rm -f $PIDFILE
&nbsp;&nbsp; &nbsp;fi
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; srsd_start
&nbsp;&nbsp; &nbsp;;;

&nbsp; status)
&nbsp;&nbsp; &nbsp;status_of_proc -p $PIDFILE &quot;$DAEMON&quot; srsd
&nbsp;&nbsp; &nbsp;exit $?&nbsp;&nbsp; &nbsp;# notreached due to set -e
&nbsp;&nbsp; &nbsp;;;
&nbsp; *)
&nbsp;&nbsp; &nbsp;echo &quot;Usage: /etc/init.d/srsd {start|stop|restart|status}&quot;
&nbsp;&nbsp; &nbsp;exit 1
esac

exit 0</pre>

<p>Configure the startup runlevels (default startup at boot time):</p>

<pre>
chmod 755 /etc/init.d/srsd
update-rc.d srsd defaults</pre>

<p>Create a &#39;secrets&#39; file with a random generated secret to use with srsd:</p>

<pre>
touch /etc/srsd.secret
chown Debian-exim /etc/srsd.secret
chmod 600 /etc/srsd.secret
openssl rand -base64 12 &gt; /etc/srsd.secret</pre>

<p>Start the SRS daemon:</p>

<pre>
invoke-rc.d srsd start</pre>

<h2 id="configure_exim4">Configure exim4</h2>

<p>There are various ways exim4 on Debian can be configured. The description below is based on the so called &#39;split configuration&#39; method but can be easily adapted to other methods. Please have a look at section 2.1 of the README.Debian:</p>

<pre>
zmore /usr/share/doc/exim4/README.Debian.gz</pre>

<p>The actual method of configuration and some of the settings below are usually set when installing exim4. They can be set/changed with:</p>

<pre>
dpkg-reconfigure exim4-config</pre>

<p>Step 0: make sure exim is configured to accept incoming mail. Within the debconf scheme this should be one of the following modes:</p>

<pre>
2.1.1.1.1.&nbsp; internet site; mail is sent and received directly using SMTP
2.1.1.1.2.&nbsp; mail sent by smarthost; received via SMTP or fetchmail</pre>

<p>Step 1: add additional routers, these should be <strong>before</strong> the dnslookup router:</p>

<pre>
vi /etc/exim4/conf.d/router/175_exim4-config_srs</pre>

<p>with the following content:</p>

<pre>
srs_bounce:
&nbsp; debug_print = &quot;R: srs_bounce for $local_part@$domain&quot;
&nbsp; driver = redirect
&nbsp; allow_fail
&nbsp; allow_defer
&nbsp; domains = $primary_hostname
&nbsp; local_part_prefix = srs0+ : srs0- : srs0= : srs1+ : srs1- : srs1=
&nbsp; caseful_local_part
&nbsp; address_data = ${readsocket{/tmp/srsd}{REVERSE $local_part_prefix$local_part@$domain}{5s}{\n}{:defer: SRS daemon failure}}
&nbsp; data = ${if match{$address_data}{^ERROR}{:fail: Invalid SRS address}{$address_data}}


srs_forward:
&nbsp; debug_print = &quot;R: srs_forward for $local_part@$domain&quot;
&nbsp; no_verify
&nbsp; senders = ! : ! *@+local_domains
&nbsp; address_data = ${readsocket{/tmp/srsd}\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; {FORWARD $sender_address_local_part@$sender_address_domain $primary_hostname\n}\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; {5s}{\n}{:defer: SRS daemon failure}}
&nbsp; errors_to = ${quote_local_part:${local_part:$address_data}}@${domain:$address_data}
&nbsp; headers_add = &quot;X-SRS: Sender address rewritten from &lt;$sender_address&gt; to &lt;${quote_local_part:${local_part:$address_data}}@${domain:$address_data}&gt; by $primary_hostname.&quot;
&nbsp; driver = redirect
&nbsp; repeat_use = false
&nbsp; allow_defer
&nbsp; data = ${quote_local_part:$local_part}@$domain</pre>

<p>Step 2: add some small modifications to the macro-definitions used:</p>

<pre>
vi /etc/exim4/conf.d/main/000_localmacros</pre>

<p>with the following content:</p>

<pre>
CHECK_RCPT_LOCAL_LOCALPARTS = ^[.] : ^.*[@%!|`#&amp;?]
MAIN_LOG_SELECTOR = +tls_peerdn +address_rewrite +return_path_on_delivery +sender_on_delivery +smtp_confirmation +smtp_connection +smtp_incomplete_transaction +smtp_no_mail</pre>

<p>The above macros ensure that the &#39;/&#39; character (might be used with generated SRS addresses) is allowed and will take care of the logging of all rewrites (and some more).</p>

<p>Step 3: restart exim. If exim is configured to use the split configuration this will automatically generate a new configuration. If you are using one of the other configuration methods please have a look at</p>

<pre>
man update-exim4.conf.template</pre>

<p>on how to generate a single exim4 configuration template from the above &#39;split configuration files&#39;.</p>

<pre>
invoke-rc.d exim4 restart</pre>

<p>You&#39;re done...</p>

<h1 id="686f7720646f657320697420776f726b3f">How does it work?</h1>

<p>Afer installing and configuring the above all incoming and outgoing mail will be checked whether the <strong>envelope</strong> sender and recipient addresses should be rewritten or not. For outgoing mails the sender address is rewritten only when the original sender is outside the local domain(s) of the server. For incoming mails the recipient address will be checked whether it is a valid SRS address (i.e. it was generated on the server based on the secret hash) and is not expired yet (default expiry is 49 days).</p>

<p>exim hands over addresses to be rewitten or validated to the srsd-daemon through a socket in /tmp/srsd. The srsd daemon then does the rewriting or validation.</p>

<p>The generated rewritten address is based on the original addres, the day the address is generated and the first secret in the /etc/srsd.secret file. Validation is done using all secrets in the secrets file (one per line) and is checked for expiry.</p>

<p>The expiry time (in days) is &#39;hard coded&#39; in the Mail::SRS Perl module (/usr/share/perl5/Mail/SRS.pm). If you need to change the default you have to edit the SRS.pm file, for example (making the expiry 14 days):</p>

<pre>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; use Mail::SRS;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; my $srs = new Mail::SRS(
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Secret&nbsp;&nbsp;&nbsp;&nbsp; =&gt; [ .... ],&nbsp;&nbsp;&nbsp; # scalar or array
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; MaxAge&nbsp;&nbsp;&nbsp;&nbsp; =&gt; <span style="color: #ff0000;">14</span>,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; # days
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; HashLength =&gt; 4,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; # base64 characters: 4 x 6bits
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; HashMin&nbsp;&nbsp;&nbsp; =&gt; 4,&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; # base64 characters
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; );
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; my $srsaddress = $srs-&gt;forward($sender, $alias);
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; my $sender = $srs-&gt;reverse($srsaddress);

</pre>

<p>SRS uses a stateless mechanism to generate and validate SRS-addresses so there is no need for storing/saving the addresses.</p>

<h1 id="known_problems">Known problems</h1>

<ul>
	<li>NDR&#39;s (bounces) from remote MTA&#39;s are sent to the rewritten address (also in the RFC2822 To: field). This will work and the NDR will be sent to the original sender but this might confuse both users and draconian spamfilters. Needs investigation.</li>
</ul>

<h1 id="security_considerations">Security considerations</h1>

<ul>
	<li>The srsd daemon runs with the priviliges of the Debian-exim user and should only get properly sanitised addresses from Exim to rewrite/validate.</li>
	<li>the requirement to accept and handle incoming mail opens up an extra port exposed to the outside world. You can minimise the additional risks by putting the MTA on your FileSender box behind a dedicated mail handling server, i.e. both incoming and outgoing mail are sent through another (dedicated) mail server. Access to the SMTP port on your FileSender server can then be restricted to accept only connections from the dedicated mail server.</li>
	<li>As always, keep your server up to date with the latest security patches, as with all software there is a chance of exploitable bugs but the Debian and Exim community have a good track record with implementing security fixes.</li>
</ul>

<h1 id="acknowledgements">Acknowledgements</h1>

<ul>
	<li>Paul Dekkers @ SURFnet for creating a working exim4 config with stock Debian packages based on the not always working information floating around on the Internet.</li>
	<li>Peter Thomassen for improvements and bug fixes.</li>
</ul>

