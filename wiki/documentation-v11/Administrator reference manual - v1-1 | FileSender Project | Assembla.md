
<p>
      </p><p>This is the Administrator Reference Manual for FileSender version 1.0 and 1.1</p>
<ul><li>[[#Administering FileSender]]</li><li>[[#Authentication]]
<ul><li>[[#IDP Attributes]]</li></ul>
</li><li>[[#Security considerations]]
<ul><li><span style="background-color: #ffffff;"><a href="https://www.assembla.com/spaces/file_sender/wiki/Administrator_reference_manual/edit#Warning%20-%20Encryption">Warning - Encryption</a></span></li></ul>
</li><li>[[#Customization]]</li><li>[[#Configuration]]
<ul><li>[[#Configuration file directives]]
<ul><li>[[#General settings]]</li><li>[[#User Interface (UI) settings]]</li><li>[[#Debug settings]]</li><li>[[#SAML attribute settings]]</li><li>[[#Acceptable Use Policy (AUP) settings]]</li><li>[[#Server settings]]</li><li>[[#Advanced server settings]]</li><li>[[#Site URL settings]]</li><li>[[#Support links]]</li><li>[[#File and directory location settings]]</li><li>[[#Database related settings]]</li><li>[[#Cron settings]]</li><li>[[#Email related configuration directives]]</li><li>[[#Email template variables]]</li><li>[[#Not implemented/unused]]</li></ul>
</li></ul>
</li></ul>
<h1>Administering FileSender</h1>
<h3>Installation and initial configuration</h3>
<p>Consult the relevant installation guide:</p>
<ul><li><a href="https://www.assembla.com/spaces/file_sender/wiki/Installation_-_Linux_Source">Installation - Linux Source</a></li><li><a href="https://www.assembla.com/spaces/file_sender/wiki/Installation_-_Debian_Ubuntu">Installation - Debian Ubuntu</a></li><li><a href="https://www.assembla.com/spaces/file_sender/wiki/Installation_-_RPM">Installation - RPM</a></li></ul>
<h3>Regular tasks</h3>
<ol><li>Make sure the daily expiry cron job runs.  This is needed to delete 
files and vouchers that have expired. The debian and RPM packages will 
install a daily cronjob for you in /etc.cron.daily/filesender. When 
installed from source make sure you have installed a cronjob as per the 
[[Installation - Linux Source#Configure cron|Configure cron]] section in
 the Installation Guide.</li><li>Clean temp_filestore and log directories.  FileSender does not do 
any of this automatically so you as a server admin need to ensure this 
happens.  The temp_filestore tends to get filled with files that are 
leftover when a user cancels an upload.  Log files are created on a 
daily basis but are not automatically purged.</li><li>Check logfiles for errors. </li><li>Database cleanup: every upload to FileSender results in one or more 
database entries.  Not all of these are deleted which could lead to 
performance degradation in the long run.  You should check your database
 what the situation is and whether it needs cleanup of very old entries.</li></ol>
<h3>The Administrator web interface</h3>
<p>The administrator web interface is accessed through the regular 
FileSender Flash UI.  A button becomes visible when you log on with an 
account that has a GUID (like eduPersonTargetedId or ePPN) configured in
 <span style="font-family: courier new,courier;">$config['admin']</span>.  The administrator web interface provides an easy overview of the use of your FileSender installation.</p>
<h3>Troubleshooting</h3>
<h4>Relevant logfiles to check</h4>
<p>Relevant logging can appear at three places:</p>
<ol><li>the FileSender logdirectory as configured in your config file with <span style="font-family: courier new,courier;">$config['log_location']</span></li><li>your webserver logs</li><li>your PHP logs (as per the relevant php.ini settings, often your /var/log/messages or /var/log/syslog file)</li></ol>
<p>! If there is no logging in your FileSender log directory, make sure the web server can write to it.</p>
<p>! If nothing works you might have issues with connecting to your 
database.  Increase database logging to study interaction between your 
database and FileSender.</p>
<h4>Getting more debugging information</h4>
<p>In case of problems you can turn on debugging in the FileSender 
configuration (see [[#Debug settings]] for the relevant directives). 
Setting<span style="font-family: courier new,courier;"> $config['debug'] = true</span>
 will turn on extra logging (both for FileSender in the FileSender 
log-directory and PHP) and additionally will show some extra technical 
information in the Flash UI shown to the user.</p>
<p id="266e6273703b266e6273703b266e6273703b266e6273703b266e6273703b266e6273703b266e6273703b2024636f6e6669675b22636c69656e745f73706563696669635f6c6f6767696e675f75696473225d">To investigate client (the browser/Flash UI) problems (for a specific user) you can enable client specific logging by setting <span style="font-family: courier new,courier;">$config["client_specific_logging"] = true</span>. By default this will generate extra logfiles <b>per user </b>for
 all users in the FileSender log directory with details about the 
relevant actions taken by the client. You can restrict the client 
specific logging to specific clients by specifying a GUID or Voucher ID 
with the <span style="font-family: courier new,courier;">$config["client_specific_logging_uids"]</span> directive.</p>
<p>Note that turning on the debug settings will decrease performance so don't forget to turn off the debugging after investigation.</p>
<h1>Authentication</h1>
<p>FileSender has <b>no</b> local user database for user authentication 
but uses the [[url:http://simplesamlphp.org/|SimpleSAMLphp]] software to
 have the authentication part handled by remote Identity Providers 
(IdP). In this model FileSender is the Service Provider (SP). The user 
is directed to the login page of the IdP and after succesful 
authentication an OK and a set of attributes is returned from the IdP to
 FileSender. The default installation and configuration has the Feide 
OpenIDP configured as public Identity Provider. If you want to connect 
your FileSender instance to your own (set of) Identy Provider(s) or 
Federation please have a look at the <span style="color: #ff0000;"> </span><a href="http://simplesamlphp.org/docs/1.6/simplesamlphp-sp">SimpleSAML Service Provider Quickstart</a>.</p>
<h2>IDP Attributes</h2>
<p>FileSender is by default looking for the attributes 'mail' and 'cn' and 'eduPersonTargetedID'.</p>
<p>These are configurable in config.php in the [[#SAML attribute settings]] section</p>
<p>You can check which attributes are received by your FileSender 
installation on the SimpleSAMLphp pages, in most cases that will be at 
https://<i><your-server></i>/simplesaml/module.php/core/authenticate.php
 . Login from that page to get a list of known attributes and their 
names and values.</p>
<h1>Security considerations</h1>
<h2><span style="background-color: #ff0000;"><a name="Warning - Encryption"></a>Warning - Encryption</span></h2>
<p>FileSender itself does <b>not</b> offer protection agains eavesdropping on the contents of uploaded/downloaded files.</p>
<p>Sensitive files can currently be protected in two ways:</p>
<ul><li>in flight: protect files during upload/download using SSL.  Ensure your FileSender webserver is only reachable over HTTPS.</li><li>in rest: files stored on the FileSender server should be encrypted by the user <b>before</b> uploading them.</li></ul>
<h1>Customization</h1>
<p>FileSender offers some limited support for customization. 
Customatizations not mentioned in this section will require changing the
 code and will not survive upgrades or re-installs unless you keep a 
good backup of all your modifications.</p>
<h3>Custom banner</h3>
<p>By default FileSender will use the banner image supplied in the <span style="font-family: courier new,courier;">www/banner.png</span> file to display at the top of all web pages. You can put a custom banner image in <span style="font-family: courier new,courier;">config/banner.png</span> which will override the default banner image. This image has to be in PNG format and should be sized as 800x60 pixels. </p>
<h3>Custom User Interface and instance name</h3>
<p>The <span style="font-family: courier new,courier;">$config['site_name']</span>
 setting can be used to give your FileSender instance a custom 
'friendly' name. The text in this directive will be used on the main 
login page and in the Subject: line and text body of all email messages.</p>
<p>The <span style="font-family: courier new,courier;">$config['site_splashtext']</span>
 can be used to display a custom text on the main login page. This text 
can contain HTML-code to insert links or do some simple formatting.</p>
<p>Both settings can be found in the [[#General settings]] section of the configuration file.</p>
<p>Also have a look at the [[#User Interface (UI) settings]] section for some settings to tweak the UI.</p>
<h3>Custom Terms and Conditions (AUP)</h3>
<p>Local Terms and Conditions (a.k.a. the Acceptable Use Policy) can be 
specified with the directives in the [[#Acceptable Use Policy (AUP) 
settings]] section.</p>
<h3>Custom support pages</h3>
<p>The settings in the [[#Support links]] section of the configuration 
file can be used to direct people to custom help and about pages and a 
page about the Gears plugin (version 1.0) or HTML5 support (version 
1.1), i.e. the pages linked to the 'Help', 'About' and 'Gears'/'HTML5' 
links in the main user interface. </p>
<p>If you need custom help/about pages copy the default help.php and 
about.php to for example 'local-help.php' and 'local-about.php' and 
modify these copies. Then adjust the [[#Support links]] settings to 
point to these custom pages. You can also just point to 'external' pages
 on for example your main website.</p>
<p>Modifying the supplied help.php and about.php is discouraged since 
these files in general will be overwritten with upgrades or re-installs.</p>
<p>The <span style="font-family: courier new,courier;">$config['site_logouturl']</span>
 setting (in the [[#Site URL settings]] section) can be used to point to
 a custom page to return to after the authenticated user has logged out.
 Note that the actual use of this page also depends on the Identity 
Provider and/or Federation of the authenticated user, not all of them 
redirect back to the requested logout page.</p>
<h3>Customising SimpleSAMLphp</h3>
<p>In case you use the local SimpleSAMLphp 'Identity Provider' selection page you can have a look at the <a href="https://www.assembla.com/spaces/file_sender/documents/am2bkchOyr4jeEeJe5cbCb/download/am2bkchOyr4jeEeJe5cbCb">themefilesender module</a>. This module will give SimpleSAMLphp the same look&feel as FileSender.</p>
<h3>Language</h3>
<p>FileSender 1.0 only supports one language (English). Full localisation (multi-language support) is on the road map for 2.0.</p>
<h1>Configuration</h1>
<p>All configuration of FileSender is done by editing the configuration file:</p>
<p style="padding-left: 30px;"><span style="font-family: courier new,courier;">config/config.php</span></p>
<p>This file is actual PHP code so be careful to adhere to the PHP syntax:</p>
<ul><li>keep the closing ; at the end of a $config specification</li><li>enclose string/text values in single or double quotes</li><li>boolean values can be specified as true or false (without quotes)</li><li>remarks/comments start with // or are enclosed in /* ... */</li></ul>
<h2>Configuration file directives</h2>
<p>This section describes all the available configuration settings in config.php.</p>
<h3>General settings</h3>
<h4>      $config['admin']</h4>
<p style="padding-left: 60px;"><i><b>description:</b></i> list of UIDs 
of administrators, separated by comma. Administrators have access to the
 Administrator Interface. A UID is the value of the attribute defined in
 <i>$config['saml_uid_attribute']</i> in the [[#SAML attribute settings]] section.</p>
<p style="padding-left: 60px;"><i><b>default:</b></i> none</p>
<p style="padding-left: 60px;"><b><i>example</i></b>: '31a7bf626eb4fa2d425f611c0490940e71e1c42c' <i>(with eduPersonTargetedID as UID attribute)</i></p>
<p style="padding-left: 60px;"><b><i>example:</i></b> 'john.doe@mysite.dom' <i>(with mail as UID attribute)</i></p>
<h4>        $config['adminEmail']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: Email address(es, separated by ,) to receive administrative messages (low disk space warning)</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: none</p>
<h4 style="padding-left: 30px;">$config['Default_TimeZone']</h4>
<p style="padding-left: 60px;"><span style="color: #ff0000;"><span style="color: #000000;"><i><b>description:</b></i> Set this to your local timezone according to timezone specifications in <a href="http://php.net/manual/en/timezones.php" target="_blank">http://php.net/manual/en/timezones.php </a></span><br></span></p>
<p style="padding-left: 60px;"><i><b>default:</b></i> 'Australia/Sydney'</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: 'Europe/Berlin'</p>
<h4>        $config['site_name']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: Friendly name used for your FileSender instance. Used on the main login page and in emails.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 'FileSender'</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: 'AARnet CloudStor'</p>
<h4>        $config["site_splashtext"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: text to display on the main login page</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "FileSender is a secure way to share large files with anyone! Logon to upload your files or invite people to send you a file."</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: It is possible to use some simple HTML markup</p>
<h3>User Interface (UI) settings</h3>
<h4>        $config['datedisplayformat']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: Format for displaying date/time. Format has to be specified in the  <a href="http://help.adobe.com/en_US/FlashPlatform/reference/actionscript/3/mx/formatters/DateFormatter.html" target="_blank">Flex DateFormatter</a> format specifier syntax</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "DD-MM-YYYY"</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "DD-MM-YYYY H:NN"</p>
<h4>        $config["versionNumber"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: show FileSender version number in the upper right corner</p>
<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>
<h4>        $config['site_showStats']</h4>
<p style="padding-left: 60px;"><b><i>description</i></b>: show upload/download statistics up in the upper right corner.<b><i><br></i></b></p>
<p style="padding-left: 60px;"><b><i>default: </i></b>false</p>
<h4>        $config['displayUserName']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: show 'Welcome 
user' in the upper left corner. The friendly name of the authenticated 
user is taken from the SAML attribute as specified by 
$config['saml_name_attribute'] or will be 'Guest' for users using a 
voucher.</p>
<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>
<h3>Debug settings</h3>
<h4>        $config["debug"]</h4>
<p style="padding-left: 60px;"><i><b>description:</b></i> if set to true
 server side logging will be more verbose and the UI wil display extra 
technical information of what's happening. This setting also increases 
the PHP loglevel.</p>
<p style="padding-left: 60px;"><b><i>values:</i></b> true/false</p>
<p style="padding-left: 60px;"><b><i>default:</i></b> false <i>(true in beta releases)</i></p>
<h4>        $config['dnslookup']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: if set to true
 the logging includes a reverse DNS lookup of the originating IP-address
 of the user. On really busy servers this may impact performance.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>
<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>
<h4>        $config["client_specific_logging"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: turn on/off 
client specific logging. If set to true the client (Flash UI) will send 
debug information to the server which will be logged in separate 
user-specific files in the 'log_location' directory.</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: turning on client specific logging will impact performance</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: false <i>(true in beta releases)</i></p>
<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>
<h4>        $config["client_specific_logging_uids"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: A list of 
UIDs, separated by comma. When client specfiic logging is turned on the 
logging will be restricted to the UIDs in this list. The value "" 
(default) means 'log all clients'. A UID can be the UID of an 
authenticated user (as specified by the saml_uid_attribute setting 
below) or a voucher ID.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: ""</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: '31a7bf626eb4fa2d425f611c0490940e71e1c42c, 6B30BA68-B883-8565-36B5-73CDBE0C672C'</p>
<h3>SAML attribute settings</h3>
<h4><b>       </b><b>$config['saml_email_attribute']<br></b></h4>
<p style="padding-left: 60px;"><i><b>description:</b></i> . attribute used as From: email address of the authenticated user</p>
<p style="padding-left: 60px;"><i><b>default:</b></i> mail</p>
<h4 style="padding-left: 30px;">$config['saml_name_attribute']</h4>
<p style="padding-left: 60px;"><i><b>description: </b></i>attribute used
 to get the friendly name of the authenticated user. If this attribute 
does not exist or has no value (?) then FileSender will use the first 
part of the email attribute before the @ as the 'name_attribute' value.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: cn</p>
<h4 style="padding-left: 30px;">$config['saml_uid_attribute']</h4>
<p style="padding-left: 60px;"><i><b>description: </b></i>attribute to uniquely identify the user.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: eduPersonTargetedID</p>
<h3>Acceptable Use Policy (AUP) settings</h3>
<h4>        $config["AuP_default"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: when set to 
false (the default) the user has to explicitly tick the 'I accept the 
AuP' checkbox before uploading a file. When set to true the checkbox 
will already be ticked.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: false</p>
<h4>        $config["AuP"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: a text box with a AuP is displayed</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>
<h4>        $config["AuP_label"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: text label to show at the AuP checkbox</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "I accept the terms and conditions of this service"</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: the text is limited to the width of the AuP-box (will be 50 to 70 characters)</p>
<h4>        $config["AuP_terms"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: text to show in the AuP box containing the terms and conditions the user has to accept before using the service.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "AuP Terms and conditions"</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: line breaks can be specified with \n or 'as is' (just continu the text on the next line), beware of the use of quotes.</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "Terms and conditions\n\nTerm 1\n\nCondition2\n\nClosing remark."</p>
<h3>Server settings</h3>
<h4>        $config['default_daysvalid']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: Maximum number of days before a file or a voucher is expired</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 20</p>
<h4>        $config['ban_extension']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: Possibly dangerous file extensions that are disallowed</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: = 'exe,bat'</p>
<h4>        $config["max_email_recipients"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: maximum email addresses allowed to send at once for voucher or file sending, a value of 0 allows unlimited emails.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 100</p>
<h4 style="padding-left: 30px;">$config['max_flash_upload_size']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: the maximum 
files size when uploading with Flash (no Gears installed (version 1.0 or
 no HTML5 support (version 1.1)), specify in number of bytes.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: '2147483648' (2 GigaByte)</p>
<p style="padding-left: 60px;"><i><b>remarks</b></i>: the value specified will be compared with the PHP settings <span style="font-family: courier new,courier;">post_max_size</span> and <span style="font-family: courier new,courier;">upload_max_filesize.</span> The minimum of these values will be used as actual maximum upload size for Flash uploads.</p>
<h4>       $config['max_gears_upload_size']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: the maximum file size when uploading with Gears (version 1.0) or HTML5 (version 1.1), specify in number of bytes.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: '107374182400' (100 GigaByte)</p>
<h4 style="padding-left: 30px;">$config["server_drivespace_warning"]</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: the percentage
 of free space on the storage device at (or below) which a warning 
message is mailed to the administrator(s) as specified in 
$config['adminEmail']. </p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 20 (= send a warning when 20% or less space is left)</p>
<h3>Advanced server settings</h3>
<p>This section contains settings that under normal circumstances don't need changing. <b>Do not change them unless you have a very good reason.</b></p>
<p>        <b>$config['postgresdateformat']</b></p>
<p style="padding-left: 60px;"><b>description:</b> Date/Time format for PostgreSQL, use<a href="http://www.php.net/manual/en/function.date.php" target="_blank"> PHP date format specifier syntax</a></p>
<p style="padding-left: 60px;"><b>default:</b> 'Y-m-d H:i:sP'</p>
<h4 style="padding-left: 30px;">$config["crlf"]</h4>
<p style="padding-left: 60px;"><b>description:</b> controls whether 
lines in emails sent out by FileSender are terminated with CRLF or with 
LF.  What makes sense depends on your PHP and email setup.  Linux/Unix 
hosts will need "\n".  Possible values are "\n" or "\r\n". Keep this at 
the default unless you have some weird setup.</p>
<p style="padding-left: 60px;"><b>default: '</b>\n'</p>
<h4 style="padding-left: 30px;">$config['voucherRegEx']</h4>
<p style="padding-left: 60px;"><i><b>description: </b></i>When someone 
uses a voucher, the voucher is in the format of 8 numbers/letters 
followed by - 4numlet-4numlet-4-12numlet unique Id that's standard flash
 and windows GUID (generated unique id).  The regex is to make sure that
 a presented voucherId adheres to this GUID format.  Anything else will 
result in a 'bugger off'.  Also makes sure that generated vouchers are 
constructed correctly.  Reason for putting it in config is because the 
PhP uniqueId is a different format so you'd need a different RegEx.  So 
this is future proofing the vouchers<b>.</b><i><b><br></b></i></p>
<p style="padding-left: 60px;"><i><b>default:</b></i> '[a-zA-Z0-9]{8}-[a-zA-Z0-9]{4}-[a-zA-Z0-9]{4}-[a-zA-Z0-9]{4}-[a-zA-Z0-9]{12}'</p>
<h4>        $config['voucherUIDLength']</h4>
<p style="padding-left: 60px;"><i><b>description: </b>See above.  Make sure no-one tries anything 'interesting' with vouchers<b>.<br></b></i></p>
<p style="padding-left: 60px;"><i><b>default:</b></i> <i>'36'</i></p>
<h4>        $config['emailRegEx']</h4>
<p style="padding-left: 60px;"><i><b>description:</b></i> Regular expression to check the syntax of email-adressess</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 
'[a-z0-9!#$%&'*+/=?^_`{|}~-]+(?:\.[a-z0-9!#$%&'*+/=?^_`{|}~-]+)*@(?:[a-z0-9](?:[a-z0-9-]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9-]*[a-z0-9])?'</p>
<h3>Site URL settings</h3>
<p>These settings define the basic URL's FileSender will use. The 
configuration file will in general automatically define them based on 
the server name of the webserver which is automatically set in the 
global PHP variable <span style="font-family: courier new,courier;">$_SERVER['SERVER_NAME'] </span>The following piece of code in config.php handles the automatic configuration:</p>
<pre><span style="color: #008000;">if ( isset($_SERVER['SERVER_NAME']) ) {</span><br>$prot =  isset($_SERVER['HTTPS']) ? 'https://' : 'http://';<br>$config['site_url'] = $prot . $_SERVER['SERVER_NAME'] . '/filesender/'; // URL to Filesender<br>$config['site_simplesamlurl'] =  $prot . $_SERVER['SERVER_NAME'] . '/simplesaml/';<br>$config['site_authenticationSource'] ="default-sp";<br>$config['site_logouturl'] = $config['site_url'] . 'logout.php';<br>$config['site_downloadurl'] = $config['site_url'] . 'files/'; // * Deprecated *<br><span style="color: #008000;">}</span></pre>
<p>Settings within this block can be modified as long as you keep those settings within the block.</p>
<h4>        $prot</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: variable containing the automatically determined current protocol (http or https) of the connection</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: isset($_SERVER['HTTPS']) ? 'https://' : 'http://'</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: do not change</p>
<h4>        $config['site_url']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: URL on your webserver where the FileSender instance can be reached</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: $prot . $_SERVER['SERVER_NAME'] . '/filesender/'</p>
<p style="padding-left: 60px;"><i><b>remarks</b></i>: URL is 
automatically generated based on the SERVER_NAME and a manually 
specified local path ('/filesender/' by default). If you have your 
FileSender running on another URL you can change the local path part. At
 a minimum, this part should contain '/' which means FileSender is 
running at the root of your webserver.</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: $prot . $_SERVER['SERVER_NAME'] . '/'</p>
<h4>        $config['site_simplesamlurl']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: URL on your webserver where the SimpleSAMLphp instance can be reached</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: $prot . $_SERVER['SERVER_NAME'] . '/simplesaml/'</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: URL is 
automatically generated based on the SERVER_NAME and a manually 
specified local path ('/simplesaml/' by default). If you have your 
SimpleSAMLphp instance running on another URL you can change the local 
path part. If you have your FileSender instance reachable with http (no 
forced SSL) but want to force authentication via simplesaml to use SSL 
change the $prot part to 'https://' (including quotes).</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: 'https://' . $_SERVER['SERVER_NAME'] . '/simplesamlphp/</p>
<h4>       $config['site_authenticationSource']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: authentication source on your SimpleSAMLphp instance to use</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "default-sp"</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "example-userpass" ; <i>Point FileSender to the 'example-userpass' authentication source defined in the SimpleSAMLphp authsources.php</i></p>
<h4>        $config['site_logouturl']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: URL to go to when the user logs out (will be used by the IdP to redirect to)</p>
<p style="padding-left: 60px;"><i><b>remark</b></i>: should be an absolute URL including protocol and host, by default this will be the URL part as generated in <span style="font-family: courier new,courier;">$config['site_url']</span> plus a local path part (default 'logout.php')</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: $config['site_url'] . 'logout.php'</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: $config['site_url'] . 'custom-logout.php'</p>
<h4>        $config['site_downloadurl']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: in beta release before 0.1.16 this was used for download URLs. Deperecated as of beta 0.1.16</p>
<p style="padding-left: 60px;"><i><b>status</b></i>: deprecated, do not use, do not remove.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: $config['site_url'] . 'files/'</p>
<p>The following setting is outside the <span style="font-family: courier new,courier;">if {}</span> block but is related to the server URL settings:</p>
<h4>        $config['forceSSL']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: when set to true (default, recommended) FileSender will force connections to always use SSL</p>
<p style="padding-left: 60px;"><i><b>values</b></i>: true/false</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: true</p>
<h3>Support links</h3>
<p>These settings can be used to point the user to custom 
help/about/gears pages. URLs specified here are opened in a new browser 
window/tab and can be relative (pointing to a file/script in the www 
directory of your FileSender instance) or absolute (including external 
sites).</p>
<h4>        $config['aboutURL']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: URL to go to when the 'About' link in the UI is selected.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "about.php"</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "local-about.php"</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "http://support.example.org/about-filesender.aspx"</p>
<h4>        $config['helpURL']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: URL to go to when the 'Help' link in the UI is selected.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: "help.php"</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "local-help.php"</p>
<p style="padding-left: 60px;"><i><b>example</b></i>: "http://support.example.org/help-for-filesender.aspx"</p>
<h4>        $config['gearsURL']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: URL to go to when the 'Gears' (1.0) or 'HTML5' (1.1) link in the UI is selected.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 'http://tools.google.com/gears/' <i>// Version 1.0(.x)</i></p>
<p style="padding-left: 60px;"><i><b>default</b></i>: 'http://html5test.com/' <i>// Version 1.1</i></p>
<p style="padding-left: 60px;"><i><b>example</b></i>: 'local-gears-information.php'</p>
<h3>File and directory location settings</h3>
<p>These settings define the directory locations where various files can
 be found or stored. Directory values are absolute filesystem paths on 
your server and should be readable and writable (except for the 
site_simplesamllocation) for the webserver user.</p>
<h4>       $config['site_filestore']</h4>
<p style="padding-left: 60px;"><i><b>description:</b></i> the directory where all uploaded files are stored</p>
<p style="padding-left: 60px;"><i><b>remarks</b></i>: this directory should have ample disk space and can fysically be stored on a NAS or other big storage device.</p>
<p style="padding-left: 60px;"><b><i>default:</i></b> '/usr/share/filesender/files/'</p>
<p style="padding-left: 60px;"><b><i>example:</i></b> '/data/filesender/files/'</p>
<h4>        $config['site_temp_filestore']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: the directory 
used to store (partial) Gears uploads. After completion of the Gears 
upload the temporary file will be moved to the 'site_filestore'</p>
<p style="padding-left: 60px;"><i><b>remarks</b></i>: this directory is 
not used for Flash uploads. You might want to do a regular check on this
 directory to remove old partial but never finished uploads. It is 
advised to keep this directory on the same partition as the actual 
'site_filestore' so moving the temporary file will be instantaneous.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: = '/usr/share/filesender/tmp/'</p>
<h4>        $config['site_simplesamllocation']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: directory where the SimpleSAMLphp software can be found. Needed to find the required SImpleSAMLphp libraries.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: = '/usr/share/simplesamlphp/'</p>
<h4>        $config['log_location']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: directory to keep FileSender specific logfiles.</p>
<p style="padding-left: 60px;"><i><b>remarks</b></i>: logfiles are 
created per day (and per user/voucheruid for client_specific_logging). 
FileSender has no internal mechanism to clean up old logs, you might 
want to do a (automated) regular cleanup of this directory.</p>
<p style="padding-left: 60px;"><i><b>default</b></i>: '/usr/share/filesender/log/'</p>
<h3>Database related settings</h3>
<h4 style="padding-left: 30px;">$config['pg_host']</h4>
<p style="padding-left: 60px;"><b><i>description: </i></b>the hostname of the host where the FileSender database server resides.  Simplest setup is on the FileSender server</p>
<p style="padding-left: 60px;"><i><b>default:</b></i> 'localhost'</p>
<h4>        $config['pg_database']</h4>
<p style="padding-left: 60px;"><b><i>description:</i></b> Name of the Postgresql database that will be used to store FileSender's meta data.  Files are stored directly on disk.</p>
<p style="padding-left: 60px;"><i><b>default:</b></i> 'filesender'<i><b><br></b></i></p>
<h4>        $config['pg_port']</h4>
<p style="padding-left: 60px;"><b><i>description: </i></b>TCP port of the Postgresql database that FileSender will connect to<b><i><br></i></b></p>
<p style="padding-left: 60px;"><i><b>default:</b></i> '5432'<i><b><br></b></i></p>
<h4>        $config['pg_username']</h4>
<p style="padding-left: 60px;"><b><i>description:</i></b> username used to authenticate to the Postgresql database<b><i><br></i></b></p>
<p style="padding-left: 60px;"><i><b>default:</b></i><b> </b>none</p>
<p style="padding-left: 60px;"><b><i>example:</i></b> 'filesender'</p>
<h4>        $config['pg_password']</h4>
<p style="padding-left: 60px;"><b><i>description:</i></b> password to authenticate to the Postgresql database</p>
<p style="padding-left: 60px;"><i><b>default:</b></i> none</p>
<p style="padding-left: 60px;"><b><i>example:</i></b> 'databasepassword'</p>
<h3>Cron settings</h3>
<h4>        $config['cron_exclude prefix']</h4>
<p style="padding-left: 60px;"><i><b>description</b></i>: exclude deletion of files with the prefix character listed (can use multiple characters eg '._' will ignore .xxxx and _xxxx<br><i><b>default</b></i>: '_'</p>
<h3>Email related configuration directives</h3>
<p>FileSender sends out 5 types of email to users. In the configuration 
file you can define templates for these emails.  These templates can 
contain template variables that will be filled when the actual email is 
created.  This section details the configuration file directives for 
those email templates and the email template variables. </p>
<p><span style="font-size: small;"><span style="color: #ff0000;"><i><b>** finished except for the mapping of which variables can be used with which templates **</b></i></span></span></p>
<h4 style="padding-left: 30px;">$config['default_emailsubject']</h4>
<p style="padding-left: 60px;"><b><i>description:</i></b> if a FileSender user refrains from entering an email subject then this subject will be used</p>
<p style="padding-left: 60px;"><i>usable template variables:</i> {siteName}, {filename}</p>
<p style="padding-left: 60px;"><i>default value:</i> "{siteName}: {filename}";</p>
<h4 style="padding-left: 30px;"> $config['<span style="color: #000000;">filedownloadedemailbody</span>']<b> </b></h4>
<p style="padding-left: 60px;"><b><i>description: </i></b>email sent to the <i>sender</i> of a file when a <i>recipient</i> has downloaded that file.</p>
<p style="padding-left: 60px;"><i>usable template variables:</i></p>
<h4 style="padding-left: 30px;">$config['<span style="color: #000000;">fileuploadedemailbody</span>']</h4>
<p style="padding-left: 60px;"><b><i>description</i>:</b> email sent to the <i>recipient(s)</i> of an uploaded file that the file is available for download.</p>
<p style="padding-left: 60px;"><i>usable template variables</i>:</p>
<h4 style="padding-left: 30px;">$config['<span style="color: #ff0000;"><span style="color: #000000;">voucherissuedemailbody</span></span>']</h4>
<p style="padding-left: 60px;"><b><i>description:</i> </b>email sent to a recipient of a voucher that a voucher is available to upload a file.</p>
<p style="padding-left: 60px;"><i>usable template variables:</i></p>
<h4 style="padding-left: 30px;">$config['defaultvouchercancelled']</h4>
<p style="padding-left: 60px;"><b><i>description:</i></b> email sent to a recipient of a voucher that said voucher is now cancelled.</p>
<p style="padding-left: 60px;"><i>usable template variables:</i></p>
<h4 style="padding-left: 30px;">$config['defaultfilecancelled']</h4>
<p style="padding-left: 60px;"><b><i>description:</i></b> email sent to a recipient of a file that said file is now cancelled.</p>
<p style="padding-left: 60px;"><i>usable template variables:</i></p>
<h3>Email template variables</h3>
<p>In email templates you can use certain variables that will be 
expanded by FileSender when the emails are actually created.  The 
following template variables can be used in the email subject and the 
email body:</p>
<h4 style="padding-left: 30px;">{fileto}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the recipient address of the mail<b> </b></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>
<p><b> </b><i>usable in emails: <b>fileuploadedemailbody, filedownloadedemailbody</b></i></p>
</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{filefrom}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the sender address of the mail</i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>usable in emails: <b>fileuploadedemailbody, filedownloadedemailbody<br></b></li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{siteName}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the site name as specified in $config['site_name']<br></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>usable in emails: <b>filedownloadedemailbody, fileuploadedemailbody, voucherissuedemailbody, defaultvouchercancelled, defaultfilecancelled</b><b> </b></li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{filename} {fileoriginalname}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the original filename. <br></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>usable in emails: <b>fileuploadedemailbody, filedownloadedemail</b><b>body</b></li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{htmlfilename}</h4>
<blockquote>
<ul><li>usable in the HTML part of emails: <b>fileuploadedemailbody, filedownloadedemail</b><b>body</b><b> </b></li><li>Same as {filename} but with html encoding of unsafe characters. <b>Always</b> use this variable to specify the filename in HTML parts of a mail</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{serverURL}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with URL as defined in $config['site_url']<b> </b></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>
<p><b> </b><i>usable in emails: </i></p>
</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{filevoucheruid}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the voucher ID of the file or voucher (?)<b> <br></b></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>
<p><b> </b><i>usable in emails: </i></p>
</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{fileexpirydate}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the expiry date of the file<b> <br></b></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>
<p><b> </b><i>usable in emails: </i></p>
</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{filesize}</h4>
<blockquote>
<ul><li>
<p><b> </b><i>will be replaced with the filesize of the file<b> <br></b></i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>
<p><b> </b><i>usable in emails: <b> </b></i></p>
</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{CRLF}</h4>
<blockquote>
<ul><li>used to insert a line break in emails.</li></ul>
</blockquote>
<h4 style="padding-left: 30px;">{charset}</h4>
<blockquote>
<ul><li>
<p><i><b> </b>will be replaced with the charset detected in the actual message</i></p>
</li></ul>
</blockquote>
<blockquote>
<ul><li>
<p><i><b> </b>used in the MIME headers of emails:</i><i> <b>fileuploadedemailbody, filedownloadedemailbody</b></i></p>
</li></ul>
</blockquote>
<p> </p>
<h3>Not implemented/unused</h3>
<p>The settings in this section are in the 1.0 config.php file but are 
not implemented, unfinished, deprecated or otherwise not used in version
 1.0 of FileSender. You should not use, change or remove these settings.</p>
<p style="padding-left: 30px;"><b>$config['site_sendfileinstructions']</b>
 = '<B>To send a file.</B><BR>Type an email address 
into the To: box<BR>Select BROWSE to choose a file on your 
compu ter.<BR>Select SEND FILE to upload and send the 
file.';        </p>
<p style="padding-left: 30px;"><b>$config['site_voucherinstructions']</b>
 = 'A Voucher allows someone to send you a file.<BR>To create a 
voucher. Enter an email address then select Send Vouc her.<BR>An 
email will be sent to the recipient with a link to use the 
Voucher.';        </p>
<p style="padding-left: 30px;"><b>$config['site_downloadinstructions']</b> = 'A file is available for you.<BR>Select Download File to download the file to your computer.';</p>
<p style="padding-left: 30px;"><b>$config['available_space']</b> = '20000M';</p>
<p style="padding-left: 60px;"><i><b>description</b></i>: put in here to
 flag somehow that only so much space was allowed to be used.  Should be
 replaced by something that says 'give a trigger to the admin when the 
available space is down to so many% of the total'.  Not in use at the 
moment.<br><i><b>default</b></i>: $config['available_space'] = '20000M';</p>
<p style="padding-left: 30px;"><b>$config['about']</b> = true;</p>
<p style="padding-left: 60px;"><i><b>description</b></i>: triggers the display of a link to an about page in the Flash UI.  The about page itself can be found in www/about.php<br><i><b>default</b></i>: $config['about'] = true;</p>
<p style="padding-left: 30px;"><b>$config["help_link_visible"]</b> = true;</p>
<p style="padding-left: 30px;"><b>$config['site_defaultlanguage']</b> = 'EN_AU';</p>
<p style="padding-left: 30px;"><b>$config['site_icon']</b> = 'cloudstor.png';</p>
<p style="padding-left: 30px;"><b>$config['site_css']</b> = '';</p>
    <p> </p>
