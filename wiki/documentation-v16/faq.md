<ul>
	<li><a class="wiki_link" href="#7131202d20776865726520646f206920747261636b2062726f7773657220696d706c656d656e746174696f6e20737570706f7274206f66207468652068746d6c352066696c656170693f" title="Q1 - Where do I track browser implementation support of the HTML5 FileAPI?">Q1 - Where do I track browser implementation support of the HTML5 FileAPI?</a></li>
	<li><a class="wiki_link" href="#7132202d207369746520776f726b732077697468206874747020627574206e6f7420776974682068747470732c20756e636c65617220666c617368206572726f72732e" title="Q2 - Site works with HTTP but not with HTTPS, unclear Flash errors.">Q2 - Site works with HTTP but not with HTTPS, unclear Flash errors.</a></li>
	<li><a class="wiki_link" href="#7133202d2066697265666f7820637261736865732077697468206c6172676520646f776e6c6f6164733f" title="Q3 - FireFox crashes with large downloads?">Q3 - FireFox crashes with large downloads?</a></li>
	<li><a href="#Undefined%20index%20AttributeName">Q4 - In the logfile I see: &quot;*Error: [8] Undefined index: &lt;/AttributeName/&gt;*&quot;. What does it mean?</a></li>
	<li><a class="wiki_link" href="#7135202d20646f65732066696c6573656e6465722068617665206d6f7265207468616e206f6e652061757468656e7469636174696f6e206d6f64653f" title="Q5 - Does FileSender have more than one authentication mode?">Q5 - Does FileSender have more than one authentication mode?</a></li>
	<li><a class="wiki_link" href="#7136202d20686f7720746f20717569636b6c79206372656174652062696720746573742066696c65733f" title="Q6 - How to quickly create big test files?">Q6 - How to quickly create big test files?</a></li>
	<li><a class="wiki_link" href="#7137202d2075706c6f61642073746f7073206166746572203820686f7572733f" title="Q7 - Upload stops after 8 hours?">Q7 - Upload stops after 8 hours?</a></li>
	<li><a class="wiki_link" href="#7138202d202f6574632f63726f6e2e6461696c792f66696c6573656e646572207068702064657072656361746564207761726e696e67206f6e207562756e74753f" title="Q8 - /etc/cron.daily/filesender PHP Deprecated warning on Ubuntu?">Q8 - /etc/cron.daily/filesender PHP Deprecated warning on Ubuntu?</a></li>
	<li><a class="wiki_link" href="#7139202d2075706c6f616473206172652072656c61746976656c7920736c6f773f" title="Q9 - Uploads are relatively slow?">Q9 - Uploads are relatively slow?</a></li>
</ul>

<h2 id="c2a0">&nbsp;</h2>

<hr />
<h4 id="7131202d20776865726520646f206920747261636b2062726f7773657220696d706c656d656e746174696f6e20737570706f7274206f66207468652068746d6c352066696c656170693f">Q1 - Where do I track browser implementation support of the HTML5 FileAPI?</h4>

<p><strong>A - Check the <a href="http://caniuse.com/#feat=fileapi">&quot;When can I use&quot; website</a> to monitor implementation progress of the HTML5 FileAPI for all major browsers.</strong>&nbsp; In particular support for <a href="http://caniuse.com/#feat=filereader">FileReader API</a> and <a href="http://caniuse.com/#feat=bloburls">Blob URLs</a> needs to be light green (=supported) for a browser to support uploads larger then 2GB</p>

<hr />
<h4 id="7132202d207369746520776f726b732077697468206874747020627574206e6f7420776974682068747470732c20756e636c65617220666c617368206572726f72732e">Q2 - Site works with HTTP but not with HTTPS, unclear Flash errors.</h4>

<p>Observed behaviour:</p>

<p>Flash error pop-ups like &quot;<a href="/spaces/file_sender/tickets/2038">#2038</a> IO Error&quot; but also other error numbers have been observed. Also:</p>

<pre>
<span style="font-family: courier new,courier;">I can log in, fill in blank fields, select file to upload, but when I</span><span style="font-family: courier new,courier;"> click send, I immediately get the message:

Uploading ubuntu-9.10-server-amd64.iso...
File uploaded
Moving File</span>

<span style="font-family: courier new,courier;">The progress bar remains 0%.</span></pre>

<p><strong>A - This problem usually occurs when a self-signed SSL server certificate is used which Flash doesn&#39;t like.&nbsp; </strong></p>

<p>When Flash wants to verify a certificate it looks in the OS specific system certificate store for a trusted &#39;root&#39; certicate to verify against (note that when using for example FireFox or Opera this will <strong>not</strong> be the certificate store used by the browser). When using a self signed certificate there most likely won&#39;t be a trusted root certificate. You can ask your users to put your self signed certificate in the &#39;system certificate store&#39; (for Windows the MS &quot;Trusted Root Certification Authorities&quot; store and for Mac OSX in the &quot;system key chain&quot;). After that Flash, even when used with Firefox or Opera seems to be happy when uploading over SSL.&nbsp; A better solution is to get a real SSL server certificate that&#39;s recognised by all major operating systems.</p>

<hr />
<h4 id="7133202d2066697265666f7820637261736865732077697468206c6172676520646f776e6c6f6164733f">Q3 - FireFox crashes with large downloads?</h4>

<p><strong>A</strong><strong> - Using FireFox</strong></p>

<p>Disable<strong> </strong>the<strong> FireBug </strong>plugin as it causes FireFox to store the download in memory and will crash when you run out of RAM.</p>

<p>&nbsp;</p>

<hr />
<h4 id="3c61206e616d653d22756e646566696e6564253230696e6465782532306174747269627574656e616d65223e3c2f613e7134202d20696e20746865206c6f6766696c652069207365653a20222a6572726f723a205b385d20756e646566696e656420696e6465783a20266c743b2f6174747269627574656e616d652f2667743b2a222e207768617420646f6573206974206d65616e3f"><a name="Undefined%20index%20AttributeName"></a>Q4 - In the logfile I see: &quot;*Error: <a href="https://www.assembla.com/code/file_sender/subversion/changesets/8">[8]</a> Undefined index: &lt;/AttributeName/&gt;*&quot;. What does it mean?</h4>

<p><strong>A - You likely need to tell SimpleSamlPHP how to handle certain attributes</strong></p>

<pre>
First, check if the IdP is sending the attribute mentioned by /AttributeName/.
If no, ask the IdP administrator to add this attribute to the allowed-to-send list.
If yes, check which format the IdP uses to send the attributes. It will be either 
oid- or urn-format.
By default, simplesamlphp is configured to translate from &quot;oid to attribute name&quot;.
As many IdPs use urn-format only, it is recommended to enable the translation from 
&quot;urn to attribute name&quot; as well.
You can do this by adding the text below in bold to the simplesamlphp configuration file (i.e.
..//simplesamlphp/config/config.php/)

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; /*
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; * Authentication processing filters that will be executed for all IdPs
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; * Both Shibboleth and SAML 2.0
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; */
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &#39;authproc.sp&#39; =&gt; array(
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; 10 =&gt; array(
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &#39;class&#39; =&gt; &#39;core:AttributeMap&#39;, &#39;oid2name&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ),
*15 =&gt; array(
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &#39;class&#39; =&gt; &#39;core:AttributeMap&#39;, &#39;urn2name&#39;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ),*</pre>

<hr />
<h4 id="7135202d20646f65732066696c6573656e6465722068617665206d6f7265207468616e206f6e652061757468656e7469636174696f6e206d6f64653f">Q5 - Does FileSender have more than one authentication mode?</h4>

<p><strong>A - Users can authenticate in two ways to the system:</strong></p>

<ol>
	<li>through one of the supported AuthN mechanisms</li>
	<li>using an upload voucher that an authenticated user gave them</li>
</ol>

<hr />
<h4 id="7136202d20686f7720746f20717569636b6c79206372656174652062696720746573742066696c65733f">Q6 - How to quickly create big test files?</h4>

<p><strong>A - On a Windows machine this is straight forward:</strong> to create a file of a certain size and if the file contents don&#39;t matter, you can use the Fsutil command as follows:</p>

<div class="KonaBody">
<pre>
fsutil file createnew &lt;name of file&gt; &lt;size in bytes&gt;</pre>

<p>For example,</p>

<pre>
fsutil file createnew d:\temp\10GBfile.txt 10737418240</pre>

<p>creates a 10GB file named 10GBfile.txt in the d:\temp folder.</p>

<p>More practical examples:</p>

<pre>
<span style="font-family: courier new,courier;">D:\&gt;fsutil file createnew 90GBfile.txt 96636764160
File D:\90GBfile.txt is created

D:\&gt;fsutil file createnew 4.7GBfile.txt 504658652
File D:\4.7GBfile.txt is created

D:\&gt;fsutil file createnew 1GBfile.txt 1073741824
File D:\1GBfile.txt is created

D:\&gt;fsutil file createnew 100MBfile.txt 104857000
File D:\100MBfile.txt is created

D:\&gt;fsutil file createnew 500MBfile.txt 524288000
File D:\500MBfile.txt is created

D:\&gt;fsutil file createnew 50MBfile.txt 52428800
File D:\50MBfile.txt is created

D:\&gt;fsutil file createnew 5MBfile.txt 5242880
File D:\5MBfile.txt is created</span></pre>
</div>

<p><input id="frmContentID" name="frmContentID" type="hidden" value="40935" /></p>

<div id="lxTdivRating">&nbsp;
<p><strong>A - On a Mac and Linux</strong></p>

<p>In a terminal window</p>

<p>dd if=/dev/urandom of=testfile.dat bs=1024 count=1024</p>

<p>&#39;if&#39; is InputFile, &#39;of&#39; is OutputFile, &#39;bs&#39; is BlockSize (in bytes) and &#39;count&#39; is the number of blocks (of size &#39;bs&#39;) to write. As input in this example you get random data (from the pseudofile /dev/urandom). You could speed up the process a little by creating a file with &#39;zeroes&#39;. In that case you can use &#39;if=/dev/zero&#39;. I prefer &#39;random&#39; data because it is more &#39;realistic&#39; data (a file of only zeroes can and will be highly compressed with up- and downloads, random data resembles more an already compressed file like a zip-archive).<br />
&nbsp;</p>

<hr />
<h4 id="7137202d2075706c6f61642073746f7073206166746572203820686f7572733f">Q7 - Upload stops after 8 hours?</h4>

<p><strong>A:&nbsp; The standard session duration timeout of SimpleSamlPHP is 8 hours.</strong>&nbsp; When uploading using Gears, the PHP code at the backend checks the authentication status for every uploaded chunk.&nbsp; If the session is longer then the session timeout of SimpleSamlPHP, the upload stops.&nbsp; Increase the value of the session duration variable in your simplesaml config.php (session.duration) to a value that will cover the estimated upload time period.</p>

<p>&nbsp;</p>

<hr />
<h4 id="7138202d202f6574632f63726f6e2e6461696c792f66696c6573656e646572207068702064657072656361746564207761726e696e67206f6e207562756e74753f">Q8 - /etc/cron.daily/filesender PHP Deprecated warning on Ubuntu?</h4>

<p>On Ubuntu the daily cronjob reports:</p>

<pre>
/etc/cron.daily/filesender: PHP Deprecated:&nbsp; Comments starting with &#39;#&#39; are deprecated in /etc/php5/cli/conf.d/mcrypt.ini on line 1 in Unknown on line 0</pre>

<p><strong>A - This is a bug in the PHP version on Ubuntu.</strong> See <a href="https://bugs.launchpad.net/ubuntu/+source/php-mcrypt/+bug/540208">https://bugs.launchpad.net/ubuntu/+source/php-mcrypt/+bug/540208</a><br />
Until the bug is fixed just replace # with ; in /etc/php5/conf.d/mcrypt.ini.</p>

<hr />
<h4 id="7139202d2075706c6f616473206172652072656c61746976656c7920736c6f773f">Q9 - Uploads are relatively slow?</h4>

<p>Uploading large files is relatively slow when compared with downloading. Can this be improved?</p>

<p><strong>A - There are a few things that might help:</strong></p>

<ul>
	<li>Check your debug settings in config.php. Disabling debug logging and client_specific_logging will in general improve upload performance:</li>
</ul>

<div id="lxTdivRating" style="padding-left: 60px;"><span style="font-family: courier new,courier;">$config[&quot;debug&quot;] = false;</span></div>

<div style="padding-left: 60px;"><span style="font-family: courier new,courier;">$config[&quot;client_specific_logging&quot;] = false;</span></div>
</div>

<div>
<ul>
	<li>For improving the Gears upload you can increase the CHUNK_BYTES parameter in www/js/fs_gears.js (requires manual edit)</li>
</ul>
</div>

<div style="padding-left: 60px;"><span style="font-family: courier new,courier;">var CHUNK_BYTES&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; = 2000000;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; //&nbsp; 2MB (default is 2000000 = 2MB)</span></div>

<div style="padding-left: 30px;">Values larger than 2 to 5 MB will not make much difference anymore and will make the upload progress bar taking less and larger steps.</div>

