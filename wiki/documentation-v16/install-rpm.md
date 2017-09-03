
<h2 id="3c7370616e207374796c653d22636f6c6f723a20236666303030303b223e3c7370616e207374796c653d22636f6c6f723a20233030303030303b223e696e7374616c6c6174696f6e3c2f7370616e3e3c2f7370616e3e"><span style="color: #ff0000;"><span style="color: #000000;">Installation</span></span></h2>

<p>To install the filesender RPM&#39;s on RedHat based Linux systems add the relevant filesender yum repository to your system. FileSender uses the Debian terminology for its distribution channels. Use the <a class="wiki_link" href="https://www.assembla.com/wiki/show/file_sender/Release_status_and_life_cycle" title="Release_status_and_life_cycle"> release status overview</a> to select the FileSender release you want to install. In the following replace &#39;stable&#39; with &#39;testing&#39; if you want to track upcoming stable releases or &#39;unstable&#39; if you want to track the development builds. Use &#39;oldstable&#39; for the previous (old) release.</p>

<pre>
$ cd /etc/yum.repos.d/
$ sudo wget http://repository.filesender.org/rpm/filesender-stable.repo
$ sudo yum install filesender</pre>

<p>This will install filesender, simplesamlphp and postgresql-server and their dependencies but might require manual installation of your favourite MTA (sendmail, postfix or exim will do).</p>

<h2 id="configuration">Configuration</h2>

<p>The RPM installation will take care of most steps mentioned in <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source" title="Installation - Linux Source">Installation - Linux Source</a>. The following manual steps are still needed:</p>

<ul>
	<li>The configuration part of <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source#step_4_-_install_and_configure_postgresql" title="Installation - Linux Source#Step 4 - Install and configure PostgreSQL">Install and configure PostgreSQL</a> by editing <span style="font-family: courier new,courier;">/var/lib/pgsql/data/pg_hba.conf </span> (may need an initial<span style="font-family: courier new,courier;"> service postgresql initdb</span>).</li>
</ul>

<ul>
	<li><a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source#step_7_-_create_the_filesender_user_and_database" title="Installation_-_Linux_Source#Step 7 - Create the FileSender user and database">Create the FileSender user and database</a> You&#39;ll first need to start the postgresql service (<span style="font-family: courier new,courier;">service postgresql start</span>)</li>
	<li><a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source#step_10_-_configure_your_filesender_installation" title="Installation_-_Linux_Source#Step 10 - Configure your FileSender installation">Configure your FileSender installation</a></li>
	<li><a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source#step_2_-_configure_apache2_with_ssl" title="Installation_-_Linux_Source#Step 2 - Configure Apache2 with SSL">Configure Apache2 with SSL</a></li>
</ul>

<p>Note that the config directory is in<span style="font-family: courier new,courier;"> /etc/filesender/ </span>and the software is installed in <span style="font-family: courier new,courier;">/usr/share/filesender</span>/ (with symlinks to <span style="font-family: courier new,courier;">/var/lib/filesender</span>/ )</p>

<p>The package also installs a daily cronjob in <span style="font-family: courier new,courier;">/etc/cron.daily/filesender</span> and some recommended PHP settings in <span style="font-family: courier new,courier;">/etc/php.d/filesender.ini</span></p>

<h2 id="starting_the_service">Starting the service</h2>

<p>After installing and configuring you&#39;ll most likely will need to start the relevant services:</p>

<pre>
service postfix start
service postgresql start
service httpd start</pre>

<p>If all is well you can add these services to the relevant run levels with <span style="font-family: courier new,courier;">chkconfig</span></p>

<h2 id="known_issues">Known issues</h2>

<ul>
	<li>At the moment the RPM&#39;s are not relocatable.</li>
	<li>On RedHat and Centos5 the default PHP version is 5.1 which is too low. Recent RedHat/Centos5 distros do provide separate php53 packages but these conflict with the &#39;default&#39; php dependencies. Current advise is to replace 5.1 with PHP 5.3 or later from your favourite additional repository (IUS has php53u which works nicely with the filesender and simplesamlphp packages). Additional info on <a href="https://www.centos.org/modules/newbb/viewtopic.php?viewmode=flat&amp;topic_id=30881&amp;forum=38">https://www.centos.org/modules/newbb/viewtopic.php?viewmode=flat&amp;topic_id=30881&amp;forum=38</a></li>
	<li>RHEL and CentOS 6/7 have a recent enough version of PHP in the standard repositories, however the php-mcrypt package is missing (needed for SImpleSAMLphp). To get that package you&#39;ll need to add the EPEL repository (see: <a href="http://fedoraproject.org/wiki/EPEL">http://fedoraproject.org/wiki/EPEL </a>).</li>
	<li>If you get database connection errors (Permission denied) SELinux might be set to prevent the webserver user from making network connections. Check with <span style="font-family: courier new,courier;">getsebool httpd_can_network_connect</span>and allow it (when disabled) with <span style="font-family: courier new,courier;">setsebool -P httpd_can_network_connect 1</span></li>
	<li>If you get errors (Permission denied) in your mail logs when FileSender tries to send mail SELinux might be set to prevent the webserver user from sending mail. Check with <span style="font-family: courier new,courier;">getsebool httpd_can_sendmail</span> and allow it (when disabled) with&nbsp; <span style="font-family: courier new,courier;">setsebool -P httpd_can_sendmail 1</span></li>
	<li>When updating with <span style="font-family: courier new,courier;">yum update</span> from a previous <b>0.1.x beta</b> package the update process will fail. Just do a <span style="font-family: courier new,courier;">yum erase filesender; yum install filesender</span> instead.<span style="font-family: courier new,courier;"> </span></li>
</ul>

<h2 id="support_and_feedback">Support and Feedback</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Support_and_Mailinglists" title="Support and Mailinglists">Support and Mailinglists</a> and <a class="wiki_link" href="/wiki/show/file_sender/Feature_requests" title="Feature requests">Feature requests</a>.</p>

