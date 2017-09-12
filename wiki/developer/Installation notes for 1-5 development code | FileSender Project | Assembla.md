<p>&nbsp;</p>

<h1 id="availability">Availability</h1>

<p>As of February 2012 13th beta builds of the development branch of FileSender 1.5 are available in the various <b>unstable</b> repositories and as of October 22nd 2012 the first release candidate (rc1) is available. The 1.5-rc1 code is thoroughly tested and considered stable but will be field tested on production servers for a period of at least two weeks to verify release readiness.</p>

<p>Installation and configuration of FileSender 1.5 can be done by following the relevant documentation for version 1.1.x. Exceptions and additions are listed below.</p>

<p>&nbsp;</p>

<h1 id="download">Download</h1>

<p>(Pre-)release Debian and RPM packages are available in the <b>unstable</b> <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Debian_Ubuntu" title="Installation - Debian Ubuntu">Debian</a> and <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_RPM" title="Installation - RPM">RPM</a> package repositories.</p>
Regularly updated .tar.gz and .zip distribution files are available from <a href="http://repository.filesender.org/unstable/">http://repository.filesender.org/unstable/&nbsp;</a> and for official beta releases at <a href="https://download.filesender.org">https://download.filesender.org</a>/ See <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source" title="Installation - Linux Source">Installation - Linux Source</a> for general installation instructions.

<p>The latest code for (pre-releases of) 1.5 is always available from the <a href="http://subversion.assembla.com/svn/file_sender/filesender/branches/filesender-1.5/">Subversion repository</a>. You can create a local working copy with:</p>

<pre>
svn co http://subversion.assembla.com/svn/file_sender/filesender/branches/filesender-1.5</pre>

<p>If you want to track the more rapidly changing development-code of 1.5 (and further) you can use the SVN trunk:</p>

<pre>
svn co http://subversion.assembla.com/svn/file_sender/filesender/trunk</pre>

<h1 id="c2a0">&nbsp;</h1>

<h1 id="requirements">Requirements</h1>

<h2 id="client_side">Client side</h2>

<p>1.5 uses the HTLM5 FileAPI for large uploads which means that Gears is not needed anymore. For large uploads you&#39;ll need a modern browser which can use the HTML5 FileAPI, for example FireFox 4+ and Google Chrome. For &#39;older&#39; browsers (including IE9 and Safari 5.1) without support for the HTML5 File API uploads are limited to 2 GB and still require Adobe Flash.</p>

<h2 id="server_side">Server side</h2>

<p>FileSender 1.5 does work with PHP 5.2.x but on some platforms 5.3 might be required due to secondary dependencies.</p>

<p>Filesender 1.5 introduces a database abstraction layer to be able to use either PostgreSQL or MySQL based on PDO (available on most default PHP installs).</p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h1 id="757067726164696e672066726f6d2070726576696f75732072656c65617365733c62723e">Upgrading from previous releases</h1>

<p>When upgrading from a source package (tar.gz or zip) It is strongly recommended that you do a fresh install after making a backup copy of your previous install and carefully re-apply any local code changes you have made in previous versions. Similarly when upgrading using svn with local modifications it is recommended to do a fresh export instead of a repository switch.</p>

<p>In all cases when upgrading from a previous release (either beta or stable) it is recommended to carefully compare&nbsp; your config.php with the distributed config-dist.php. Other important changes that require extra attention when upgrading from a specific release are mentioned below.</p>

<p>&nbsp;</p>

<h1 id="upgrading_from_1.5-beta1">Upgrading from 1.5-beta1</h1>

<h3 id="2e2f636f6e666967206469726563746f7279">./config directory</h3>

<p>As of 1.5-beta2 the ./config directory as distributed only contains a sample config-dist.php file. All other templates/sample files have been moved to ./config-templates or their contents have been merged into the ./language/* files. This means that when unpacking a release file won&#39;t overwrite existing configuration files. To get a working configuration copy config-dist.php to config.php and make the appropriate changes in config.php.</p>

<h3 id="language_files">Language files</h3>

<p>As of 1.5-beta2 (or svn trunk revision 1297) the naming of the language files has changed. Also as of 1.5-beta2 the &#39;customisable&#39; language files that used to be in<span style="font-family: courier new,courier;"> ./config</span> have been merged with/moved to the distribution language files in <span style="font-family: courier new,courier;">./language</span>. Due to the changed naming scheme, language files that are in <span style="font-family: courier new,courier;">./config</span> won&#39;t be used anymore <b>except</b> for the file <span style="font-family: courier new,courier;">locale.php</span>. If you don&#39;t have local customisations you should remove<span style="font-family: courier new,courier;"> locale.php</span> and other language files from the<span style="font-family: courier new,courier;"> ./config</span> directory. If you do have local customisations please change<span style="font-family: courier new,courier;"> ./config/locale.php</span> and (if applicable) the names of the language files according to the naming scheme described in<span style="font-family: courier new,courier;"> ./language/README.language</span>.</p>

<h3 id="database_changes">Database changes</h3>

<p>Due to a change in the back-end workflow the database type of the fileto and corresponding logto columns needs to be changed from varchar(250) to text. Not doing so will break uploads to multiple recipients exceeding the 250 character limit when combined.</p>

<p>&nbsp;</p>

<p>For Postgresql:</p>

<pre>
#sudo -u postgres psql filesender
&nbsp;&nbsp;   ALTER TABLE files ALTER fileto TYPE text;
&nbsp;&nbsp;   ALTER TABLE logs ALTER logto TYPE text;
&nbsp;    \q</pre>

<p>For MySQL:&nbsp;</p>

<pre>
#sudo mysql filesender
&nbsp;&nbsp;  ALTER TABLE files CHANGE fileto fileto text default null;
&nbsp;&nbsp;  ALTER TABLE logs CHANGE logto logto text default null;
    quit
</pre>
&nbsp;

<h1 id="757067726164696e672066726f6d20312e302e782f312e312e78">Upgrading from 1.0.x/1.1.x</h1>

<h3 id="client_side_notes">Client side notes</h3>

<p>Due to changes in the css/default.css stylesheet definitions users might experience a garbled layout of the FileSender pages just after upgrading to 1.5.&nbsp; This is caused by a long cache expiry date for static files which depends on the (default) expiry/cache control settings of your webserver. When this happens the user can fix this by reloading the page in the browser.</p>

<p>&nbsp;</p>

<h3 id="database_changes">Database changes</h3>

<ul>
	<li>The changes mentioned above for upgrading from 1.5-beta1 also are required when upgrading from 1.0.x/1.1.x.</li>
	<li>With 1.5 it is now <b>required</b> to adjust the files table in the database if the database was created with a FileSender version before 1.0.1. Please execute the following if not already done when upgrading to 1.0.1:</li>
</ul>

<pre>
   #sudo -u postgres psql filesender
&nbsp;&nbsp;   ALTER TABLE files ALTER fileip6address TYPE character varying(45);
&nbsp;    \q</pre>

<ul>
	<li>The fileauthuserid column in the files table now has a size of 500, consistent with the corresponding column in the logs table and to allow for SAML attributes with very large values. When upgrading from a previous version execute:</li>
</ul>

<pre>
&nbsp;&nbsp; #sudo -u postgres psql filesender
&nbsp;&nbsp;&nbsp;&nbsp; ALTER TABLE files ALTER fileauthuseruid TYPE character varying(500);
     \q</pre>

<h1 id="c2a0">&nbsp;</h1>

<h1 id="configuration_of_database_parameters">Configuration of database parameters</h1>

<p>Configuration of the database connection parameters in config.php has changed to a database-type independent method. The old PostgreSQL-specific pg_* settings are now obsolete and must be replaced with their new equivalents (db_*) including a specification of the database type:&nbsp;</p>

<pre>
&nbsp;&nbsp; $config[&quot;db_type&quot;] = &quot;pgsql&quot;;// pgsql or mysql
  &nbsp;$config[&#39;db_host&#39;] = &#39;localhost&#39;;
&nbsp;&nbsp; $config[&#39;db_database&#39;] = &#39;filesender&#39;;
&nbsp;&nbsp; $config[&#39;db_port&#39;] = &#39;5432&#39;;
&nbsp;&nbsp; // database username and password
&nbsp;&nbsp; $config[&#39;db_username&#39;] = &#39;filesender&#39;;
&nbsp;&nbsp; $config[&#39;db_password&#39;] = &#39;yoursecretpassword&#39;;</pre>

<p>To accomodate more&nbsp; elaborate PDO database settings a DSN style database setting can be configured which will override the db_* settings:</p>

<pre>
&nbsp;&nbsp;&nbsp; //Optional DSN format overides db_ settings
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn&#39;] = &quot;pgsql:host=localhost;dbname=filesender&quot;;
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn&#39;] = &#39;pgsql:host=localhost;dbname=filesender&#39;;
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn&#39;] = &#39;sqlite:/usr/share/filesender/db/filesender.sqlite&#39;;
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn_driver_options&#39;] = array();
&nbsp;&nbsp;&nbsp; // dsn requires username and password in $config[&#39;db_username&#39;] and $config[&#39;db_password&#39;]</pre>

<h4 id="24636f6e6669675b2764736e275d" style="padding-left: 30px;">$config[&#39;dsn&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description: </i></b>the &#39;URL&#39; pointing to the FileSender database</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> none</p>

<h1 id="c2a0">&nbsp;</h1>

<h1 id="using_mysql_as_backend_database">Using MySQL as backend database</h1>

<p><b><i>** Volunteers needed for testing and documenting **</i></b></p>

<p>Currently all documentation and the RPM and Debian packages are based on using PostgreSQL as database backend. With 1.5 it is possible though to use MySQL. A sample SQL-script to create the database is provided in <span style="font-family: courier new,courier;">scripts/mysql_filesender_db.sql</span></p>

<h1 id="c2a0">&nbsp;</h1>

<h1 id="important_changes_in_config.php">Important changes in config.php</h1>

<h3 id="localised_configuration_settings">Localised configuration settings</h3>

<p>A number of configurable settings have been moved to the language files in <span style="font-family: courier new,courier;">./language</span>. They still can be customised. See [<span style="background-color: #ffff00;">TBD</span>] for details.</p>

<p><b>&nbsp;</b></p>

<p><b>-Date display format</b></p>

<p>The display formats of dates are now defined in the language files for all browser pages.</p>

<pre>
&nbsp; $config[&#39;datedisplayformat&#39;]&nbsp; -&gt; $lang[&#39;datedisplayformat&#39;] (default&nbsp; &quot;d-m-Y&quot; for en_AU)) </pre>

<p>The $config[&#39;datedisplayformat&#39;] is at this moment still used for formatting the exipry date of a file/voucher in outgoing mails.</p>

<p>Note: The display format of dates has been changed to use the <a href="http://www.php.net/manual/en/function.date.php" target="_blank">PHP-format</a> (instead of the previously used Flex format). The old format used in 1.1 was DD-MM-YYYY which when used in 1.5 will give you something like &#39;WedWed-SepSep-2011201120112011&#39; . Please keep this in mind when transferring a custom format from a config.php in 1.0.x or 1.5 svn versions dated before August 24th 2011.</p>

<p>&nbsp;</p>

<p>-<b> All AuP related textual settings</b></p>

<pre>
&nbsp;&nbsp; $config[&quot;AuP_label&quot;] -&gt; $lang[&quot;_ACCEPTTOC&quot;]
&nbsp;&nbsp; $config[&quot;AuP_terms&quot;] -&gt; $lang[&quot;_AUPTERMS]&quot;</pre>

<p><b>- Site &#39;splash&#39; text</b></p>

<pre>
&nbsp;&nbsp; $config[&quot;site_splashtext&quot;] -&gt; $lang[&quot;_SITE_SPLASHTEXT &quot;]</pre>

<h4 id="64656661756c74206c616e6775616765203c62723e">Default language</h4>

<p>The previously unused $config[&#39;site_defaultlanguage&#39;]&nbsp; setting is as of 1.5-beta2 used to set a default language when the browser has an unsupported language preference. The (new) default is &#39;en_AU&#39;.</p>

<pre>
$config[&#39;site_defaultlanguage&#39;]&nbsp; = &#39;en_AU&#39; ;
</pre>

<h4 id="gears_to_html5_transition">Gears to HTML5 transition</h4>

<p>- Setting for maximum filesize</p>

<p>&nbsp;The max_gears_upload_size config setting is now obsolete and has been replaced with:&nbsp;</p>

<pre>
&nbsp;  $config[&#39;max_html5_upload_size&#39;]</pre>

<p>- In 1.5-beta1 to beta3 the gearsURL setting was replaced by the HTML5URL setting. As of 1.5-beta4 the HTML5 logo now points to the standard help and the HTML5URL setting has been removed.</p>

<p><strike>- URL for information on HTML5</strike></p>

<p><strike>The gearsURL setting has been replaced with a new HTML5URL setting:</strike></p>

<pre>
<strike>&nbsp;  $config[&#39;HTML5URL&#39;] = &#39;http://html5test.com/&#39;; </strike>
</pre>

<p>- The upload chunk size for HTML5 uploads is now a configurable setting&nbsp;</p>

<pre>
   $config[&quot;upload_chunk_size&quot;] </pre>

<h4 id="3c623e61626f75742c2068656c7020616e642061757020746578743c2f623e" style="font-weight: normal;"><b>About, Help and AuP text</b></h4>

<p>As of <a href="https://www.assembla.com/code/file_sender/subversion/changesets/858">revision:858</a> the semantics of aboutURL and helpURL in the config.php have changed.&nbsp; They can now point to a *page* resulting in a new page being opened in a new tab, or they can be empty, resulting in a popup. The new defaults as of 1.5 are the empty value (&quot;&quot;)&nbsp; Note that the popups are &quot;not popups as per opening a popup window but modal inline popups that have nothing to do with popup blockers.&quot;. The popup is populated from the language file, using _HELP_TEXT and _ABOUT_TEXT.&nbsp; You can have a localised override in your config directory [TBD].</p>

<p>&nbsp;</p>

<p>Relevant config.php directives:</p>

<pre>
&nbsp;  $config[&#39;aboutURL&#39;] = &quot;&quot;;
&nbsp;&nbsp; $config[&#39;helpURL&#39;] = &quot;&quot;;</pre>

<p>Relevant settings in language files:</p>

<pre>
&nbsp;&nbsp; $lang[&quot;_HELP_TEXT&quot;]
&nbsp;&nbsp; $lang[&quot;_ABOUT_TEXT&quot;]
&nbsp;&nbsp; $lang[&quot;_AUPTERMS&quot;]</pre>

<h4 id="3c623e74656d70206469726563746f72793c2f623e"><b>temp directory</b></h4>

<p style="padding-left: 30px;">as of <a href="https://www.assembla.com/code/file_sender/subversion/changesets/871">revision:871</a> the temp directory is no longer used for FileSender specific actions.&nbsp; This means the config directive <i><span class="was">$config[&quot;site_temp</span>_filestore&quot;];</i> is no longer used.&nbsp; If you have configured PHP to use the previously configured site_temp_filestore you can keep that directory and it will still be used for Flash uploads. The setting and use of that directory is now however only defined in the site-wide PHP settings. It is still advised to keep that directory on the same disk partition as the FileSender filestore.</p>

<h3 id="new_configuration_settings_in_config.php">New configuration settings in config.php</h3>

<pre>
 &nbsp; $config[&quot;displayerrors&quot;] = false; // Display debug errors on screen (true/false)
 &nbsp; $config[&quot;upload_chunk_size&quot;]&nbsp; = &#39;2000000&#39;;
</pre>

<p>As of beta3 it is possible to use a configurable &#39;shred&#39; command in the daily cron job to securely wipe instead of just &#39;unlink&#39; expired and deleted files. Note that this will increase the time needed for the cron job to run significantly. Sites running the cron job with an increased frequency (instead of daily) should check the timings carefully. The default is to just unlink the files, to activate check if the command to be used is available and set $config[&#39;cron_shred&#39;] to <b>true</b>.</p>

<pre>
   $config[&#39;cron_shred&#39;] = false; // instead of simply unlinking, overwrite expired files so they are hard to recover
   $config[&#39;cron_shred_command&#39;] = &#39;/usr/bin/shred -f -u -n 1 -z&#39;; // overwrite once (-n 1) with random data, once with zeros (-z), then remove (-u)
</pre>

<h3 id="new_mail_template_macros">New Mail template macros</h3>

<p>{htmlfileoriginalname} : HTML version of {fileoriginalname}</p>

<p>{filemessage_start} and {filemessage_end} : markers for begin and end of the (optional) personal message</p>

<h2 id="language_definitions">Language definitions</h2>

<p><span><span style="background-color: #ff9999;">[To be done]</span></span></p>

<h2 id="os_specific_notes">OS specific notes</h2>

<p>&nbsp;none</p>

<h2 id="packaging_notes">Packaging notes</h2>

<p>The 1.5-xxx Debian and RPM packages will update any previous (package) install of FileSender, including 1.0.x stable and testing packages. As of 1.5-beta1 the versioning has changed slightly if you have installed a 1.5.0-* Debian/RPM package from before 1.5-beta1 this means that you&#39;ll have to &#39;downgrade&#39; the package, for example:<br />
<br />
RPM: &#39;downgrade&#39; to filesender.noarch 0:1.5-0.1.beta1<br />
&nbsp;&nbsp; yum downgrade filesender<br />
<br />
Debian: &#39;downgrade&#39; to filesender_1.5~beta1<br />
&nbsp;&nbsp; apt-get install filesender=1.5~beta1</p>

<p>When upgrading the previously unstable 1.0.x-yyyymmddhhmm versions any empty directory created by the older version will be removed. If you&#39;re using the experimental <a class="wiki_link" href="/wiki/show/file_sender/Mail_Bounce_Handling" title="Mail Bounce Handling">Mail Bounce Handling</a> you&#39;ll need to manually recreate and symlink the maildrop tree.</p>

<h3 id="-_debian_.deb">- Debian .deb</h3>

<p>The unstable and testing repositories have SimpleSAMLphp 1.8.x packages. As of version 1.7.0 the Debian SimpleSAMLphp packaging switched the default baseurl from &#39;simplesaml/&#39; to &#39;simplesamlphp/&#39; to adhere to standard Debian policies. This change is also refelected in the FileSender packages in testing and unstable. This might break upgrades from previous versions that were installed with SimpleSAMLphp version 1.6.3. Please check the relevant settings in /etc/simplesamlphp/config.php, /etc/filesender/config.php and your webserver config (Alias statements).&nbsp;</p>

