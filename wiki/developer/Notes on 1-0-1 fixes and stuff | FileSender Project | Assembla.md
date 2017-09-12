<h2 id="233337393a2069707636206c6f6767696e6720627567"><a href="/spaces/file_sender/tickets/379">#379</a>: IPv6 logging bug</h2>

<h3 id="defects">Defects</h3>

<p>1: the client IPv6 address wasn&#39;t stored in the logs db-table</p>

<p>2: the db column for the address was too short</p>

<h3 id="files_changed">Files changed</h3>

<pre>
classes/DB_Input_Checks.php
classes/Functions.php
scripts/filesender_db.sql</pre>

<h3 id="caveats">Caveats</h3>

<p>The fixes activate code that requires the gmp PHP module. This module is part of PHP since version 4.0.4 and is enabled on most if not all stock PHP installs. Can be checked with:</p>

<pre>
% php -r &#39;phpinfo(8);&#39; | grep -i gmp
gmp
gmp support =&gt; <strong>enabled</strong>
GMP version =&gt; 4.1.4</pre>

<h3 id="upgrade_notes">Upgrade notes</h3>

<p>When upgrading from previous versions you should fix the relevant column<br />
size in the database with:</p>

<pre>
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; #sudo -u postgres psql filesender
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ALTER TABLE files ALTER fileip6address TYPE character varying(45);
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; \q</pre>

<p>New installs will automatically create the correct column size. The code checks for the actual size of the fileip6address column and will truncate the address to be stored if the above ALTER TABLE statement isn&#39;t done on existing installs.</p>

<h3 id="testing_notes">Testing Notes</h3>

<p>Fixes have been tested on filesender.surfnet.nl. No specific additional testing required. QA check will be done by checking the other 1.0.1 tests done over IPv6.</p>

<h2 id="233338302c20233338392c20233339303a2066697820746865206d61785f67656172735f75706c6f61645f73697a6520636865636b"><a href="/spaces/file_sender/tickets/380">#380</a>, <a href="/spaces/file_sender/tickets/389">#389</a>, <a href="/spaces/file_sender/tickets/390">#390</a>: fix the max_gears_upload_size check</h2>

<h3 id="defect_and_fix">Defect and fix</h3>

<p>The check on the max_gears_upload_size configurable wasn&#39;t implemented. Fixed by adding a check in the Flash UI.</p>

<h3 id="files_changed">Files changed</h3>

<pre>
<em>flex/src/org/ricoshae/upload_gears.mxml</em>
www/swf/filesender.swf
</pre>

<h3 id="testing_notes">Testing notes</h3>

<p>With a Gears upload selecting empty files (0 bytes), files &gt; 2G on a Mac and files larger than the configured gears upload maximum should give an immediate popup stating that the file is too large (or empty) and the file should not be &#39;selected&#39; (i.e. filled in as file to be uploaded) and there should be no Send button.</p>

<h2 id="233338313a20616c6c6f77206d756c7469706c6520656d61696c2061646472657373657320746f2062652073657061726174656420627920626f7468206120636f6d6d6120616e6420612073656d692d636f6c6f6e"><a href="/spaces/file_sender/tickets/381">#381</a>: allow multiple email addresses to be separated by both a comma and a semi-colon</h2>

<h3 id="defect_and_fix">Defect and fix</h3>

<p>People seem to be used to ; as separator. To cater for this both the standard separator (comma) and the &#39;popular&#39; separator (semicolon) are now accepted. They can both be used.</p>

<h3 id="files_changed">Files changed</h3>

<pre>
<em>flex/src/org/ricoshae/newEmail.mxml
flex/src/org/ricoshae/vouchers.mxml
flex/src/org/ricoshae/upload_std.mxml
flex/src/org/ricoshae/upload_gears.mxml</em>
www/swf/filesender.swf</pre>

<h3 id="testing_notes">Testing Notes</h3>

<p>Multiple email addresses entered with a comma, a semicolon or a mix of both should be used as valid recipient addresses (i.e. generate multiple valid messages to the addresses entered and should be stored as separate entries for each recipient). This should work with both Flash and Gears uploads (authenticated and from a voucher) and with adding recipients to a file or sending a voucher. Tooltips should reflect the two separators in all cases.</p>

<h2 id="233338333a207472696d20737572726f756e64696e672077686974657370616365207769746820656d61696c206164726573736573"><a href="/spaces/file_sender/tickets/383">#383</a>: Trim surrounding whitespace with email adresses</h2>

<h3 id="defect_and_fix">Defect and fix</h3>

<p>Email addresses entered with whitespace where stored including the whitespace. This has been fixed by trimming surrounding whitespace.</p>

<h3 id="files_changed">Files changed</h3>

<pre>
<em>flex/src/org/ricoshae/upload_std.mxml
flex/src/org/ricoshae/upload_gears.mxml</em>
<em>flex/src/org/ricoshae/newEmail.mxml</em>
www/swf/filesender.swf</pre>

<h3 id="testing_notes">Testing Notes</h3>

<p>When entering multiple addresses with whitespace all addresses should be listed in the MyFiles table without whitespace (both after an upload or after adding recipients to a file)</p>

<h2 id="233237313a2073696d706c6573616d6c70687020312e372b20636f6d7061746962696c697479"><a href="/spaces/file_sender/tickets/271">#271</a>: SimpleSAMLphp 1.7+ compatibility</h2>

<h3 id="defect_and_fix">Defect and fix</h3>

<p>As of SSP 1.7 an additional cookie is required for SAML authentication. This cookie wasn&#39;t propagated when uploading with Flash. Code has been added to use the additional cookie when set and when uploading with Flash.</p>

<h3 id="affected_files">Affected files</h3>

<ul class="changes">
	<li>classes/AuthSaml.php</li>
	<li>flex/src/filesender.mxml&nbsp;</li>
	<li>flex/src/org/ricoshae/upload_std.mxml</li>
	<li>www/fs_uploadit.php</li>
</ul>

<h3 id="testing_notes">Testing notes</h3>

<p>Code changes should not interfere with existing installations using SSP &lt; 1.7+. Required tests against a SSP &lt; 1.7+ install can be restricted to &#39;flash-only&#39; uploads, both authenticated and from a voucher.</p>

<h2 id="233338343a206578706572696d656e74616c3a206d61696c20626f756e63652066756e6374696f6e616c697479"><a href="/spaces/file_sender/tickets/384">#384</a>: EXPERIMENTAL: Mail Bounce functionality</h2>

<p>This new functionality is not enabled by default and to enable it will require extra manual steps. The only changes against the files in te 1.0 codebase are in Mail.php (slightly modified sendemail function). All other files/code/config changes that are needed will be supplied in the 1.0.1 release but without changing anything.</p>

<p>Need to think about a non-intrusive way to do this, Work In progress.....</p>

<h3 id="changed_files">Changed files</h3>

<pre>
classes/Mail.php</pre>

<p>- Extra type parameter (not needed for normal operations, doesn&#39;t interfere with existing code)</p>

<p>- reshuffling of existing code, added some extra control statements and code to handle bounce notifications.</p>

<h3 id="changes_when_not_activated">Changes when NOT activated</h3>

<p>- Reply-To: header in outgoing mail has been removed</p>

<p>- A X-FileSenderUID: header is now added in all outgoing mails containing the UID of the file/voucher</p>

<h3 id="added_files">Added files</h3>

<pre>
cron/emailbouncehandler.php</pre>

<h3 id="extra_directory_tree_needed_when_activated">Extra directory tree needed when activated</h3>

<p>This shouldn&#39;t be in the 1.0.1 packages but need to be manually created.</p>

<pre>
&lt;filesender-base&gt;/maildrop/new
&lt;filesender-base&gt;/maildrop/done
&lt;filesender-base&gt;/maildrop/failure</pre>

<h3 id="config.php_changes_needed_for_activation">config.php changes needed for activation</h3>

<p>The following directives should be added to config.php (could be supplied as a separate file to be manually inserted)</p>

<pre>

&nbsp;</pre>

<pre class="lang-php prettyprint" style="background-color: transparent; overflow: visible; font-family: Monaco,'Bitstream Vera Sans Mono',monospace,Courier; line-height: normal; white-space: pre-wrap; width: 1265px; padding: 0px; margin: 0px; border: 0px solid #888888;">
<span class="pln" style="color: #000000; padding: 0px; margin: 0px;">&nbsp; &nbsp; &nbsp; &nbsp; </span><span class="com" style="color: #880000; padding: 0px; margin: 0px;">// email bounce handling</span></pre>
<br />
<span class="pln" style="padding: 0px; margin: 0px;">&nbsp; &nbsp; &nbsp; &nbsp; $config</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">[</span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&#39;return_path&#39;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">]</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">=</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&quot;&quot;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">;</span><br />
<span class="pln" style="padding: 0px; margin: 0px;">&nbsp; &nbsp; &nbsp; &nbsp; $config</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">[</span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&#39;emailbounce_location&#39;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">]</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">=</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&#39;/usr/share/filesender/maildrop/new&#39;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">;</span><br />
<span class="pln" style="color: #000000; padding: 0px; margin: 0px;">&nbsp; &nbsp; &nbsp; &nbsp; $config</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">[</span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&#39;emailbounce_subject&#39;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">]</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">=</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&quot;{siteName}: Email notification sending failure&quot;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">;</span><br />
&nbsp;
<pre class="lang-php prettyprint" style="background-color: transparent; overflow: visible; font-family: Monaco,'Bitstream Vera Sans Mono',monospace,Courier; line-height: normal; white-space: pre-wrap; width: 1265px; padding: 0px; margin: 0px; border: 0px solid #888888;">

&nbsp;</pre>

<pre class="lang-php prettyprint" style="background-color: transparent; overflow: visible; font-family: Monaco,'Bitstream Vera Sans Mono',monospace,Courier; line-height: normal; white-space: pre-wrap; width: 1265px; padding: 0px; margin: 0px; border: 0px solid #888888;">

&nbsp;</pre>

<pre class="lang-php prettyprint" style="background-color: transparent; overflow: visible; font-family: Monaco,'Bitstream Vera Sans Mono',monospace,Courier; line-height: normal; white-space: pre-wrap; width: 1265px; padding: 0px; margin: 0px; border: 0px solid #888888;">
<span class="pun" style="color: #666600; padding: 0px; margin: 0px;"><span class="pun" style="color: #666600; padding: 0px; margin: 0px;"><span class="pln" style="color: #000000; padding: 0px; margin: 0px;">&nbsp; &nbsp; &nbsp; &nbsp; $config</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">[</span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&#39;bouncenotification&#39;</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">]</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">=</span><span class="pln" style="color: #000000; padding: 0px; margin: 0px;"> </span><span class="str" style="color: #008800; padding: 0px; margin: 0px;">&#39;{CRLF}--simple_mime_boundary{CRLF}Content-type:text/plain; charset={charset}{CRLF}{CRLF}
Dear Sir, Madam,

The {siteName} service attempted to send an email to {fileoriginalto} on your behalf.

The message was rejected by the remote site, the most common reason
being an error in the email address entered for the recipient.

Please log into {siteName} to check the recipient address.

{siteName} allows adding new recipients to files without needing to upload the file again, from the table in &quot;My Files&quot;. In the case of Vouchers however, a new voucher must be issued.

Best regards,

{siteName}{CRLF}{CRLF}--simple_mime_boundary{CRLF}Content-type:text/html; charset={charset}{CRLF}{CRLF}
&lt;HTML&gt;
&lt;HEAD&gt;
&lt;meta http-equiv=&quot;Content-Type&quot; content=&quot;text/html;charset={charset}&quot;&gt;
&lt;/HEAD&gt;
&lt;BODY&gt;
&lt;P&gt;Dear Sir, Madam,&lt;/P&gt;
&lt;P&gt;The {siteName} service attempted to send an email to {fileoriginalto} on your behalf.&lt;/P&gt;
&lt;P&gt;The message was rejected by the remote site, the most common reason
being an error in the email address entered for the recipient.&lt;/P&gt;
&lt;P&gt;Please log into {siteName} to check the recipient address.&lt;/P&gt;
&lt;P&gt;{siteName} allows adding new recipients to files without needing to upload the file again, from the table in &quot;My Files&quot;. In the case of Vouchers however, a new voucher must be issued.&lt;/P&gt;
&lt;P&gt;Best regards,&lt;/P&gt;
&lt;P&gt;{siteName}&lt;/P&gt;
&lt;/BODY&gt;
&lt;/HTML&gt;{CRLF}{CRLF}--simple_mime_boundar</span><span class="pun" style="color: #666600; padding: 0px; margin: 0px;">y</span></span></span></pre>
<span class="pun" style="color: #666600; padding: 0px; margin: 0px;"><span class="pun" style="color: #666600; padding: 0px; margin: 0px;"> </span> </span>

<h3 id="testing_notes">Testing Notes</h3>

<p>All mail sending functions should be tested against an install <strong>without </strong>the functionality activated, i.e. with a normal 1.0 config.php (unaltered) and without the extra scripts and directory trees. The only visible changes should be the extra X-FileSenderUID: header and the lack of a Reply-To: header.</p>

<p><strong>To be determined</strong></p>

<p>script to create maildrop tree?</p>

<p>sample config-experimental.php files?</p>

<p>sample cronjob file?</p>

