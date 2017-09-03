
<p>&nbsp;</p>

<ul>
	<li><a class="wiki_link" href="#client_and_server_requirements" title="Client and Server Requirements">Client and Server Requirements</a></li>
	<li><a class="wiki_link" href="#install_apache2" title="Install Apache2">Install Apache2</a></li>
	<li><a class="wiki_link" href="#configure_apache2_with_ssl" title="Configure Apache2 with SSL">Configure Apache2 with SSL</a></li>
	<li><a class="wiki_link" href="#install_and_configure_php5" title="Install and configure PHP5">Install and configure PHP5</a></li>
	<li><a class="wiki_link" href="#install_and_configure_postgresql" title="Install and configure PostgreSQL">Install and configure PostgreSQL</a></li>
	<li><a class="wiki_link" href="#install_simplesamlphp" title="Install SimpleSAMLphp">Install SimpleSAMLphp</a></li>
	<li><a class="wiki_link" href="#install_the_filesender_package" title="Install the FileSender package">Install the FileSender package</a></li>
	<li><a class="wiki_link" href="#create_the_filesender_user_and_database" title="Create the FileSender user and database">Create the FileSender user and database</a></li>
	<li><a class="wiki_link" href="#configure_your_filesender_installation" title="Configure your FileSender installation">Configure your FileSender installation</a></li>
	<li><a class="wiki_link" href="#configure_cron" title="Configure Cron">Configure Cron</a></li>
	<li><a class="wiki_link" href="#start_using_filesender" title="Start using FileSender">Start using FileSender</a></li>
	<li><a class="wiki_link" href="#support_and_feedback" title="Support and Feedback">Support and Feedback</a></li>
</ul>

<p>&nbsp;</p>

<p>This is the installation documentation for installing <b>FileSender 1.1(.x)</b> on Linux. This guide is written for installation from source on the Debian Linux platform but any Linux variant should work with some modifications (most notably about installing the required additional software packages).</p>

<p><i>Debian and RPM packages are also available to automate most of the steps below. Please see <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Debian_Ubuntu" title="Installation - Debian Ubuntu">Installation - Debian Ubuntu</a> and <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_RPM" title="Installation - RPM">Installation - RPM</a> for instructions on how to get and use them. The Debian and RPM packages will install the filesender and simplesamlphp software in the <span style="font-family: courier new,courier;">/usr/share/</span> directory tree. In the examples below<span style="font-family: courier new,courier;"> /var/www</span> is used as base directory. Please adapt the examples below where appropriate when using the packages.</i></p>

<p>&nbsp;</p>

<h2 id="client_and_server_requirements">Client and Server Requirements</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Requirements_for_v1-1" title="Requirements_for_v1-1">Requirements_for_v1-1</a>.</p>

<h2 id="install_apache2">Install Apache2</h2>

<p>Install Apache2 from the Debian package repository:</p>

<p style="padding-left: 30px;"><span style="font-family: courier new,courier;">$ apt-get install apache2</span></p>

<h2 id="configure_apache2_with_ssl">Configure Apache2 with SSL</h2>

<p><span style="font-family: arial,helvetica,sans-serif;">FileSender assumes it will run on a webserver with SSL enabled, which is enforced by the ForceSSL setting in the FileSender configuration file, check <a class="wiki_link" href="#configure_your_filesender_installation" title="Configure your FileSender installation">Configure your FileSender installation</a></span><span style="font-family: courier new,courier;"><span style="font-family: arial,helvetica,sans-serif;">).&nbsp; Get a certificate and <a href="http://httpd.apache.org/docs/2.2/ssl/">configure your webserver with SSL</a>.&nbsp; Please note that a self-signed certificate will most likely cause upload problems with Flash (most notably the &quot;<a href="/spaces/file_sender/tickets/2038">#2038</a> IO Error&quot; but others have been seen).&nbsp; This is a Flash problem which is explained in more <a href="/wiki/show/file_sender/FAQ#71202d207369746520776f726b732077697468206874747020627574206e6f7420776974682068747470732c20756e636c656172206572726f72732e">detail in the FAQ</a>.</span></span></p>

<p><span style="font-family: courier new,courier;"><span style="font-family: arial,helvetica,sans-serif;">Disabling SSL means all file uploads and downloads are unprotected and any data transferred to and from your FileSender installation can be stolen.&nbsp; Disabling SSL is not advisable.</span></span></p>

<h2 id="install_and_configure_php5">Install and configure PHP5</h2>

<ul>
	<li><b>Install PHP5</b> from the Debian package repository:</li>
</ul>

<p style="padding-left: 60px;"><span style="font-family: courier new,courier;">$ apt-get install php5 php5-cgi</span></p>

<ul>
	<li><b>Check whether the GMP extension is enabled</b> (it usually is):</li>
</ul>

<p style="padding-left: 60px;"><span style="font-family: courier new,courier;">$cat /etc/php5/conf.d/gmp.ini</span><br />
<span style="font-family: courier new,courier;"># configuration for php GMP module</span><br />
<span style="font-family: courier new,courier;">extension=gmp.so</span></p>

<ul>
	<li><b>Change some PHP ini-settings</b> to allow for larger files, longer execution times and to turn on logging. As of version 1.0.1 a sample settings file is provided in the the FileSender config directory as <span style="font-family: courier new,courier;">filesender-php.ini</span>. This file can be stored in your <span style="font-family: courier new,courier;">/etc/php.d/</span> or <span style="font-family: courier new,courier;">/etc/php5/conf.d/</span> directory to activate those settings.&nbsp; Please adapt the sample settings file where needed. Alternatively you can manually edit your php.ini file:</li>
</ul>

<p style="padding-left: 60px;"><span style="font-family: courier new,courier;">$ gedit /etc/php5/apache2/php.ini</span></p>

<p style="padding-left: 60px;"><b>To allow for larger files and longer execution times you will need to edit these lines:</b></p>

<p style="padding-left: 90px;">max_input_time(in seconds)<br />
upload_max_filesize(in M)<br />
post_max_size (in M)</p>

<p style="padding-left: 90px;"><b>NOTE</b>: Remember to change filesender $config[&#39;max_flash_upload_size&#39;] to match your upload_max_filesize.If they are not the same FileSender will use the lowest value as the actual maximum upload size for Flash uploads.</p>

<p style="padding-left: 60px;">Reasonable values are:</p>

<p style="padding-left: 90px;">max_input_time = <b>3600</b><br />
upload_max_filesize = <b>2047M</b><br />
post_max_size = <b>2146445312</b> ; 2047M + 10K<br />
<b>&nbsp;</b></p>

<p style="padding-left: 60px;"><b>To change the temporary location for Flash uploads configure this in php.ini:</b></p>

<p style="padding-left: 90px;">upload_tmp_dir = <i>/your/temporarylocation </i></p>

<p style="padding-left: 90px;"><b>Note: </b>that this setting is for all PHP-apps, not only for filesender.</p>

<p style="padding-left: 90px;"><b>Note</b>: It is best to make this temporary folder location the same as your filesender $config[&#39;site_temp_filestore&#39;].</p>

<p style="padding-left: 60px;"><b>To turn on logging configure these lines in php.ini:</b></p>

<p style="padding-left: 90px;">log_errors = <b>on</b><br />
error_log =<b> syslog</b></p>

<p style="padding-left: 90px;">&nbsp;</p>

<ul>
	<li><b>When using Suhosin, </b>make sure your <b>/etc/php5/apache2/conf.d/suhosin.ini</b> contains the following:<b> </b></li>
</ul>

<pre>
; configuration for php suhosin module
extension=suhosin.so
&nbsp;
&nbsp;
; For Suhosin plugin versions before 0.9.33
suhosin.cookie.encrypt = off
; Needed for IE compatibility
suhosin.session.cryptua = off
; Needed for SimpleSAMLphp
suhosin.get.max_value_length = 2048
</pre>

<h2 id="install_and_configure_postgresql">Install and configure PostgreSQL</h2>

<p>PostgreSQL can be installed from your standard debian repository along with PostgreSQL support in PHP:</p>

<p style="padding-left: 30px;"><span style="font-family: courier new,courier;">$ apt-get install postgresql php5-pgsql</span></p>

<p>FileSender uses password based database logins and by default assumes that PostgreSQL is configured to accept password based sessions on &#39;localhost&#39;. You should check and when needed change the relevant settings in the PostgreSQL pg_hba.conf configuration file. This file should have the following entries with <b>md5</b> listed as METHOD for local IPv4 and IPv6 connections:</p>

<pre>
# Database administrative login by UNIX sockets
local&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; postgres&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ident
# TYPE&nbsp; DATABASE&nbsp;&nbsp;&nbsp; USER&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; CIDR-ADDRESS&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; METHOD
# &quot;local&quot; is for Unix domain socket connections only
local&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ident
# IPv4 local connections:
host&nbsp;&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 127.0.0.1/32&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b>md5</b>
# IPv6 local connections:
host&nbsp;&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; all&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ::1/128&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b>md5</b></pre>

<p>On Debian based systems this file will be in <span style="font-family: courier new,courier;">/etc/postgresql/&lt;version&gt;/main/pg_hba.conf </span>. On Red Hat/Fedora based systems this file will be in <span style="font-family: courier new,courier;">/var/lib/pgsql/data/pg_hba.conf</span> . When changing the pg_hba.conf file you&#39;ll have to restart the database server with (version number may be different or not needed depending on your system):</p>

<p style="padding-left: 30px;"><span style="color: #888888;"><span style="font-family: courier new,courier;">$ /etc/init.d/postgresql-8.3 restart</span></span></p>

<h2 id="install_simplesamlphp">Install SimpleSAMLphp</h2>

<p>To set up a working SimpleSAMLphp that uses the preconfigured !OpenIdP as an authentication mechanism follow this recipe:</p>

<ol>
	<li>Download <a href="http://code.google.com/p/simplesamlphp/downloads/list">SimpleSAMLphp 1.8.1</a> (note that recent Debian/Ubuntu have packages available, also the FileSender RPM and Debian repositories have SimpleSAMLphp packages).</li>
	<li>Some SimpleSAMLphp setups require the PHP mcrypt extension: <span style="font-family: courier new,courier;">apt-get install php-mcrypt</span></li>
	<li>Extract it into a suitable directory on your website such as /var/www/simplesamlphp-1.8.1</li>
	<li>Add &quot;Alias /simplesaml /var/www/simplesamlphp-1.8.1/www&quot; to your Apache virtual host configuration</li>
	<li>Copy the standard configuration files to the right places:</li>
</ol>

<p style="padding-left: 60px;"><i>$ cp -r config-templates/*.php config/<br />
$ cp -r metadata-templates/*.php metadata/</i></p>

<p>To tailor your <a href="http://simplesamlphp.org/">SimpleSAMLph</a>p installation to your local site please check its<a href="http://simplesamlphp.org/docs"> installation and configuration documentation</a>.</p>

<p>When connecting to an Identity provider make sure all the required attributes are sent by the identity provider. See the <a class="wiki_link" href="/wiki/show/file_sender/Administrator_reference_manual#idp_attributes" title="Administrator_reference_manual#idp_attributes">section on IdP attributes</a> in the Reference Manual for details.</p>

<p>By default the following attributes are set as required:</p>

<p style="padding-left: 30px;">mail<br />
eduPersonTargetedID<br />
cn</p>

<p>By default FileSender uses eduPersonTargetedID for the unique identification of the user (this can be changed in the configuration). If your identity provider doesn&#39;t provide the eduPersonTargetedID attribute you can either change the attrabute uniquely identyfing a user or alternatively you can add an authproc filter to the metadata of that Identity provider to locally generate an&nbsp;eduPersonTargetedID attribute . See <a href="http://simplesamlphp.org/docs/1.8/core:authproc_targetedid">http://simplesamlphp.org/docs/1.8/core:authproc_targetedid</a> for the details.</p>

<h2 id="install_the_filesender_package">Install the FileSender package</h2>

<ul>
	<li>Download the FileSender software from the FileSender 1.1 <a class="wiki_link" href="/wiki/show/file_sender/Download" title="Download">download page</a>.</li>
	<li>Extract the FileSender tarbal</li>
</ul>

<pre style="padding-left: 60px;">
<span style="font-family: courier new,courier;">tar zxvf /usr/local/src/filesender-1.1.tar.gz</span></pre>

<p style="padding-left: 60px;">This will create a directory &#39;<span style="font-family: courier new,courier;">filesender-1.1</span>&#39; . You can move that directory to the preferred location on your system. In this document we&#39;ll use <span style="font-family: courier new,courier;">/var/www/filesender </span>:</p>

<pre style="padding-left: 60px;">
mv filesender-1.1 /var/www/filesender</pre>

<ul>
	<li>Make the files, tmp and log directories writable by the web daemon user and allow the web deamon user to read the config.php configuration file:</li>
</ul>

<pre style="padding-left: 60px;">
cd /var/www/filesender
chown www-data:www-data tmp files log
chgrp www-data config/config.php</pre>

<p style="padding-left: 60px;">The directory structure and permissions should now be as follows, carefully check the entries marked in <b>bold</b>:</p>

<pre style="padding-left: 60px;">
filesender:/var/www/filesender# ls -l config/
total 24
<b>-rw-r-----</b> 1 root <b>www-data</b> 15347 2011-01-27 18:54 <b>config.php</b>

filesender:/var/www/filesender# ls -al
total 100
drwxr-xr-x 11 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 .
drwxr-xr-x&nbsp; 9 root&nbsp;&nbsp;   root  &nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:56 ..
-rw-r--r--&nbsp; 1 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp; 10783 2011-01-29 12:37 CHANGELOG.txt
drwxr-xr-x&nbsp; 2 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 classes
drwxr-xr-x&nbsp; 2 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 config
drwxr-xr-x&nbsp; 2 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 cron
drwxr-xr-x&nbsp; 2 <b>www-data www-data</b>&nbsp; 4096 2011-01-29 18:39 <b>files</b>
drwxr-xr-x&nbsp; 2 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 includes
-rw-r--r--&nbsp; 1 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 3318 2011-01-29 12:28 INSTALL.txt
-rw-r--r--&nbsp; 1 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 1554 2011-01-14 11:33 LICENCE.txt
drwxr-xr-x&nbsp; 2 <b>www-data www-data</b>&nbsp; 4096 2011-01-29 18:39 <b>log</b>
-rw-r--r--&nbsp; 1 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 2002 2011-01-29 12:28 README.txt
drwxr-xr-x&nbsp; 2 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 scripts
drwxr-xr-x&nbsp; 2 <b>www-data www-data</b>&nbsp; 4096 2011-01-29 18:39 <b>tmp</b>
drwxr-xr-x&nbsp; 6 root&nbsp;&nbsp;&nbsp;&nbsp; root&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 4096 2011-01-29 18:39 www</pre>

<ul>
	<li>Add an alias to your Apache virtual host configuration:</li>
</ul>

<p style="padding-left: 60px;">&lt;VirtualHost *&gt;</p>

<p style="padding-left: 90px;">...</p>

<p style="padding-left: 90px;">Alias /filesender /var/www/filesender/www</p>

<p style="padding-left: 90px;">...</p>

<p style="padding-left: 60px;">&lt;/VirtualHost&gt;</p>

<p style="padding-left: 60px;">this will make the FileSender web tree accessible through your web site.&nbsp; Alternatively you can simply point your DocumentRoot to /var/www/filesender/www</p>

<p>&nbsp;</p>

<h2 id="create_the_filesender_user_and_database">Create the FileSender user and database</h2>

<p>Run the following commands in a terminal to create the PostgreSQL user and&nbsp; database to be used by FileSender.</p>

<p>Create the database user <span style="font-family: courier new,courier;">filesender</span> without special privileges and with a password. The command will prompt you to specify and confirm a password for the new user. This is the password you need to configure in the FileSender configuration file.</p>

<pre>
$ sudo -u postgres createuser -S -D -R -P filesender
Enter password for new role: <b>&lt;secret&gt;</b>
Enter it again: <b>&lt;secret&gt;</b></pre>

<p>Create the filesender database with UTF8 encoding owned by the newly created filesender user:</p>

<pre>
$ sudo -u postgres createdb -E UTF8 -O filesender filesender
$ psql -h localhost filesender filesender &lt; /var/www/filesender/scripts/filesender_db.sql
Password for user filesender: <b>&lt;secret&gt;</b>
NOTICE:&nbsp; CREATE TABLE will create implicit sequence &quot;files_fileid_seq&quot; for serial column &quot;files.fileid&quot;
NOTICE:&nbsp; CREATE TABLE / PRIMARY KEY will create implicit index &quot;files_pkey&quot; for table &quot;files&quot;
CREATE TABLE
CREATE SEQUENCE
NOTICE:&nbsp; CREATE TABLE / PRIMARY KEY will create implicit index &quot;logs_pkey&quot; for table &quot;logs&quot;
CREATE TABLE</pre>

<p>&nbsp;</p>

<h2 id="configure_your_filesender_installation">Configure your FileSender installation</h2>

<p>To configure your FileSender installation, edit</p>

<p style="padding-left: 30px;"><b>/var/www/filesender/config/config.php</b></p>

<p>Carefully check and adapt the following settings. The minimum required changes to config.php are marked in <b>bold</b>:</p>

<pre style="padding-left: 30px;">
$config[&#39;admin&#39;] = &#39;&#39;;
$config[&#39;adminEmail&#39;] = &#39;<b>Your.Address@example.org</b>&#39;;
$config[&#39;Default_TimeZone&#39;] = &#39;<b>Europe/Berlin</b>&#39;;

$config[&#39;site_url&#39;] = $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;<b>/filesender/</b>&#39;; // URL to Filesender
$config[&#39;site_simplesamlurl&#39;] =&nbsp; $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;<b>/simplesaml/</b>&#39;;

$config[&#39;site_filestore&#39;] = &#39;<b>/var/www/filesender/files/</b>&#39;; 
$config[&#39;site_temp_filestore&#39;] = &#39;<b>/var/www/filesender/tmp/</b>&#39;; 
$config[&#39;site_simplesamllocation&#39;] = &#39;<b>/var/www/simplesamlphp-1.8.1/</b>&#39;;
$config[&#39;log_location&#39;] = &#39;<b>/var/www/filesender/log/</b>&#39;; 

$config[&#39;site_name&#39;] = &#39;FileSender&#39;;

$config[&#39;forceSSL&#39;] = true;

$config[&#39;pg_host&#39;] = &#39;localhost&#39;; // postgres database host
$config[&#39;pg_database&#39;] = &#39;filesender&#39;;   // name of database on postgres
$config[&#39;pg_port&#39;] = &#39;5432&#39;; // default port
$config[&#39;pg_username&#39;] = &#39;filesender&#39;; // username to connect to postgress database 
$config[&#39;pg_password&#39;] = &#39;<b>&lt;secret&gt;</b>&#39;;  // password to connect to postgress database</pre>

<p>Detailed information about the configuration settings of FileSender can be found in the <a class="wiki_link" href="/wiki/show/file_sender/Administrator_reference_manual" title="Administrator reference manual">Administrator reference manual</a></p>

<h2 id="configure_cron">Configure Cron</h2>

<p>Cron jobs are scheduled by setting up a &quot;crontab.&quot; A crontab is a text file that contains the commands to be run.<br />
Filesender uses a Cron job to remove files that have expired and close any vouchers that have expired.<br />
Typically you would run the Cron job every night at a set time. Note that the Debian and RPM packages will install the required cronjob for you.</p>

<p>To edit a crontab through the command line, type:</p>

<p><code>crontab -e</code></p>

<p>Add the following line:</p>

<p><code>0 0 * * * php -q /var/www/filesender/cron/cron.php</code></p>

<p>This will run your cron page nightly at midnight.</p>

<h2 id="start_using_filesender">Start using FileSender</h2>

<p style="padding-left: 30px;">https://yoursite/filesender/</p>

<h2 id="support_and_feedback">Support and Feedback</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Support_and_Mailinglists" title="Support and Mailinglists">Support and Mailinglists</a> and <a class="wiki_link" href="/wiki/show/file_sender/Feature_requests" title="Feature requests">Feature requests</a>.</p>

