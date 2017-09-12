<h1 id="introduction">Introduction</h1>

<p>FileSender 1.x is designed to send mails <b>on behalf of</b> an authenticated user but will by definition send those mails from a server outside the administrative domain of those authenticated users. This will introduce problems with receving sites using very strict anti-spam measures (i.e. strict SPF checking). One possible solution (independent of FileSender) is described in <a class="wiki_link" href="/wiki/show/file_sender/Configuring_SRS_with_Exim_(Debian_and_Ubuntu)" title="Configuring SRS with Exim (Debian and Ubuntu)">Configuring SRS with Exim (Debian and Ubuntu)</a>.</p>

<p>Another solution is currently (as of Feb 2011) available as experimental feature based on patches from David Jericho (AARNet) and described in this document.</p>

<h1 id="requirements">Requirements</h1>

<ul>
	<li>The MTA running on the same server as FileSender is configured to accept and handle <b>incoming</b> mail (either directly or through external spamfiltering solutions)</li>
	<li>A dedicated local address is used as envelope sender (return-path) and mail destined for that address is locally delivered to the &#39;webserver user&#39; (www-data on Debian, apache on RedHat?)</li>
	<li>Local delivery is done in such a way that each incoming message for the &#39;return-path&#39; user is stored as a separate file in a dedicated directory</li>
</ul>

<h1 id="installation">Installation</h1>

<p>The Mail Bounce Handling feature is available as experimental feature in FileSender 1.0.1 and later but needs to be manually activated.</p>

<p>The mail bounce functionality requires new settings and templates in config/config.php, be sure to merge those with your existing config.php. For the stable 1.1.x/1.5 release versions the required settings can be found in and merged from the<span style="font-family: courier new,courier;"> config[-templates]/config.experimental-bounce-handling </span>file.</p>

<p>When installing from the source tarball you&#39;ll need to do the following after unpacking:</p>

<pre style="">
cd <i>&lt;filesender-base&gt;</i>

mkdir -p maildrop/new
mkdir -p maildrop/done
mkdir -p maildrop/failures

chown -R www-data:www-data maildrop
chmod -R 750 maildrop</pre>

<h1 id="configuration">Configuration</h1>

<p>To enable the &#39;Mail Bounce&#39; functionality a few manual steps are needed. Most steps are dependent on your MTA and your choice of local MDA (Mail Delivery Agent). The steps below should give you a general idea of what is needed.</p>

<h3 id="312e20646566696e6520746865202772657475726e2d7061746827206164647265737320746f207573653a">1. Define the &#39;return-path&#39; address to use:</h3>

<p>In this document we&#39;ll use <span style="font-family: courier new,courier;">filesender-bounces@example.org</span></p>

<h3 id="2._add_an_alias">2. Add an alias</h3>

<pre style="">
vi /etc/aliases
filesender-bounces:    www-data</pre>

<h3 id="3._create_a_.forward_for_the_www-data_user">3. Create a .forward for the www-data user</h3>

<pre style="">
vi ~www-data/.forward</pre>

<pre style="">
|/usr/share/filesender/scripts/bounce.sh</pre>

<pre style="">
chown www-data ~www-data/.forward</pre>

<h3 id="342e2063726561746520612067656e65726963202764656c69766572792720736372697074">4. Create a generic &#39;delivery&#39; script</h3>

<pre style="">
cd &lt;filesender-base&gt;/scripts
vi bounce.sh</pre>

<pre style="">
#!/bin/sh
timestamp=$(date &quot;+%Y-%m-%d_%H:%M:%S&quot;)
cat &gt; $(mktemp -p /usr/share/filesender/maildrop/new/ bounce.${timestamp}.XXXXXX)</pre>

<pre style="">
chmod +x bounce.sh</pre>

<h3 id="3c623e352e20656e61626c652074686520757365206f662061206465646963617465642072657475726e2d70617468206164647265737320696e2066696c6573656e6465723c2f623e"><b>5. Enable the use of a dedicated return-path address in FileSender</b></h3>

<p>In config/config.php:</p>

<pre style="">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; // email bounce handling
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;return_path&#39;] = &quot;<b>filesender-bounces@example.org</b>&quot;;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;emailbounce_location&#39;] = &#39;/usr/share/filesender/maildrop/new&#39;;</pre>

<h3 id="6._add_a_cronjob_to_process_incoming_mails">6. Add a cronjob to process incoming mails</h3>

<pre style="">
vi /etc/cron.d/filesender</pre>

<pre style="">
# Look for incoming bounces every 5 minutes
*/5 *&nbsp;&nbsp;&nbsp;&nbsp; * * *&nbsp;&nbsp;&nbsp;&nbsp; www-data php /usr/share/filesender/cron/emailbouncehandler.php</pre>

<h1 id="686f7720646f657320697420776f726b3f">How does it work?</h1>

<p>All outgoing mails have an additional &#39;X-FileSenderUID&#39; header added with the UID of the uploaded file or voucher. In case the message cannot be delivered it will be returned to the address specified as &#39;return-path&#39;. The incoming bounces will be processed by the &#39;emailbouncehandler.php&#39; script. This script looks for the X-FileSenderUID header and if found will figure out to and from which addresses the original message was sent. It will then send a generic &#39;Failure notice&#39; to the original sender.</p>

<p>Processed bounces are moved to the &#39;&lt;filesender-base&gt;/maildrop/done&#39; directory (so when people ask about details of the failure you can look them up there). Incoming messages without a X-FileSenderUID header are moved to the &lt;filesender-base&gt;/maildrop/failures directory for manual inspection.</p>

<p>Currently no provisons are made to alert the administrator of failures and there is also no automatic cleanup of processed bounces.</p>

<h1 id="open_issues">Open issues</h1>

<ul>
	<li>No distinction is made between &#39;temporary&#39; and &#39;permanent&#39; failures. Should this be needed? (Needs more field testing probably)</li>
	<li>No distinction is made between &#39;files&#39; and &#39;vouchers&#39; (currently the template text takes care of that)</li>
	<li>A bounce triggered by a file download is processed in the same way as for a file upload: the failure notice is sent to the original uploader, not to the downloader.</li>
</ul>

<h1 id="developer_notes">Developer notes</h1>

<p>The relevant files are:</p>

<ul>
	<li>classes/Mail.php : modified sendemail() function. New parameter &#39;type&#39; added, is used for sending bounces (type &#39;bounce&#39;). This parameter could be used to add functionality to distinguish between uploads and downloads and more.</li>
	<li>cron/emailbouncehandler.php: the actual bouncehandler called by cron</li>
	<li>config/config.php : new config settings (see above) and template/bounce subject</li>
</ul>

