<p>Note: this page is kept around for historical reference.</p>

<p><strong>Overview</strong><br />
Develop a web based file uploading platform (&lt; 1.5 GB) and a cross platform client-based file uploading platform for large file sizes (&gt; 1.5 GB) to allow secure sharing of files with other users. Authentication provided through SAML and LDAP.</p>

<p>Workflow:</p>

<p>A user has 2 options.<br />
1. In case the file to be shared is smaller than 1.5GB.</p>

<ul>
	<li>&nbsp;Logon to file sender site</li>
	<li>&nbsp;Authenticate using SAML/LDAP</li>
	<li>Select Encrypted Storage - enter unique password</li>
	<li>Add recipient users&#39; email accounts</li>
	<li>Select timeframe before removal from server</li>
	<li>Upload a file using Flex/HTTP Transfer</li>
	<li>Notification arrives when a recipient completes a download of the file</li>
</ul>

<p>2. IIn case the file to be shared is larger than 1.5GB.</p>

<ul>
	<li>Download AIR Application</li>
	<li>Open File Sender Client</li>
	<li>Authenticate using SAML/LDAP</li>
	<li>Select Encrypted Storage - enter unique password</li>
	<li>Add recipient users&#39; email accounts</li>
	<li>Select timeframe before removal from server</li>
	<li>Schedule transfer at a particular time</li>
	<li>Upload a file using HTTP</li>
	<li>(optiional: pause/resume uploads where required)</li>
	<li>Notification arrives when a recipient completes a download of the file</li>
</ul>

<p>2. b Due to an undocumented major problem in the Adobe AIR framework file/bytearray access, it is impossible to select part of a file when loading a bytearray from a local file. Rather, the AIR framework must load the entire file into memory first. This issue has not yet been resolved by Adobe, forcing this project to trial alternative means of uploading. We are trialing a Java Applet as an optional way of uploading over 1.5Gb files.</p>

<p>Large file transfer using HTTP upload while still providing a cross platform solution is achieved using the following process. By splitting the file down into smaller files and upload each small file through http to the server (this is an extra security in that the file needs to be put back together to work again). What this means is that a file of say 10 GB (afile.mdb) would become 20 x 500Mb files. Each file is uploaded to the server and if one file fragment upload fails or the network locks up or a natural disaster occurs, then the application and server know where they are up to and are able to go back and re-start on the last incomplete file. Once all file fragments are uploaded, the collection of file fragments is made available for an authorised user to download. The AIR application on the recipient client side then puts the file fragments back together as one file for the user.</p>

<p><strong>Technology</strong></p>

<p>File Sender will involve the following technologies</p>

<p>Client</p>

<ul>
	<li>Web Browser</li>
	<li>Flash Player</li>
	<li>Adobe AIR</li>
</ul>

<p>Server</p>

<ul>
	<li>Simple Saml (<a href="http://rnd.feide.no/simplesamlphp" target="_blank">see SimpleSaml</a>)</li>
	<li>PHP</li>
	<li>Postgres (<a href="http://www.postgresql.org/" target="_blank">Postgres database</a>)</li>
	<li>Flex (<a href="http://www.adobe.com/products/flex/" target="_blank">Adobe Flex</a>)</li>
</ul>

<p>&nbsp;</p>

