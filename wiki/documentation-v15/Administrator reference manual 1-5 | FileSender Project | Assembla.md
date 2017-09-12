<h2 id="74686973206973207468652061646d696e6973747261746f72207265666572656e6365206d616e75616c20666f722066696c6573656e6465722076657273696f6e20312e352e20c2a0">This is the Administrator Reference Manual for FileSender version 1.5. &nbsp;</h2>
&nbsp;

<ul>
	<li><a class="wiki_link" href="#1._administering_filesender" title="1. Administering FileSender">1. Administering FileSender</a>

	<ul>
		<li><a class="wiki_link" href="#1.1_installation_and_initial_configuration" title="1.1 Installation and initial configuration">1.1 Installation and initial configuration</a></li>
		<li><a class="wiki_link" href="#1.2_regular_tasks" title="1.2 Regular tasks">1.2 Regular tasks</a></li>
		<li><a class="wiki_link" href="#1.3_the_administrator_web_interface" title="1.3 The Administrator web interface">1.3 The Administrator web interface</a></li>
		<li><a class="wiki_link" href="#1.4_troubleshooting" title="1.4 Troubleshooting">1.4 Troubleshooting</a></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#2._authenticating_users" title="2. Authenticating users">2. Authenticating users</a>
	<ul>
		<li><a class="wiki_link" href="#idp_attributes" title="IdP Attributes">IdP Attributes</a></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#3._security_considerations" title="3. Security considerations">3. Security considerations</a>
	<ul>
		<li><span style="background-color: #ffffff;"><a href="#Warning%20-%20Encryption">Warning - Encryption</a></span></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#4._customising_the_look_and_feel_of_your_filesender_installation" title="4. Customising the look and feel of your FileSender installation">4. Customising the look and feel of your FileSender installation</a>
	<ul>
		<li><a class="wiki_link" href="#4.1_banner" title="4.1 Banner">4.1 Banner</a></li>
		<li><a class="wiki_link" href="#4.2_favicon" title="4.2 Favicon">4.2 Favicon</a></li>
		<li><a class="wiki_link" href="#4.3_site_name" title="4.3 Site name">4.3 Site name</a></li>
		<li><a class="wiki_link" href="#4.4_landing_page_splash_text" title="4.4 Landing page splash text">4.4 Landing page splash text</a></li>
		<li><a class="wiki_link" href="#4.5_various_ui_settings_toggles" title="4.5 Various UI settings toggles">4.5 Various UI settings toggles</a></li>
		<li><a class="wiki_link" href="#4.6_date_formats" title="4.6 Date formats">4.6 Date formats</a></li>
		<li><a class="wiki_link" href="#4.7_terms_and_conditions_(aup)_controls" title="4.7 Terms and Conditions (AuP) controls">4.7 Terms and Conditions (AuP) controls</a></li>
		<li><a class="wiki_link" href="#4.8_custom_help_and_about" title="4.8 Custom help and about">4.8 Custom help and about</a><span style="background-color: rgb(255, 255, 255);">&nbsp;</span></li>
		<li><span style="background-color: rgb(255, 255, 255);"><a class="wiki_link" href="#4.9_custom_logout_url" title="4.9 Custom logout URL">4.9 Custom logout URL</a></span>&nbsp;</li>
		<li><a class="wiki_link" href="#4.10_email_customisation" title="4.10 Email customisation">4.10 Email customisation</a>&nbsp;</li>
		<li><a class="wiki_link" href="#4.11_customising_simplesamlphp" title="4.11 Customising SimpleSAMLphp">4.11 Customising SimpleSAMLphp</a></li>
	</ul>
	</li>
</ul>

<ul>
	<li><a class="wiki_link" href="#5._dealing_with_language_files_and_localisation" title="5. Dealing with language files and localisation">5. Dealing with language files and localisation</a>&nbsp;

	<ul>
		<li><a class="wiki_link" href="#5.1_internationalisation_and_character_encoding" title="5.1 Internationalisation and character encoding">5.1 Internationalisation and character encoding</a></li>
		<li><a class="wiki_link" href="#5.2_technical_details_about_the_language_file_mechanism" title="5.2 Technical details about the language file mechanism">5.2 Technical details about the language file mechanism</a></li>
		<li><a class="wiki_link" href="#5.3_customising_languages" title="5.3 Customising languages">5.3 Customising languages</a></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#6._technical_details_about_pause_-_resume_functionality" title="6. Technical details about pause - resume functionality">6. Technical details about pause - resume functionality</a></li>
	<li><a class="wiki_link" href="#7._configuration_file_directives" title="7. Configuration file directives">7. Configuration file directives</a>&nbsp;
	<ul>
		<li><a class="wiki_link" href="#general_settings" title="General settings">General settings</a></li>
		<li><a class="wiki_link" href="#user_interface_(ui)_settings" title="User Interface (UI) settings">User Interface (UI) settings</a></li>
		<li><a class="wiki_link" href="#debug_settings" title="Debug settings">Debug settings</a></li>
		<li><a class="wiki_link" href="#saml_attribute_settings" title="SAML attribute settings">SAML attribute settings</a></li>
		<li><a class="wiki_link" href="#acceptable_use_policy_(aup)_settings" title="Acceptable Use Policy (AUP) settings">Acceptable Use Policy (AUP) settings</a></li>
		<li><a class="wiki_link" href="#server_settings" title="Server settings">Server settings</a></li>
		<li><a class="wiki_link" href="#advanced_server_settings" title="Advanced server settings">Advanced server settings</a></li>
		<li><a class="wiki_link" href="#site_url_settings" title="Site URL settings">Site URL settings</a></li>
		<li><a class="wiki_link" href="#support_links" title="Support links">Support links</a></li>
		<li><a class="wiki_link" href="#file_and_directory_location_settings" title="File and directory location settings">File and directory location settings</a></li>
		<li><a class="wiki_link" href="#database_related_settings" title="Database related settings">Database related settings</a></li>
		<li><a class="wiki_link" href="#cron_settings" title="Cron settings">Cron settings</a></li>
		<li><a class="wiki_link" href="#email_related_configuration_directives" title="Email related configuration directives">Email related configuration directives</a></li>
		<li><a class="wiki_link" href="#email_template_variables" title="Email template variables">Email template variables</a></li>
		<li><a class="wiki_link" href="#6e6f7420696d706c656d656e7465642f756e75736564" title="Not implemented/unused">Not implemented/unused</a></li>
	</ul>
	</li>
</ul>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2 id="1._administering_filesender">1. Administering FileSender</h2>

<h3 id="1.1_installation_and_initial_configuration">1.1 Installation and initial configuration</h3>

<p>Consult the relevant installation guide:</p>

<ul>
	<li><a href="/spaces/file_sender/wiki/Installation_-_Linux_Source">Installation - Linux Source</a></li>
	<li><a href="/spaces/file_sender/wiki/Installation_-_Debian_Ubuntu">Installation - Debian Ubuntu</a></li>
	<li><a href="/spaces/file_sender/wiki/Installation_-_RPM">Installation - RPM</a></li>
</ul>

<h3 id="1.2_regular_tasks">1.2 Regular tasks</h3>

<ol>
	<li><b>Make sure the daily expiry cron job runs</b>.&nbsp; This is needed to delete files and vouchers that have expired, as well as to remove stale database entries from cancelled uploads. The debian and RPM packages will install a daily cronjob for you in /etc.cron.daily/filesender. When installed from source make sure you have installed a cronjob as per the <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source#configure_cron" title="Installation - Linux Source#Configure cron">Configure cron</a> section in the Installation Guide.</li>
	<li><b>Clean temp_filestore and log directories.</b>&nbsp; FileSender does not do any of this automatically so you as a server admin need to ensure this happens.&nbsp; The temp_filestore tends to get filled with files that are leftover when a user cancels an upload.&nbsp; Log files are created on a daily basis but are not automatically purged.</li>
	<li><b>Check logfiles for errors</b>.&nbsp;</li>
	<li><b>Database cleanup</b>: every upload to FileSender results in one or more database entries.&nbsp; Not all of these are deleted which could lead to performance degradation in the long run.&nbsp; You should check your database what the situation is and whether it needs cleanup of very old entries.</li>
</ol>

<h3 id="1.3_the_administrator_web_interface">1.3 The Administrator web interface</h3>

<p>The administrator web interface is accessed through the regular FileSender user interface.&nbsp; An &#39;Administration&#39; button becomes visible next to MyFiles when you log on with an account that has a GUID (like <i>eduPersonTargetedId</i> or <i>eduPersonPrincipalName</i>) configured in <span style="font-family: courier new,courier;">$config[&#39;admin&#39;]</span>.&nbsp; The administrator web interface provides an easy overview of the use of your FileSender installation.</p>

<h3 id="1.4_troubleshooting">1.4 Troubleshooting</h3>

<h4 id="relevant_logfiles_to_check">Relevant logfiles to check</h4>

<p>Relevant logging can appear at three places:</p>

<ol>
	<li>the FileSender logdirectory as configured in your config file with <span style="font-family: courier new,courier;">$config[&#39;log_location&#39;]</span></li>
	<li>your webserver logs</li>
	<li>your PHP logs (as per the relevant php.ini settings, often your /var/log/messages or /var/log/syslog file)</li>
</ol>

<p>! If there is no logging in your FileSender log directory, make sure the web server can write to it.</p>

<p>! If nothing works you might have issues with connecting to your database.&nbsp; Increase database logging to study interaction between your database and FileSender.</p>

<h4 id="getting_more_debugging_information">Getting more debugging information</h4>

<p>In case of problems you can turn on debugging in the FileSender configuration (see <a class="wiki_link" href="#debug_settings" title="Debug settings">Debug settings</a> for the relevant directives). Setting<span style="font-family: courier new,courier;"> $config[&#39;debug&#39;] = true</span> will turn on extra logging (both for FileSender in the FileSender log-directory and PHP) and additionally will show some extra technical information.</p>

<p id="266e6273703b266e6273703b266e6273703b266e6273703b266e6273703b266e6273703b266e6273703b2024636f6e6669675b22636c69656e745f73706563696669635f6c6f6767696e675f75696473225d">To investigate client (browser) problems (for a specific user) you can enable client specific logging by setting <span style="font-family: courier new,courier;">$config[&quot;client_specific_logging&quot;] = true</span>. By default this will generate extra logfiles <b>per user </b>for all users in the FileSender log directory with details about the relevant actions taken by the client. You can restrict the client specific logging to specific clients by specifying a GUID or Voucher ID with the <span style="font-family: courier new,courier;">$config[&quot;client_specific_logging_uids&quot;]</span> directive.</p>

<p>Note that turning on the debug settings will decrease performance so don&#39;t forget to turn off the debugging after investigation.</p>

<p>&nbsp;</p>

<h2 id="322e2061757468656e7469636174696e672075736572733c62723e">2. Authenticating users</h2>

<p>FileSender<b> has no built-in local user database</b>.&nbsp; It uses the <a href="http://simplesamlphp.org/">SimpleSAMLphp</a> software to connect to your authentication source of choice.&nbsp; With SimpleSamlPHP you can connect to most authentication sources you can imagine.&nbsp; RADIUS, LDAP, SQL, flat file, SAML 2.0 IdPs, Shibboleth, YubiKey, Twitter, Google: whatever you need to chances are SimpleSAMLphp will let you use it, out of the box.&nbsp; Check <a href="http://simplesamlphp.org/docs/stable/simplesamlphp-idp#section_2">SimpleSAMLphp&#39;s list of supported authentication modules</a> for details.</p>

<p>&nbsp;</p>

<p>The default FileSender installation and configuration uses Feide OpenIDP.&nbsp; This ensures you&#39;ll be up and running within the hour and can test your FileSender install. &nbsp; To connect your FileSender installation to your authentication source(s) of choice, please check the <a href="http://simplesamlphp.org/docs/1.6/simplesamlphp-sp">SimpleSAML Service Provider Quickstart</a>.&nbsp; If you have a question about how to configure SimpleSAMLphp, please consider asking your question on <a href="http://simplesamlphp.org/lists">the SimpleSAMLphp mailinglists</a></p>

<p>&nbsp;</p>

<p>In SimpleSAMLphp terms, your FileSender + SimpleSAMLphp installation is a <i><b>Service Provider (SP)</b></i>.&nbsp; It uses one or more <i><b>Identity Providers (IdP)</b></i> to do the authentication and provide attributes to FileSender.&nbsp; This Identity Provider will supply the FileSender software with information about the user: attributes.</p>

<h4 id="3c693e69647020617474726962757465733c2f693e"><i>IdP Attributes</i></h4>

<p>FileSender <b>needs</b> two attributes to work:</p>

<ul>
	<li>something that uniquely identifies every user (saml_uid_attribute)</li>
	<li>something that supplies the user&#39;s email address (saml_email_attribute)</li>
</ul>

<div>&nbsp;</div>

<div>
<p>An error &quot;<i>Your Identity Provider is not providing the required attributes</i>&quot; will be thrown if FileSender doesn&#39;t receive these attributes when a user logs in.</p>
</div>

<div>&nbsp;</div>

<div>You may supply an <b>optional</b> third attribute:</div>

<ul>
	<li>something that supplies the user&#39;s &quot;friendly name&quot; (saml_name_attribute)</li>
</ul>

<p><span style="font-size: 13px;">Please consult&nbsp;</span><b style="font-size: 13px; line-height: 17px;">$config[&#39;displayUserName&#39;] </b><span style="font-size: 13px; line-height: 17px;">for details.&nbsp;</span></p>

<p>&nbsp;</p>

<p><i style="color: rgb(17, 17, 17); font-family: inherit; font-size: 14px; font-weight: bold; line-height: 16px;">How to configure</i><span style="color: rgb(17, 17, 17); font-family: inherit; font-size: 14px; font-weight: bold; line-height: 16px;">&nbsp; IdP Attributes</span></p>

<p>You configure the attribute name mappings in the config.php file, the <a class="wiki_link" href="#saml_attribute_settings" title="SAML attribute settings">SAML attribute settings</a> section).&nbsp; The default configuration is:</p>

<pre style="">
$config[&#39;saml_uid_attribute&#39;] = &#39;eduPersonTargetedID&#39;; // Attribute to uniquely identify the user 
$config[&#39;saml_email_attribute&#39;] = &#39;mail&#39;; // Attribute used for email address
$config[&#39;saml_name_attribute&#39;] = &#39;cn&#39;; // Attribute used to get the user&#39;s name
</pre>

<h4 id="3c693e6578616d706c653c2f693e"><i>Example</i></h4>

<p>A typical change you might want to consider is using &#39;eduPersonPrincipalName&#39; as the saml_uid_attribute in stead of eduPersonTargetedId, as it makes debugging easier.&nbsp; Please be aware you open your installation for the risk of session hijacking through rogue IdPs.&nbsp; Check with your login providers</p>

<pre style="">
$config[&#39;saml_uid_attribute&#39;] = &#39;eduPersonPrincipalName&#39;; // Attribute to uniquely identify the user
</pre>

<h4 id="3c693e6d6f726520696e666f726d6174696f6e206f6e206964702061747472696275746573203c2f693e3c62723e"><i>More information on IdP attributes </i></h4>

<p>You can check which attributes are received by your FileSender installation on the SimpleSAMLphp pages, in most cases that will be at https://<i>&lt;your-server&gt;</i>/simplesaml/module.php/core/authenticate.php . Login from that page to get a list of known attributes and their names and values.</p>

<p>&nbsp;</p>

<p>If your IdP doesn&#39;t send you any attribute uniquely identifying a user, you can add an authproc filter to the metadata of that Identity provider to locally generate an&nbsp;eduPersonTargetedID attribute. See <a href="http://simplesamlphp.org/docs/1.8/core:authproc_targetedid">http://simplesamlphp.org/docs/1.8/core:authproc_targetedid</a> for the details.</p>

<p>&nbsp;</p>

<h2 id="3._security_considerations">3. Security considerations</h2>

<p><span style="background-color: #ff0000;"><a name="Warning%20-%20Encryption"></a>Warning - Encryption</span></p>

<p>FileSender itself does <b>not</b> offer protection agains eavesdropping on the contents of uploaded/downloaded files.</p>

<p>Sensitive files can currently be protected in two ways:</p>

<ul>
	<li>in flight: protect files during upload/download using SSL.&nbsp; Ensure your FileSender webserver is only reachable over HTTPS.</li>
	<li>in rest: files stored on the FileSender server should be encrypted by the user <b>before</b> uploading them.</li>
</ul>

<p>&nbsp;</p>

<h2 id="4._customising_the_look_and_feel_of_your_filesender_installation">4. Customising the look and feel of your FileSender installation</h2>

<p>With FileSender version 1.5 you can customise more than with version 1.1.&nbsp;&nbsp; Customisations not mentioned in this section will require changing the code and will not survive upgrades or re-installs unless you keep a good backup of all your modifications.&nbsp; Config file directives you find in config/config.php and start with $config.&nbsp; Language file directives you find in the language files and start with $lang.</p>

<h3 id="4.1_banner">4.1 Banner</h3>

<p>A banner picture is automatically displayed at the top of all web pages.&nbsp;&nbsp;</p>

<h4 id="3c693e64656661756c742062616e6e65723c2f693e203c62723e"><i>default banner</i></h4>

<pre style="">
<span>&nbsp;&nbsp; &nbsp;</span>&lt;your_filesender_dir&gt;/www/banner.png</pre>

<h4 id="3c623e3c693e637573746f6d2062616e6e65723c2f693e3c2f623e203c62723e"><b><i>custom banner</i></b></h4>

<p>You override the default banner with a custom banner image named <b>banner.png</b> placed in the config directory.&nbsp; This image has to be in PNG format and should be sized to 800x60 pixels</p>

<pre style="">
<span>&nbsp;&nbsp; &nbsp;</span>&lt;your_filesender_dir&gt;/<span style="font-family: courier new,courier;">config/banner.png</span> 
</pre>

<h3 id="4.2_favicon">4.2 Favicon</h3>
The <b>favicon.ico</b> is found in &lt;your_filesender_dir&gt;/www/favicon.ico.&nbsp; It can currently not be customised in the same way as the banner can.&nbsp; This is functionality planned for version 2.0.

<h3 id="4.3_site_name">4.3 Site name</h3>
Use the <b>$config[&#39;site_name&#39;]</b> directive to specify a custom friendly name to your FileSender instance.&nbsp; The site_name is used at various places, amongst others in the default splash text, the help, the title bar and <span style="font-weight: normal;">Subject: line and text body of all email messages..&nbsp; Check <a class="wiki_link" href="#configuration_file_directives" title="Configuration file directives">Configuration file directives</a> for details.</span>

<p>&nbsp;</p>

<p id="c2a020c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f6e616d65275d"><span style="font-weight: normal;">&nbsp;</span></p>

<h3 id="4.4_landing_page_splash_text">4.4 Landing page splash text</h3>

<p>You can display a custom text on the main login page, also known as the landing page.&nbsp; This text is specified in the language file(s) active on your installation.&nbsp; Use <b>$lang[&quot;_SITE_SPLASHHEAD&quot;]</b> to specify a custom header for your splash text, and <b>$lang[&quot;_SITE_SPLASHTEXT&quot;]</b> to specify the splash text.</p>

<p>&nbsp;</p>

<p>Example:</p>

<pre style="">
// Login Splash text
$lang[&quot;_SITE_SPLASHHEAD&quot;] = &quot;&lt;p style=\&quot;text-align:center;\&quot;&gt;&quot; .htmlspecialchars($config[&#39;site_name&#39;]) .&quot;&lt;/p&gt;&quot;;
$lang[&quot;_SITE_SPLASHTEXT&quot;] = &quot;&lt;p style=\&quot;text-align:center;\&quot;&gt;&lt;i&gt;&lt;font size=\&quot;+1\&quot;&gt;share files of any size with anyone!&lt;/font&gt;&lt;/i&gt;&lt;br&gt;
Logon to upload your files or invite people to send you a file.&lt;br&gt;&lt;br&gt;&lt;br&gt;&lt;/p&gt;
&lt;p&gt;&lt;b&gt;Latest news:&lt;/b&gt;&lt;br&gt;14-11-2012:CloudStor was upgraded to a new software version, see &lt;a href=\&quot;http://www.ecampus.no/2012/11/14/cloudstor-oppgradert/\&quot;&gt;the eCampus blog article&lt;/a&gt; for details!  &lt;i&gt;Please report any problems to &lt;a href=\&quot;mailto:support@example.com\&quot;&gt;support@example.com&lt;/a&gt;.&lt;/i&gt; &lt;/p&gt;&quot;;

</pre>

<h3 id="4.5_various_ui_settings_toggles">4.5 Various UI settings toggles</h3>

<p>You can toggle the version number (<b>$config[&quot;versionNumber&quot;]</b>), total up/download counters (<b>$config[&#39;site_showStats&#39;]</b>) and the &quot;Welcome &lt;user&gt;&quot; friendly username (<b>$config[&#39;displayUserName&#39;]</b>).&nbsp; Check the <a class="wiki_link" href="#user_interface_(ui)_settings" title="User Interface (UI) Settings">User Interface (UI) Settings</a> section for details.</p>

<h3 id="4.6_date_formats">4.6 Date formats</h3>

<p>There are three places where date formats are configured.&nbsp; If you want to customise the date format make sure to change <i><b>all three</b></i> to ensure a consistent date format experience for your users.</p>

<ul>
	<li>config.php: <b>$config[&#39;datedisplayformat&#39;] </b>= &quot;d-m-Y&quot;; // used for date format in emails</li>
	<li>language file (e.g. en_AU.php):<b>$lang[&#39;datedisplayformat&#39;] </b>= &quot;d/m/Y&quot;; // Format for displaying date/time, use PHP date() format string syntax</li>
	<li>language file (e.g. en_AU.php): <b>$lang[&quot;_DP_dateFormat&quot;] </b>= &#39;dd/mm/yy&#39;;</li>
</ul>

<h3 id="4.7_terms_and_conditions_(aup)_controls">4.7 Terms and Conditions (AUP) controls</h3>

<p id="acceptable_use_policy_(aup)_settings">FileSender supports an AuP tick box.&nbsp; You can make clicking this tick box mandatory, you can configure it to be ticked by default or you can switch it off entirely.&nbsp; The AuP text is specified in the language file(s) active on your FileSender instance.&nbsp; Check the <a class="wiki_link" href="#acceptable_use_policy_(aup)_settings" title="Acceptable Use Policy (AUP) settings">Acceptable Use Policy (AUP) settings</a> section for $config options.</p>

<p>&nbsp;</p>

<p><b>&nbsp;</b></p>

<p><b>Example AUP text:</b></p>

<pre style="">
$lang[&quot;_AUPTERMS&quot;] = &quot;1. Your use of the UNINETT CloudStor Service (Service) is governed by your institution&#39;s IT regulations&lt;br&gt;&lt;br&gt;

2. The Service is governed by Norwegian law. You will only use this Service for purposes in accordance&nbsp; with Norwegian laws and regulations, in particular those laws and regulations pertaining to intellectual property rights (copyright)&lt;br&gt;&lt;br&gt;

3. You will refrain from any use that threatens the availability of the Service&lt;br&gt;&lt;br&gt;

4. The Service is provided \&quot;as-is\&quot; and delivered on a best-effort basis, any warranties and fitness for a particular purpose are disclaimed.&lt;br&gt;&quot;;
</pre>

<h3 id="4.8_custom_help_and_about">4.8 Custom help and about</h3>

<h4 id="6d6574686f6420313a206d6f64616c20696e6c696e6520706f707570202864656661756c74206d6574686f64293c62723e">method 1: Modal inline popup (default method)</h4>

<p>When a user clicks on &quot;help&quot; or on &quot;about&quot;, by default a window will pop up with text drawn from the relevant language file.&nbsp; The text is specified in <b>$lang[&quot;_HELP_TEXT&quot;] </b>and <b>$lang[&quot;_ABOUT_TEXT&quot;]</b>.&nbsp;&nbsp;</p>

<p>&nbsp;</p>

<p><b>NOTE:</b> the help and about windows are modal inline dialog windows, not popups that trigger popup blockers.</p>

<p>&nbsp;</p>

<p>If you want to customise the help and/or about text for this method, you need to create a local override language file and specify a customised <b>$lang[&quot;_HELP_TEXT&quot;] </b>and/or <b>$lang[&quot;_ABOUT_TEXT&quot;]</b> in this customised language file.&nbsp;&nbsp;</p>

<p>&nbsp;</p>

<p><b>NOTE: </b>when you change the help and about text, you probably will want to limit the available language files to only those containing your customised help and about!</p>

<h4 id="6d6574686f6420323a206c696e6b20746f207370656369666963202865787465726e616c292068746d6c207061676573">method 2: Link to specific (external) HTML pages</h4>

<p>Like with previous versions you can still simply link a help and/or about page.&nbsp; <span style="background-color: rgb(255, 255, 255);">Check the&nbsp; <a class="wiki_link" href="#support_links" title="Support links">Support links</a> for details.</span></p>

<h3 id="4.9_custom_logout_url">4.9 Custom logout URL</h3>

<p><span style="background-color: rgb(255, 255, 255);">The <span style="font-family: courier new,courier;">$config[&#39;site_logouturl&#39;]</span> setting (in the <a class="wiki_link" href="#site_url_settings" title="Site URL settings">Site URL settings</a> section) can be used to point to a custom page to return to after the authenticated user has logged out. Note that the actual use of this page also depends on the Identity Provider and/or Federation of the authenticated user, not all of them redirect back to the requested logout page.</span></p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h3 id="4.10_email_customisation">4.10 Email customisation</h3>

<p>You can customise all the emails sent out by FileSender.&nbsp; The email templates are configured in the configuration file.</p>

<p id="email_template_variables">check the <a class="wiki_link" href="#email_related_configuration_directives" title="Email related configuration directives">Email related configuration directives</a> and the <a class="wiki_link" href="#email_template_variables" title="Email template variables">Email template variables</a> section for details.</p>

<h3 id="4.11_customising_simplesamlphp">4.11 Customising SimpleSAMLphp</h3>

<p id="customising_simplesamlphp">In case you use the local SimpleSAMLphp &#39;Identity Provider&#39; selection page you can have a look at the <a href="https://www.assembla.com/spaces/file_sender/documents/am2bkchOyr4jeEeJe5cbCb/download/am2bkchOyr4jeEeJe5cbCb">themefilesender module</a>. This module will give SimpleSAMLphp the same look&amp;feel as FileSender.</p>

<h3 id="5._dealing_with_language_files_and_localisation">5. Dealing with language files and localisation</h3>

<p>As of version 1.5, FileSender supports multiple languages.&nbsp; All web-UI texts are taken from the language file matching the browser&#39;s indicated language preference. &nbsp;&nbsp;</p>

<p>&nbsp;</p>

<ul>
	<li>out-of-the-box (distribution-provided) the following language files are included:&nbsp; <b><i>Czech, Croatian, Dutch, English (Australian), French, German, Hungarian, Italian, Norwegian (Bokm&aring;l), Serbian, Slovenian</i> and <i>Spanish.</i></b>&nbsp;</li>
	<li><b>NOTE: <i>do not change these distribution-provided language files</i>!</b>&nbsp; This will give you a head-ache when upgrading.&nbsp; Read section 5.2 on customising language tags.</li>
	<li>the filesender-core team maintains Dutch, English and Norwegian, the other files are maintained by contributors<b><i>.</i></b></li>
	<li>the distribution-provided language files are located in the directory <i><b>&lt;filesender-root&gt;/languages,</b></i> one file per language<i><b>.</b></i></li>
	<li>if a browser language preference is sent for which no language file is present, the default language file is selected<b>.</b></li>
</ul>

<h3 id="5.1_internationalisation_and_character_encoding">5.1 Internationalisation and character encoding</h3>

<p>FileSender encodes all input and output text in UTF-8.&nbsp; There should be no problems encoding any characters or languages.</p>

<h3 id="5.2_technical_details_about_the_language_file_mechanism">5.2 Technical details about the language file mechanism</h3>

<p>The language directory contains&nbsp; contains the distribution files for the various language definitions as well as a file &quot;<i>locale.php</i>&quot; controlling which language files can be served up. &nbsp; Definitions and mappings in these files can be over-ruled by a corresponding file (with the same name) in the main ./config directory.&nbsp;&nbsp; Local customisations should be done in these files in the ./config directory. See <a href="http://www.assembla.com/spaces/filesendercontrib/">http://www.assembla.com/spaces/filesendercontrib/</a> on how to report errors in the translations or contribute new translations.</p>
&nbsp;

<p>The naming scheme of the language files in this directory and mapping of browser tags to language files is based on Best Current Practices as defined by <a href="http://tools.ietf.org/html/bcp47">IETF BCP 47: Tags for Identifying Languages</a> and related ICU/ISO guidelines.</p>

<h4 id="66696c65206e616d696e673c62723e">File naming</h4>

<p>&lt;language&gt;_&lt;COUNTRY&gt;.php<br />
<br />
&lt;language&gt; is the shortest two/three letter ISO 639 language code in lowercase<br />
&lt;COUNTRY&gt; is the ISO 3166-1 country/region/territory code in UPPERcase<br />
<br />
Use of &quot;_&quot; (underscore) in filenames follows the convention for defining &#39;locales&#39; on modern Linux/Unix systems and defined/allowed by the related Unicode/ICU definitions, see <a href="http://www.unicode.org/reports/tr35/#Unicode_Language_and_Locale_Identifiers">http://www.unicode.org/reports/tr35/#Unicode_Language_and_Locale_Identifiers</a> and<a href="http://userguide.icu-project.org/locale"> http://userguide.icu-project.org/locale</a>).</p>

<h4 id="browser_tags_mapping">Browser tags mapping</h4>

<p>Mapping from browser language tags to language files is done in locale.php. Note that browser tags for language preference use the &quot;-&quot; hyphen as defined in <a href="http://tools.ietf.org/html/bcp47">IETF BCP 47:&nbsp; Tags for Identifying Languages</a>. Tags specified in locale.php should be all lowercase.</p>

<h3 id="5.3_customising_languages">5.3 Customising languages</h3>

<p>You can easily adapt relevant language labels to your local needs in an upgrade-friendly way, for example to localise the splash screen text, the AUP text, the help text, etc.&nbsp; When you adapt certain language labels you will probably want to limit the available languages on your site to only those that you in fact translated.&nbsp; This is also easily done.</p>

<p>&nbsp;</p>

<p><span style="font-weight: normal;"><span style="background-color: rgb(255, 0, 0);"><b>Warning:</b></span> the texts specified in a language file are sent to the user&#39;s browser as-is.&nbsp; Unfiltered.&nbsp; Make sure you run your customised language files through a HTML validator!&nbsp; </span></p>

<h4 id="limiting_what_languages_your_installation_supports">Limiting what languages your installation supports</h4>

<p>Copy language/locale.php to your ./config/ directory and edit it to support only the languages you want.&nbsp; For example, UNINETT currently supports two languages: English and Norwegian - Bokm&aring;l:</p>

<pre style="">
root@cloudstor:/usr/local/filesender/filesender/config# cat locale.php  
&lt;?php

//The below array maps locales provided by the browser to your local translation.
//Put your custom translated file in the &quot;config&quot; subdirectory.
//Add relevant entries for browser locales here, and your translation will automagically be recognized and used....

// Uninett supports English and Norwegian - Bokm&aring;l.

$locales  =  array(
<span>&nbsp;&nbsp; &nbsp;</span>&quot;en&quot;=&gt;  &quot;en_AU.php&quot;,
<span>&nbsp;&nbsp; &nbsp;</span>&quot;en-au&quot; =&gt;  &quot;en_AU.php&quot;,
<span><span>&nbsp;&nbsp; &nbsp;</span></span>&quot;no&quot; =&gt; &quot;no_NO.php&quot;,
<span>&nbsp;&nbsp; &nbsp;</span>&quot;nb&quot; =&gt; &quot;no_NO.php&quot;,
<span>&nbsp;&nbsp; &nbsp;</span>&quot;nb-no&quot; =&gt; &quot;no_NO.php&quot;,
);
?&gt;

</pre>

<h4 id="customising_certain_language_texts">Customising certain language texts</h4>

<p>All language texts come in the form of a language label $lang[&quot;&lt;label&gt;&quot;] = &quot;text to be displayed&quot;.</p>

<p>&nbsp;</p>

<p>You probably do not want to change all language labels unless you&#39;d like to add a new language.&nbsp; To customise certain language labels, create a file in your .config/ directory <i><b>with exactly the same name as the language file you&#39;d like to over-ride</b></i> and put the language labels + texts you&#39;d like to be used in that file.&nbsp; Files in the ./config directory are NOT overwritten when upgrading.</p>

<p>&nbsp;</p>

<p>As an example here&#39;s the over-ride file UNINETT uses for its FileSender production service:</p>

<pre style="">
root@cloudstor:/var/www/filesender/config# more en_AU.php
&lt;?php

/* ---------------------------------
 * Overrides to en_AU Language File
 * ---------------------------------
 */

$lang[&quot;_LOGON&quot;] = &#39;Logon with &lt;br&gt;&lt;br&gt; &lt;img src=&quot;https://cloudstor.uninett.no/feide_logo_72x40.png&quot;&gt;&#39;;

$lang[&quot;_ERROR_CONTACT_ADMIN&quot;] = &quot;There has been an error - please contact support@example.com.&quot;;	
$lang[&quot;_ERROR_INCORRECT_FILE_SIZE&quot;] = &quot;There has been a problem uploading your file. &lt;br /&gt;The file size on the server d
oes not match your original file. &lt;br /&gt;&lt;br /&gt;Please contact support@example.com.&quot;;
$lang[&quot;_DISK_SPACE_ERROR&quot;] = &quot;There is not enough drive space on this service. This should not happen.  Please contact s
upport@ecampus.no and/or upload a smaller file.&quot;;
$lang[&quot;_ERROR_ATTRIBUTES&quot;] = &quot;Your institution is not providing the required identity attributes to Feide. Please contac
t support@example.com&quot;;
// vouchers
$lang[&quot;_SEND_NEW_VOUCHER&quot;] = &quot;A Voucher allows someone to send you a file.&lt;br /&gt;
To create a voucher, enter an email address then select Send Voucher.&lt;br /&gt;
An email will be sent to the recipient with a link to use the Voucher.&quot;;

// Login Splash text
$lang[&quot;_SITE_SPLASHHEAD&quot;] = &quot;&lt;p style=\&quot;text-align:center;\&quot;&gt;&quot; . htmlspecialchars($config[&#39;site_name&#39;]) .&quot;&lt;/p&gt;&quot;;
$lang[&quot;_SITE_SPLASHTEXT&quot;] = &quot;&lt;p style=\&quot;text-align:center;\&quot;&gt;&lt;i&gt;&lt;font size=\&quot;+1\&quot;&gt;share files of any size with anyone!&lt;/
font&gt;&lt;/i&gt;&lt;br&gt;
Logon to upload your files or invite people to send you a file.&lt;br&gt;&lt;br&gt;&lt;br&gt;&lt;/p&gt;&quot;;
// &lt;p&gt;&lt;b&gt;Latest news:&lt;/b&gt;&lt;br&gt;14-11-2012:CloudStor was upgraded to a new software version, see &lt;a href=\&quot;http://www.ecamp
us.no/2012/11/14/cloudstor-oppgradert/\&quot;&gt;the eCampus blog article&lt;/a&gt; for details!  &lt;i&gt;Please report any problems to &lt;a 
href=\&quot;mailto:support@example.com\&quot;&gt;support@example.com&lt;/a&gt;.&lt;/i&gt; &lt;/p&gt;&quot;;

// site about
$lang[&quot;_ABOUT_TEXT&quot;] = &#39; &lt;div align=&quot;left&quot; style=&quot;padding:5px&quot;&gt;&#39;. htmlspecialchars($config[&#39;site_name&#39;]) .&#39; is an instal
lation of FileSender (&lt;a rel=&quot;nofollow&quot; href=&quot;http://www.filesender.org/&quot; target=&quot;_blank&quot;&gt;www.filesender.org&lt;/a&gt;), which
 is developed to the requirements of the higher education and research community.&lt;/div&gt;&#39;;

// site AUP terms
$lang[&quot;_AUPTERMS&quot;] = &quot;1. Your use of the UNINETT CloudStor Service (Service) is governed by your institution&#39;s IT regula
tions&lt;br&gt;&lt;br&gt;

2. The Service is governed by Norwegian law. You will only use this Service for purposes in accordance  with Norwegian l
aws and regulations, in particular those laws and regulations pertaining to intellectual property rights (copyright)&lt;br&gt;
&lt;br&gt;

3. You will refrain from any use that threatens the availability of the Service&lt;br&gt;&lt;br&gt;

4. The Service is provided \&quot;as-is\&quot; and delivered on a best-effort basis, any warranties and fitness for a particular p
urpose are disclaimed.&lt;br&gt;&quot;;

?&gt;</pre>

<p>&nbsp;</p>

<h2 id="6._technical_details_about_pause_-_resume_functionality">6. Technical details about pause - resume functionality</h2>

<p>Placeholder to document additional technical details about pause - resume functionality.&nbsp; For now we&#39;ll suffice to say it works based on the file name and the file size, and that it only works with the HTML5 uploads.&nbsp;</p>

<h2 id="7._configuration_file_directives">7. Configuration file directives</h2>

<p>All configuration of FileSender is done by editing the configuration file:</p>

<p style="padding-left: 30px;"><span style="font-family: courier new,courier;">config/config.php</span></p>

<p>&nbsp;</p>

<p>This file is actual PHP code so be careful to adhere to the PHP syntax:</p>

<ul>
	<li>keep the closing ; at the end of a $config specification</li>
	<li>enclose string/text values in single or double quotes</li>
	<li>boolean values can be specified as true or false (without quotes)</li>
	<li>remarks/comments start with // or are enclosed in /* ... */</li>
	<li>make sure you don&#39;t have any extra characters after the ?&gt; at the end of the php code</li>
</ul>

<p>&nbsp;</p>

<p>This section describes all the available configuration settings in config.php.</p>

<h3 id="general_settings">General settings</h3>

<h4 id="c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2761646d696e275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;admin&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description:</b></i> list of UIDs of administrators, separated by comma. Administrators have access to the Administrator Interface. A UID is the value of the attribute defined in <i>$config[&#39;saml_uid_attribute&#39;]</i> in the <a class="wiki_link" href="#saml_attribute_settings" title="SAML attribute settings">SAML attribute settings</a> section.</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> none</p>

<p style="padding-left: 60px;"><b><i>example</i></b>: &#39;31a7bf626eb4fa2d425f611c0490940e71e1c42c&#39; <i>(with eduPersonTargetedID as UID attribute)</i></p>

<p style="padding-left: 60px;"><b><i>example:</i></b> &#39;john.doe@mysite.dom&#39; <i>(with mail as UID attribute)</i></p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2761646d696e656d61696c275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;adminEmail&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: Email address(es, separated by ,) to receive administrative messages (low disk space warning)</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: none</p>

<h4 id="24636f6e6669675b2764656661756c745f74696d657a6f6e65275d" style="padding-left: 30px;">$config[&#39;Default_TimeZone&#39;]</h4>

<p style="padding-left: 60px;"><span style="color: #ff0000;"><span style="color: #000000;"><i><b>description:</b></i> Set this to your local timezone according to timezone specifications in <a href="http://php.net/manual/en/timezones.php" target="_blank">http://php.net/manual/en/timezones.php </a></span></span></p>

<p style="padding-left: 60px;"><i><b>default:</b></i> &#39;Australia/Sydney&#39;</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: &#39;Europe/Berlin&#39;</p>

<h4 id="3c626c6f636b71756f7465207374796c653d22223e3c68343e3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e24636f6e6669675b2764656661756c745f6c616e6775616765275d3c2f7370616e3e3c2f68343e3c2f626c6f636b71756f74653e">&nbsp;</h4>

<blockquote style="">
<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e24636f6e6669675b2764656661756c745f6c616e6775616765275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">$config[&#39;Default_Language&#39;]</span></h4>
</blockquote>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><span style="color: rgb(255, 0, 0);"><span style="color: rgb(0, 0, 0);"><i><b>description:</b></i> S</span></span>et the default language to use when the user&#39;s browser wants a language that&#39;s not available. &nbsp; For available languages see the language directory on your FileSender installation.&nbsp; In case you make a typo here, there is a last resort hard-coded fallback to en_AU.</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>default:</b></i>&nbsp;&#39;en_AU&#39;</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>example</b></i>: &#39;no_NO&#39;</span></p>

<p>&nbsp;</p>

<h4 id="c2a020c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f6e616d65275d">&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_name&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: Friendly name used for your FileSender instance. Used on the main login page, the title bar, the help and in emails.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: &#39;FileSender&#39;</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: &#39;AARNet CloudStor&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a03c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223ec2a02024636f6e6669675b22736974655f73706c61736874657874225d3c2f7370616e3e">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="background-color: rgb(255, 255, 255);">&nbsp; $config[&quot;site_splashtext&quot;]</span></h4>

<blockquote style="">
<blockquote>
<blockquote><b><font>depcrecated.&nbsp; </font></b><font>You now set this in the language files using </font><font>$lang[&quot;_SITE_SPLASHHEAD&quot;] and&nbsp;</font><font>$lang[&quot;_SITE_SPLASHTEXT&quot;].</font></blockquote>
</blockquote>
</blockquote>

<p>&nbsp;</p>

<h3 id="user_interface_(ui)_settings">User Interface (UI) settings</h3>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a03c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e2024636f6e6669675b2764617465646973706c6179666f726d6174275d3c2f7370616e3e">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<span style="background-color: rgb(255, 255, 255);"> $config[&#39;datedisplayformat&#39;]</span></h4>

<blockquote style="">
<blockquote><span style="background-color: rgb(255, 255, 255);"><span style="background-color: rgb(255, 255, 255);"><i><b>description</b></i>: Format for displaying date/time. Use the <a href="http://php.net/manual/en/function.date.php">PHP date () format string syntax</a>. </span>&nbsp;</span></blockquote>
</blockquote>

<blockquote style="">
<blockquote><span style="background-color: rgb(255, 255, 255);"><i><b>1.5 default</b></i>:&nbsp;&quot;d-m-Y</span><span style="background-color: rgb(255, 255, 255);">&quot;</span></blockquote>
</blockquote>

<blockquote style="">
<blockquote><span style="background-color: rgb(255, 255, 255);"><span style="background-color: rgb(255, 255, 255);"><i><b>1.5 example</b></i>:&nbsp;&quot;d-m-Y&quot;</span>&nbsp; </span><span style="background-color: rgb(255, 255, 255);"> </span></blockquote>
</blockquote>

<blockquote style="">
<blockquote><span style="background-color: rgb(255, 153, 0);"><span style="background-color: rgb(255, 255, 255);"><b>Note:</b> the semantics of this directive changed with version 1.5.</span></span></blockquote>
</blockquote>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2276657273696f6e6e756d626572225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;versionNumber&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: show FileSender version number in the upper right corner</p>

<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f73686f777374617473275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_showStats&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description</i></b>: show upload/download statistics up in the upper right corner.</p>

<p style="padding-left: 60px;"><b><i>default: </i></b>false</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27646973706c6179757365726e616d65275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;displayUserName&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: show &#39;Welcome user&#39; in the upper left corner. The friendly name of the authenticated user is taken from the SAML attribute as specified by $config[&#39;saml_name_attribute&#39;] or will be &#39;Guest&#39; for users using a voucher.</p>

<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>

<h3 id="debug_settings">Debug settings</h3>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b226465627567225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;debug&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description:</b></i> if set to true server side logging will be more verbose and the UI wil display extra technical information of what&#39;s happening. This setting also increases the PHP loglevel.</p>

<p style="padding-left: 60px;"><b><i>values:</i></b> true/false</p>

<p style="padding-left: 60px;"><b><i>default:</i></b> false <i>(true in beta releases)</i></p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27646e736c6f6f6b7570275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;dnslookup&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: if set to true the logging includes a reverse DNS lookup of the originating IP-address of the user. On really busy servers this may impact performance.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>

<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b22636c69656e745f73706563696669635f6c6f6767696e67225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;client_specific_logging&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: turn on/off client specific logging. If set to true the client (Flash UI) will send debug information to the server which will be logged in separate user-specific files in the &#39;log_location&#39; directory.</p>

<p style="padding-left: 60px;"><i><b>remark</b></i>: turning on client specific logging will impact performance</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: false <i>(true in beta releases)</i></p>

<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b22636c69656e745f73706563696669635f6c6f6767696e675f75696473225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;client_specific_logging_uids&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: A list of UIDs, separated by comma. When client specfiic logging is turned on the logging will be restricted to the UIDs in this list. The value &quot;&quot; (default) means &#39;log all clients&#39;. A UID can be the UID of an authenticated user (as specified by the saml_uid_attribute setting below) or a voucher ID.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: &quot;&quot;</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: &#39;31a7bf626eb4fa2d425f611c0490940e71e1c42c, 6B30BA68-B883-8565-36B5-73CDBE0C672C&#39;</p>

<h3 id="saml_attribute_settings">SAML attribute settings</h3>

<h4 id="3c623ec2a0c2a0c2a0c2a0c2a0c2a0203c2f623e3c623e24636f6e6669675b2773616d6c5f656d61696c5f617474726962757465275d3c62723e3c2f623e"><b>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; </b><b>$config[&#39;saml_email_attribute&#39;]</b></h4>

<p style="padding-left: 60px;"><i><b>description:</b></i> . attribute used as From: email address of the authenticated user</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> mail</p>

<h4 id="24636f6e6669675b2773616d6c5f6e616d655f617474726962757465275d" style="padding-left: 30px;">$config[&#39;saml_name_attribute&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description: </b></i>attribute used to get the friendly name of the authenticated user. If this attribute does not exist or has no value (?) then FileSender will use the first part of the email attribute before the @ as the &#39;name_attribute&#39; value.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: cn</p>

<h4 id="24636f6e6669675b2773616d6c5f7569645f617474726962757465275d" style="padding-left: 30px;">$config[&#39;saml_uid_attribute&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description: </b></i>attribute to uniquely identify the user.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: eduPersonTargetedID</p>

<h3 id="acceptable_use_policy_(aup)_settings">Acceptable Use Policy (AUP) settings</h3>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b226175705f64656661756c74225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;AuP_default&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: when set to false (the default) the user has to explicitly tick the &#39;I accept the AuP&#39; checkbox before uploading a file. When set to true the checkbox will already be ticked.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: false</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b22617570225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;AuP&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: a text box with an AuP is displayed</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b226175705f6c6162656c225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;AuP_label&quot;]</h4>

<p style="padding-left: 60px;"><i><b><b><font>deprecated.&nbsp; </font></b><font>You now set this in the language files using&nbsp; $lang[&quot;_ACCEPTTOC&quot;]</font></b></i></p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b226175705f7465726d73225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;AuP_terms&quot;]</h4>

<blockquote style="">
<blockquote>
<blockquote><span style=""><i><b><b><font>deprecated.&nbsp; </font></b><font>You now set this in the language files using&nbsp; </font></b></i>$lang[&quot;_AUPTERMS&quot;]</span></blockquote>
</blockquote>
</blockquote>

<p style="padding-left: 60px;"><i><b>description</b></i>: text to show in the AuP box containing the terms and conditions the user has to accept before using the service.</p>
&nbsp;

<h3 id="server_settings">Server settings</h3>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2764656661756c745f6461797376616c6964275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;default_daysvalid&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: Maximum number of days before a file or a voucher is expired</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: 20</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2762616e5f657874656e73696f6e275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;ban_extension&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: Possibly dangerous file extensions that are disallowed</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: = &#39;exe,bat&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b226d61785f656d61696c5f726563697069656e7473225d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&quot;max_email_recipients&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: maximum email addresses allowed to send at once for voucher or file sending, a value of 0 allows unlimited emails.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: 100</p>

<h4 id="24636f6e6669675b276d61785f666c6173685f75706c6f61645f73697a65275d" style="padding-left: 30px;">$config[&#39;max_flash_upload_size&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: the maximum files size when uploading with Flash (browser with no HTML5 support), specify in number of bytes.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: &#39;2147483648&#39; (2 GigaByte)</p>

<p style="padding-left: 60px;"><i><b>remarks</b></i>: the value specified will be compared with the PHP settings <span style="font-family: courier new,courier;">post_max_size</span> and <span style="font-family: courier new,courier;">upload_max_filesize.</span> The minimum of these values will be used as actual maximum upload size for Flash uploads</p>

<blockquote style="">
<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e24636f6e6669675b276d61785f68746d6c355f75706c6f61645f73697a65275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">$config[&#39;max_html5_upload_size&#39;]</span></h4>
</blockquote>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>description</b></i>: the maximum file size when uploading with HTML5, specify in number of bytes</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><b><i>availability:</i></b> version 1.5</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><b><i>default:</i></b> &#39;107374182400&#39; (100 GigaByte)</span></p>

<blockquote style="">
<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e24636f6e6669675b2275706c6f61645f6368756e6b5f73697a65225d20c2a03d202732303030303030273b2f2f3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">$config[&quot;upload_chunk_size&quot;] &nbsp;= &#39;2000000&#39;;//</span></h4>
</blockquote>

<blockquote style="">
<blockquote style="">
<blockquote style="">
<div><span style="background-color: rgb(255, 255, 255);"><b>description:</b>&nbsp;<span style="font-style: normal;">uploads using HTML5 happen one chunk at a time. &nbsp;This directive specifies how big each chunk is. &nbsp;When using long latency paths and/or when sending very large files an increased chunk size might lead to an improved transfer speed experienced.</span></span></div>

<div><span style="background-color: rgb(255, 255, 255);"><b>availability:</b> <span style="font-style: normal;">version 1.5</span></span></div>

<div><span style="background-color: rgb(255, 255, 255);"><span style="font-style: normal;">default:&nbsp;</span><span style="font-style: normal;">&#39;2000000&#39;;</span></span></div>
</blockquote>
</blockquote>
</blockquote>

<blockquote style="">
<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e24636f6e6669675b276d61785f67656172735f75706c6f61645f73697a65275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">$config[&#39;max_gears_upload_size&#39;]</span></h4>
</blockquote>

<blockquote style="">
<blockquote>
<blockquote><span style="background-color: rgb(255, 255, 255);">Deprecated in 1.5 </span></blockquote>
</blockquote>
</blockquote>

<p>&nbsp;</p>

<h3 id="advanced_server_settings">Advanced server settings</h3>

<p>This section contains settings that under normal circumstances don&#39;t need changing. <b>Do not change them unless you have a very good reason.</b></p>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <b>$config[&#39;postgresdateformat&#39;]</b></p>

<p style="padding-left: 60px;"><b><i>Deprecated in version 1.5</i> </b></p>

<p style="padding-left: 60px;"><b>description:</b> Date/Time format for PostgreSQL, use<a href="http://www.php.net/manual/en/function.date.php" target="_blank"> PHP date format specifier syntax</a></p>

<p style="padding-left: 60px;"><b>default:</b> &#39;Y-m-d H:i:sP&#39;</p>

<h4 id="24636f6e6669675b2263726c66225d" style="padding-left: 30px;">$config[&quot;crlf&quot;]</h4>

<p style="padding-left: 60px;"><b>description:</b> controls whether lines in emails sent out by FileSender are terminated with CRLF or with LF.&nbsp; What makes sense depends on your PHP and email setup.&nbsp; Linux/Unix hosts will need &quot;\n&quot;.&nbsp; Possible values are &quot;\n&quot; or &quot;\r\n&quot;. Keep this at the default unless you have some weird setup.</p>

<p style="padding-left: 60px;"><b>default: &#39;</b>\n&#39;</p>

<h4 id="24636f6e6669675b27766f75636865727265676578275d" style="padding-left: 30px;">$config[&#39;voucherRegEx&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description: </b></i>When someone uses a voucher, the voucher is in the format of 8 numbers/letters followed by - 4numlet-4numlet-4-12numlet unique Id that&#39;s standard flash and windows GUID (generated unique id).&nbsp; The regex is to make sure that a presented voucherId adheres to this GUID format.&nbsp; Anything else will result in a &#39;bugger off&#39;.&nbsp; Also makes sure that generated vouchers are constructed correctly.&nbsp; Reason for putting it in config is because the PhP uniqueId is a different format so you&#39;d need a different RegEx.&nbsp; So this is future proofing the vouchers<b>.</b></p>

<p style="padding-left: 60px;"><i><b>default:</b></i> &#39;[a-zA-Z0-9]{8}-[a-zA-Z0-9]{4}-[a-zA-Z0-9]{4}-[a-zA-Z0-9]{4}-[a-zA-Z0-9]{12}&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27766f75636865727569646c656e677468275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;voucherUIDLength&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description: </b>See above.&nbsp; Make sure no-one tries anything &#39;interesting&#39; with vouchers<b>.</b></i></p>

<p style="padding-left: 60px;"><i><b>default:</b></i> <i>&#39;36&#39;</i></p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27656d61696c7265676578275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;emailRegEx&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description:</b></i> Regular expression to check the syntax of email-adressess</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: &#39;[a-z0-9!#$%&amp;&#39;*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&amp;&#39;*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?&#39;</p>

<h3 id="site_url_settings">Site URL settings</h3>

<p>These settings define the basic URL&#39;s FileSender will use. The configuration file will in general automatically define them based on the server name of the webserver which is automatically set in the global PHP variable <span style="font-family: courier new,courier;">$_SERVER[&#39;SERVER_NAME&#39;] </span>The following piece of code in config.php handles the automatic configuration:</p>

<pre style="">
if ( isset($_SERVER[&#39;SERVER_NAME&#39;]) ) {
$prot =&nbsp; isset($_SERVER[&#39;HTTPS&#39;]) ? &#39;https://&#39; : &#39;http://&#39;;
$config[&#39;site_url&#39;] = $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;/filesender/&#39;; // URL to Filesender
$config[&#39;site_simplesamlurl&#39;] =&nbsp; $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;/simplesaml/&#39;;
$config[&#39;site_authenticationSource&#39;] =&quot;default-sp&quot;;
$config[&#39;site_logouturl&#39;] = $config[&#39;site_url&#39;] . &#39;logout.php&#39;;
$config[&#39;site_downloadurl&#39;] = $config[&#39;site_url&#39;] . &#39;files/&#39;; // * Deprecated *
<span style="color: #008000;">}</span></pre>

<p>Settings within this block can be modified as long as you keep those settings within the block.</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a0202470726f74">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $prot</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: variable containing the automatically determined current protocol (http or https) of the connection</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: isset($_SERVER[&#39;HTTPS&#39;]) ? &#39;https://&#39; : &#39;http://&#39;</p>

<p style="padding-left: 60px;"><i><b>remark</b></i>: do not change</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f75726c275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_url&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: URL on your webserver where the FileSender instance can be reached</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;/filesender/&#39;</p>

<p style="padding-left: 60px;"><i><b>remarks</b></i>: URL is automatically generated based on the SERVER_NAME and a manually specified local path (&#39;/filesender/&#39; by default). If you have your FileSender running on another URL you can change the local path part. At a minimum, this part should contain &#39;/&#39; which means FileSender is running at the root of your webserver.</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;/&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f73696d706c6573616d6c75726c275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_simplesamlurl&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: URL on your webserver where the SimpleSAMLphp instance can be reached</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: $prot . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;/simplesaml/&#39;</p>

<p style="padding-left: 60px;"><i><b>remark</b></i>: URL is automatically generated based on the SERVER_NAME and a manually specified local path (&#39;/simplesaml/&#39; by default). If you have your SimpleSAMLphp instance running on another URL you can change the local path part. If you have your FileSender instance reachable with http (no forced SSL) but want to force authentication via simplesaml to use SSL change the $prot part to &#39;https://&#39; (including quotes).</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: &#39;https://&#39; . $_SERVER[&#39;SERVER_NAME&#39;] . &#39;/simplesamlphp/</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f61757468656e7469636174696f6e736f75726365275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_authenticationSource&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: authentication source on your SimpleSAMLphp instance to use</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: &quot;default-sp&quot;</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: &quot;example-userpass&quot; ; <i>Point FileSender to the &#39;example-userpass&#39; authentication source defined in the SimpleSAMLphp authsources.php</i></p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f6c6f676f757475726c275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_logouturl&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: URL to go to when the user logs out (will be used by the IdP to redirect to)</p>

<p style="padding-left: 60px;"><i><b>remark</b></i>: should be an absolute URL including protocol and host, by default this will be the URL part as generated in <span style="font-family: courier new,courier;">$config[&#39;site_url&#39;]</span> plus a local path part (default &#39;logout.php&#39;)</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: $config[&#39;site_url&#39;] . &#39;logout.php&#39;</p>

<p style="padding-left: 60px;"><i><b>example</b></i>: $config[&#39;site_url&#39;] . &#39;custom-logout.php&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f646f776e6c6f616475726c275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_downloadurl&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: in beta release before 0.1.16 this was used for download URLs. Deperecated as of beta 0.1.16</p>

<p style="padding-left: 60px;"><i><b>status</b></i>: Obsoleted</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: $config[&#39;site_url&#39;] . &#39;files/&#39;</p>

<p>The following setting is outside the <span style="font-family: courier new,courier;">if {}</span> block but is related to the server URL settings:</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27666f72636573736c275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;forceSSL&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: when set to true (default, recommended) FileSender will force connections to always use SSL</p>

<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>

<h3 id="support_links">Support links</h3>

<p>These settings control what happens when a user clicks on the &quot;Help&quot; or &quot;About&quot; buttons.</p>

<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223ec2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2761626f757475726c275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;aboutURL&#39;]</span></h4>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>description</b></i>: if &quot;&quot;, a modal inline popup dialogue is shown with the contents of $lang[&quot;_ABOUT_TEXT&quot;].&nbsp; Alternatively a URL can be used to point to a specific (local or external) HTML page.</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>default</b></i>: &quot;&quot;</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>example</b></i>: &quot;http://support.example.org/about-filesender.aspx&quot;</span></p>

<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223ec2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2768656c7075726c275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;helpURL&#39;]</span></h4>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>description</b></i>: </span><span style="background-color: rgb(255, 255, 255);">if &quot;&quot;, a modal inline popup dialogue is shown with the contents of $lang[&quot;_HELP_TEXT&quot;].&nbsp; Alternatively a URL can be used to point to a specific (local or external) HTML page.</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>default</b></i>: &quot;&quot;</span></p>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>example</b></i>: &quot;http://support.example.org/help-for-filesender.aspx&quot;</span></p>

<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223ec2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27676561727375726c275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;gearsURL&#39;]</span></h4>

<p style="padding-left: 60px;"><span style="background-color: rgb(255, 255, 255);"><i><b>deprecated as of version 1.5.&nbsp; The information is now contained in the default </b></i></span><span style="background-color: rgb(255, 255, 255);">$lang[&quot;_HELP_TEXT&quot;].</span></p>

<h3 id="file_and_directory_location_settings">File and directory location settings</h3>

<p>These settings define the directory locations where various files can be found or stored. Directory values are absolute filesystem paths on your server and should be readable and writable (except for the site_simplesamllocation) for the webserver user.</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f66696c6573746f7265275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_filestore&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description:</b></i> the directory where all uploaded files are stored</p>

<p style="padding-left: 60px;"><i><b>remarks</b></i>: this directory should have ample disk space and can fysically be stored on a NAS or other big storage device.</p>

<p style="padding-left: 60px;"><b><i>default:</i></b> &#39;/usr/share/filesender/files/&#39;</p>

<p style="padding-left: 60px;"><b><i>example:</i></b> &#39;/data/filesender/files/&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f74656d705f66696c6573746f7265275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_temp_filestore&#39;]</h4>

<p><span>&nbsp;&nbsp; &nbsp;</span><span>&nbsp;&nbsp; &nbsp;</span><span>&nbsp;&nbsp;&nbsp; </span>Deprecated in version 1.5</p>

<p style="padding-left: 60px;"><strike><i><b>description</b></i>: the directory used to store (partial) Gears uploads. After completion of the Gears upload the temporary file will be moved to the &#39;site_filestore&#39;</strike></p>
<strike> </strike>

<p style="padding-left: 60px;"><strike><i><b>remarks</b></i>: this directory is not used for Flash uploads. You might want to do a regular check on this directory to remove old partial but never finished uploads. It is advised to keep this directory on the same partition as the actual &#39;site_filestore&#39; so moving the temporary file will be instantaneous.</strike></p>
<strike> </strike>

<p style="padding-left: 60px;"><strike><i><b>default</b></i>: = &#39;/usr/share/filesender/tmp/&#39;</strike></p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b27736974655f73696d706c6573616d6c6c6f636174696f6e275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;site_simplesamllocation&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: directory where the SimpleSAMLphp software can be found. Needed to find the required SImpleSAMLphp libraries.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: = &#39;/usr/share/simplesamlphp/&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b276c6f675f6c6f636174696f6e275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;log_location&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: directory to keep FileSender specific logfiles.</p>

<p style="padding-left: 60px;"><i><b>remarks</b></i>: logfiles are created per day (and per user/voucheruid for client_specific_logging). FileSender has no internal mechanism to clean up old logs, you might want to do a (automated) regular cleanup of this directory.</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: &#39;/usr/share/filesender/log/&#39;</p>

<h3 id="database_related_settings">Database related settings</h3>

<h4 id="24636f6e6669675b2764625f74797065275d" style="padding-left: 30px;">$config[&#39;db_type&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> specifies what type of database you&#39;re using.&nbsp; Values can be &quot;pgsql&quot;;// pgsql or mysql</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> &#39;pgsql&#39;</p>

<h4 id="24636f6e6669675b2764625f686f7374275d" style="padding-left: 30px;">$config[&#39;db_host&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description: </i></b>the hostname of the host where the FileSender database server resides.&nbsp; Simplest setup is on the FileSender server</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> &#39;localhost&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2764625f6461746162617365275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;db_database&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> Name of the Postgresql database that will be used to store FileSender&#39;s meta data.&nbsp; Files are stored directly on disk.</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> &#39;filesender&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2764625f706f7274275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;db_port&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description: </i></b>TCP port of the Postgresql database that FileSender will connect to</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> &#39;5432&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2764625f757365726e616d65275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;db_username&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> username used to authenticate to the Postgresql database</p>

<p style="padding-left: 60px;"><i><b>default:</b></i><b> </b>none</p>

<p style="padding-left: 60px;"><b><i>example:</i></b> &#39;filesender&#39;</p>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2764625f70617373776f7264275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;db_password&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> password to authenticate to the Postgresql database</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> none</p>

<p style="padding-left: 60px;"><b><i>example:</i></b> &#39;databasepassword&#39;</p>

<p style="padding-left: 60px;">&nbsp;</p>

<p>To accomodate more&nbsp; elaborate PDO database settings a DSN style database setting can be configured which will override the db_* settings:</p>

<pre style="">
&nbsp;&nbsp;&nbsp; //Optional DSN format overides db_ settings
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn&#39;] = &quot;pgsql:host=localhost;dbname=filesender&quot;;
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn&#39;] = &#39;pgsql:host=localhost;dbname=filesender&#39;;
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn&#39;] = &#39;sqlite:/usr/share/filesender/db/filesender.sqlite&#39;;
&nbsp;&nbsp;&nbsp; //$config[&#39;dsn_driver_options&#39;] = array();
&nbsp;&nbsp;&nbsp; // dsn requires username and password in $config[&#39;db_username&#39;] and $config[&#39;db_password&#39;]</pre>

<h4 id="24636f6e6669675b2764736e275d" style="padding-left: 30px;">$config[&#39;dsn&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description: </i></b>the &#39;URL&#39; pointing to the FileSender database</p>

<p style="padding-left: 60px;"><i><b>default:</b></i> none</p>

<h3 id="cron_settings">Cron settings</h3>

<h4 id="c2a0c2a0c2a0c2a0c2a0c2a0c2a02024636f6e6669675b2763726f6e5f6578636c75646520707265666978275d">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;cron_exclude prefix&#39;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: exclude deletion of files with the prefix character listed (can use multiple characters eg &#39;._&#39; will ignore .xxxx and _xxxx<br />
<i><b>default</b></i>: &#39;_&#39;</p>

<p style="padding-left: 60px;">&nbsp;</p>

<blockquote style="">
<blockquote style="">
<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e24636f6e6669675b2763726f6e5f7368726564275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">$config[&#39;cron_shred&#39;]</span></h4>
</blockquote>
</blockquote>

<blockquote style="">
<blockquote style="">
<blockquote style=""><span style="background-color: rgb(255, 255, 255);"><i><b>description</b></i>:<span style="font-style: normal;">&nbsp;instead of simply unlinking, overwrite expired files so they are hard to recover</span></span></blockquote>
</blockquote>

<blockquote style="">
<blockquote style=""><span style="background-color: rgb(255, 255, 255);"><i style="font-weight: bold;">availability:</i><span style="font-style: normal;"> version 1.5</span></span></blockquote>
</blockquote>

<blockquote style="">
<blockquote style=""><span style="background-color: rgb(255, 255, 255);"><i><b>default</b></i>:<span style="font-style: normal;"> false;</span></span></blockquote>
</blockquote>
</blockquote>

<blockquote style="">
<blockquote style="">
<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223ec2a024636f6e6669675b2763726f6e5f73687265645f636f6d6d616e64275d3c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">&nbsp;$config[&#39;cron_shred_command&#39;]</span></h4>
</blockquote>
</blockquote>

<blockquote style="">
<blockquote style="">
<blockquote style=""><span style="background-color: rgb(255, 255, 255);"><i><b>description</b></i>:<span style="font-style: normal;">&nbsp;the command used to shred files</span></span></blockquote>
</blockquote>

<blockquote style="">
<blockquote style=""><span style="background-color: rgb(255, 255, 255);"><b><i>availability:</i></b><span style="font-style: normal;"> version 1.5</span></span></blockquote>
</blockquote>

<blockquote style="">
<blockquote style="">
<div><span style="background-color: rgb(255, 255, 255);"><i><b>default</b></i>:<span style="font-style: normal;">&nbsp;&#39;/usr/bin/shred -f -u -n 1 -z&#39;;</span></span></div>
</blockquote>
</blockquote>
</blockquote>

<div>
<p>&nbsp;</p>

<p style="padding-left: 60px;">&nbsp;</p>

<p>&nbsp;</p>

<p style="padding-left: 60px;">&nbsp;</p>

<p style="padding-left: 60px;">&nbsp;&nbsp;</p>

<p>&nbsp;</p>

<h3 id="email_related_configuration_directives">Email related configuration directives</h3>

<p>FileSender sends out 5 types of email to users. In the configuration file you can define templates for these emails.&nbsp; These templates can contain template variables that will be filled when the actual email is created.&nbsp; This section details the configuration file directives for those email templates and the email template variables.&nbsp;</p>

<p><span style="font-size: small;"><span style="color: #ff0000;"><i><b>** finished except for the mapping of which variables can be used with which templates **</b></i></span></span></p>

<h4 id="24636f6e6669675b2764656661756c745f656d61696c7375626a656374275d" style="padding-left: 30px;">$config[&#39;default_emailsubject&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> if a FileSender user refrains from entering an email subject then this subject will be used</p>

<p style="padding-left: 60px;"><i>usable template variables:</i> {siteName}, {filename}</p>

<p style="padding-left: 60px;"><i>default value:</i> &quot;{siteName}: {filename}&quot;;</p>

<h4 id="c2a024636f6e6669675b273c7370616e207374796c653d22636f6c6f723a20233030303030303b223e66696c65646f776e6c6f61646564656d61696c626f64793c2f7370616e3e275d3c623ec2a03c2f623e" style="padding-left: 30px;">&nbsp;$config[&#39;<span style="color: #000000;">filedownloadedemailbody</span>&#39;]<b>&nbsp;</b></h4>

<p style="padding-left: 60px;"><b><i>description: </i></b>email sent to the <i>sender</i> of a file when a <i>recipient</i> has downloaded that file.</p>

<p style="padding-left: 60px;"><i>usable template variables:</i></p>

<h4 id="24636f6e6669675b273c7370616e207374796c653d22636f6c6f723a20233030303030303b223e66696c6575706c6f61646564656d61696c626f64793c2f7370616e3e275d" style="padding-left: 30px;">$config[&#39;<span style="color: #000000;">fileuploadedemailbody</span>&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description</i>:</b> email sent to the <i>recipient(s)</i> of an uploaded file that the file is available for download.</p>

<p style="padding-left: 60px;"><i>usable template variables</i>:</p>

<h4 id="24636f6e6669675b273c7370616e207374796c653d22636f6c6f723a20236666303030303b223e3c7370616e207374796c653d22636f6c6f723a20233030303030303b223e766f7563686572697373756564656d61696c626f64793c2f7370616e3e3c2f7370616e3e275d" style="padding-left: 30px;">$config[&#39;<span style="color: #ff0000;"><span style="color: #000000;">voucherissuedemailbody</span></span>&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i> </b>email sent to a recipient of a voucher that a voucher is available to upload a file.</p>

<p style="padding-left: 60px;"><i>usable template variables:</i></p>

<h4 id="24636f6e6669675b2764656661756c74766f756368657263616e63656c6c6564275d" style="padding-left: 30px;">$config[&#39;defaultvouchercancelled&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> email sent to a recipient of a voucher that said voucher is now cancelled.</p>

<p style="padding-left: 60px;"><i>usable template variables:</i></p>

<h4 id="24636f6e6669675b2764656661756c7466696c6563616e63656c6c6564275d" style="padding-left: 30px;">$config[&#39;defaultfilecancelled&#39;]</h4>

<p style="padding-left: 60px;"><b><i>description:</i></b> email sent to a recipient of a file that said file is now cancelled.</p>

<p style="padding-left: 60px;"><i>usable template variables:</i></p>

<h3 id="email_template_variables">Email template variables</h3>

<p>In email templates you can use certain variables that will be expanded by FileSender when the emails are actually created.&nbsp; The following template variables can be used in the email subject and the email body:</p>

<h4 id="7b66696c65746f7d" style="padding-left: 30px;">{fileto}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the recipient address of the mail<b>&nbsp;</b></i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>usable in emails: <b>fileuploadedemailbody, filedownloadedemailbody</b></i></p>
	</li>
</ul>
</blockquote>

<h4 id="7b66696c6566726f6d7d" style="padding-left: 30px;">{filefrom}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the sender address of the mail</i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>usable in emails: <b>fileuploadedemailbody, filedownloadedemailbody</b></li>
</ul>
</blockquote>

<blockquote style=""><b>&nbsp;</b></blockquote>

<blockquote style=""><b>{filemessage_start} and {filemessage_end}</b></blockquote>

<ul style="margin-left: 40px;">
	<li><b>markers for begin and end of the (optional) personal message</b></li>
	<li>usable in emails:<b> <b>fileuploadedemailbody</b> </b></li>
</ul>

<h4 id="7b736974656e616d657d" style="padding-left: 30px;">{siteName}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the site name as specified in $config[&#39;site_name&#39;]</i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>usable in emails: <b>filedownloadedemailbody, fileuploadedemailbody, voucherissuedemailbody, defaultvouchercancelled, defaultfilecancelled</b><b>&nbsp;</b></li>
</ul>
</blockquote>

<h4 id="7b66696c656e616d657d207b66696c656f726967696e616c6e616d657d" style="padding-left: 30px;">{filename} {fileoriginalname}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the original filename. </i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>usable in emails: <b>fileuploadedemailbody, filedownloadedemail</b><b>body</b></li>
</ul>
</blockquote>

<ul>
</ul>

<h4 id="7b68746d6c66696c656e616d657d203c623e7b68746d6c66696c656f726967696e616c6e616d657d3c2f623e" style="padding-left: 30px;">{htmlfilename} <b>{htmlfileoriginalname}</b></h4>

<blockquote style="">
<ul>
	<li>usable in the HTML part of emails: <b>fileuploadedemailbody, filedownloadedemail</b><b>body</b><b> </b></li>
	<li>Same as {filename} but with html encoding of unsafe characters. <b>Always</b> use this variable to specify the filename in HTML parts of a mail</li>
</ul>
</blockquote>

<h4 id="7b73657276657275726c7d" style="padding-left: 30px;">{serverURL}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with URL as defined in $config[&#39;site_url&#39;]<b>&nbsp;</b></i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>usable in emails:&nbsp;</i></p>
	</li>
</ul>
</blockquote>

<h4 id="7b66696c65766f75636865727569647d" style="padding-left: 30px;">{filevoucheruid}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the voucher ID of the file or voucher (?)<b> </b></i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>usable in emails:&nbsp;</i></p>
	</li>
</ul>
</blockquote>

<h4 id="7b66696c65657870697279646174657d" style="padding-left: 30px;">{fileexpirydate}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the expiry date of the file<b> </b></i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>usable in emails:&nbsp;</i></p>
	</li>
</ul>
</blockquote>

<h4 id="7b66696c6573697a657d" style="padding-left: 30px;">{filesize}</h4>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>will be replaced with the filesize of the file<b> </b></i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>
	<p><b>&nbsp;</b><i>usable in emails:&nbsp;<b>&nbsp;</b></i></p>
	</li>
</ul>
</blockquote>

<h4 id="7b63726c667d" style="padding-left: 30px;">{CRLF}</h4>

<blockquote style="">
<ul>
	<li>used to insert a line break in emails.</li>
</ul>
</blockquote>

<h4 id="7b636861727365747d" style="padding-left: 30px;">{charset}</h4>

<blockquote style="">
<ul>
	<li>
	<p><i><b>&nbsp;</b>will be replaced with the charset detected in the actual message</i></p>
	</li>
</ul>
</blockquote>

<blockquote style="">
<ul>
	<li>
	<p><i><b>&nbsp;</b>used in the MIME headers of emails:</i><i> <b>fileuploadedemailbody, filedownloadedemailbody</b></i></p>
	</li>
</ul>
</blockquote>

<p>&nbsp;</p>

<h3 id="6e6f7420696d706c656d656e7465642f756e75736564">Not implemented/unused</h3>

<p style="padding-left: 30px;"><b>$config[&#39;site_icon&#39;]</b> = &#39;cloudstor.png&#39;;</p>

<p style="padding-left: 30px;"><b>$config[&#39;site_css&#39;]</b> = &#39;&#39;;</p>

<h4 id="24636f6e6669675b227365727665725f647269766573706163655f7761726e696e67225d" style="padding-left: 30px;">$config[&quot;server_drivespace_warning&quot;]</h4>

<p style="padding-left: 60px;"><i><b>description</b></i>: the percentage of free space on the storage device at (or below) which a warning message is mailed to the administrator(s) as specified in $config[&#39;adminEmail&#39;].&nbsp;</p>

<p style="padding-left: 60px;"><i><b>default</b></i>: 20 (= send a warning when 20% or less space is left)</p>

<p style="padding-left: 30px;">&nbsp;</p>
</div>

