<ul>
	<li><a class="wiki_link" href="#overview" title="Overview">Overview</a></li>
	<li><a class="wiki_link" href="#versions_tested" title="Versions Tested">Versions Tested</a></li>
	<li><a class="wiki_link" href="#62726f7773657220666c61736820706c7567696e2c206a6176617363726970742073657474696e677320616e642068746d6c3520646574656374696f6e" title="Browser Flash plugin, Javascript settings and HTML5 detection">Browser Flash plugin, Javascript settings and HTML5 detection</a></li>
	<li><a class="wiki_link" href="#authenticated_only" title="Authenticated only">Authenticated only</a>
	<ul>
		<li><a class="wiki_link" href="#authentication_-_logon" title="Authentication - Logon">Authentication - Logon</a></li>
		<li><a class="wiki_link" href="#697373756520766f7563686572732c2073696e676c6520616e64206d756c7469706c6520726563697069656e74732073657061726174656420627920636f6c6f6e202f2073656d69636f6c6f6e" title="Issue vouchers, single and multiple recipients separated by colon / semicolon">Issue vouchers, single and multiple recipients separated by colon / semicolon</a></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#authenticated_and_using_a_voucher" title="Authenticated and using a voucher">Authenticated and using a voucher</a>
	<ul>
		<li><a class="wiki_link" href="#61736369692066696c652075706c6f61642c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e74732c2075706c6f61642070726f6d707473" title="ASCII file upload, single recipient, default field contents, upload prompts">ASCII file upload, single recipient, default field contents, upload prompts</a></li>
		<li><a class="wiki_link" href="#69736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382066696c652075706c6f61642c2074776f20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473" title="ISO-8859-1 / non-ISO-8859-1 UTF8 file upload, two recipients separated by comma / semi-colon, custom field contents">ISO-8859-1 / non-ISO-8859-1 UTF8 file upload, two recipients separated by comma / semi-colon, custom field contents</a></li>
		<li><a class="wiki_link" href="#63616e63656c20616e6420726573746172742028666c61736829206f7220726573756d65202868746d6c35292061757468656e746963617465642075706c6f61642c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473" title="Cancel and restart (Flash) or resume (HTML5) authenticated upload, single recipient, custom field contents">Cancel and restart (Flash) or resume (HTML5) authenticated upload, single recipient, custom field contents</a></li>
		<li><a class="wiki_link" href="#6c617267652066696c652075706c6f6164206f76657220322067622c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473202868746d6c35206f6e6c7929" title="large file upload over 2 GB, single recipient, default field contents (HTML5 only)">large file upload over 2 GB, single recipient, default field contents (HTML5 only)</a></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#authenticated_only" title="Authenticated only">Authenticated only</a>
	<ul>
		<li><a class="wiki_link" href="#re-send_new_email" title="Re-Send New Email">Re-Send New Email</a></li>
		<li><a class="wiki_link" href="#616464206e657720726563697069656e742c2061736369692c2073696e676c6520726563697069656e742c206f726967696e616c206669656c6420636f6e74656e7473" title="Add New Recipient, ASCII, single recipient, original field contents">Add New Recipient, ASCII, single recipient, original field contents</a></li>
		<li><a class="wiki_link" href="#616464206e657720726563697069656e742c2069736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382c2074776f20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473" title="Add New Recipient, ISO-8859-1 / non-ISO-8859-1 UTF8, two recipients separated by comma / semi-colon, custom field contents">Add New Recipient, ISO-8859-1 / non-ISO-8859-1 UTF8, two recipients separated by comma / semi-colon, custom field contents</a></li>
		<li><a class="wiki_link" href="#delete_file" title="Delete File">Delete File</a></li>
		<li><a class="wiki_link" href="#delete_voucher" title="Delete Voucher">Delete Voucher</a></li>
		<li><a class="wiki_link" href="#authentication_-_logoff" title="Authentication - Logoff">Authentication - Logoff</a></li>
	</ul>
	</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="overview">Overview</h2>

<p>The following provides a list of considerations and workflows for and during testing of the local configuration and functionality of FileSender prior to the 1.1 release. <span style="background-color: rgb(255, 0, 0);"><span style="background-color: rgb(255, 255, 255);">See <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows_for_v1-0-1" title="Test Workflows for v1-0-1">Test Workflows for v1-0-1</a> for tests conducted for the 1.01 release, and <span style="background-color: rgb(255, 0, 0);"><span style="background-color: rgb(255, 255, 255);"> <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows_for_v1-5" title="Test Workflows for v1-5">Test Workflows for v1-5</a> for tests</span></span> planned for the 1.5 release. </span></span></p>

<p>These tests are based primarily on usage by <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a> of the <a href="http://www.aarnet.edu.au/"> AARNet</a> installation of FileSender. Contributions to these workflows also provided by <a href="https://www.assembla.com/profile/xjansen"> Xander Jansen</a> based on the <a href="http://www.surfnet.nl">SURFnet</a> installation of FileSender.</p>

<p>Please note that these test workflows may not represent an exhaustive list of all possible user actions. Also, some aspects of these workflows may become no longer applicable as FileSender develops. If you find anything incorrect, please advise, or correct it yourself if you have access.</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="versions_tested">Versions Tested</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>FileSender Release</b></td>
			<td><b>Installation</b></td>
			<td><b>Testing Status</b></td>
			<td><b>Notes</b></td>
			<td><b>OS</b></td>
			<td><b>Browser</b></td>
			<td><b>HTML5 or Flash?</b></td>
			<td><b>Conducted by</b></td>
		</tr>
		<tr>
			<td rowspan="5">1.1</td>
			<td><a href="https://filesender.surfnet.nl/special" target="_blank">https://filesender.surfnet.nl/special</a> &nbsp;</td>
			<td>Complete</td>
			<td>Full set as detailed below, except for uploading files over 2GB</td>
			<td>OSX 10.6.8</td>
			<td>Firefox 7.0.1</td>
			<td>HTML5</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td><a href="https://filesender.surfnet.nl/special" target="_blank">https://filesender.surfnet.nl/special</a> &nbsp;</td>
			<td>Complete</td>
			<td>Full set as detailed below, except for uploading files over 2GB (which is not possible with Flash only)</td>
			<td>OSX 10.6.8</td>
			<td>Safari 5.1.1</td>
			<td>Flash 11.0.1.152</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td rowspan="3"><a href="https://filesender.surfnet.nl/special" target="_blank">https://filesender.surfnet.nl/special</a> &nbsp;</td>
			<td rowspan="3">Complete</td>
			<td rowspan="3">Uploading files over 2 GB (authenticated &amp; using voucher)</td>
			<td>&nbsp;OSX 10.5.8</td>
			<td>&nbsp;Firefox 7.0.1</td>
			<td>&nbsp;HTML5</td>
			<td rowspan="3"><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a></td>
		</tr>
		<tr>
			<td>&nbsp;Ubuntu Lucid</td>
			<td>&nbsp;Chrome 15.0.874.54 beta</td>
			<td>&nbsp;HTML5</td>
		</tr>
		<tr>
			<td>&nbsp;Windows 7</td>
			<td>&nbsp;Chrome 14.0.835.202 m</td>
			<td>&nbsp;HTML5</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
	</tbody>
</table>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="62726f7773657220666c61736820706c7567696e2c206a6176617363726970742073657474696e677320616e642068746d6c3520646574656374696f6e">Browser Flash plugin, Javascript settings and HTML5 detection</h2>

<ul>
	<li>disable Flash plugin and restart browser</li>
	<li>load FileSender logon page, prompt should appear <span style="color: rgb(102, 102, 153);">&quot;Install Flash Player. This application requires Flash Player. To install Flash Player go to Adobe.com&quot;</span> with a link to <span style="color: rgb(102, 102, 153);">&quot;Get Flash&quot;</span></li>
	<li>re-enable Flash plugin and restart browser</li>
	<li>disable Javascript in browser (e.g. Firefox on Mac under Preferences &gt; Content)</li>
	<li>load FileSender logon page again, prompt should appear <span style="color: rgb(102, 102, 153);">&quot;JavaScript is turned off in your web browser. This application will not run without Javascript enabled in your web browser.&quot;</span></li>
	<li>re-enable Javascript (no need to restart browser)</li>
	<li>load FileSender logon page again</li>
	<li>verify whether&nbsp;&quot;HTML5 [tick]&quot; or &quot;HTML5 X&quot; icon is displayed in top right-hand corner, which indicates whether the browser (version) does support HTML5 or does not (Flash only)</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="--_authenticated_only_--">-- Authenticated only --</h2>

<h3 id="authentication_-_logon">Authentication - Logon</h3>

<ul>
	<li>verify that page cannot be reached by http - should be accessible via https only</li>
	<li>click on the About and Help links and verify content, before logging on to FileSender</li>
	<li>logon</li>
	<li>click on the About and Help links again and verify content again after logon</li>
	<li>verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;</li>
</ul>

<h3 id="697373756520766f7563686572732c2073696e676c6520616e64206d756c7469706c6520726563697069656e74732073657061726174656420627920636f6c6f6e202f2073656d69636f6c6f6e">Issue vouchers, single and multiple recipients separated by colon / semicolon</h3>

<ul>
	<li>click on &ldquo;Vouchers&rdquo; button</li>
	<li>verify that explanatory text about how to use Vouchers is present</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Send Voucher&rdquo; button - prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Message. Please check email address&rdquo;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>in the &ldquo;Send Vouchers to:&rdquo; field, enter recipient email address</li>
	<li>click on &ldquo;Send Voucher&rdquo; button - prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Voucher Sent&rdquo;</span> - click on &ldquo;OK&rdquo; button</li>
	<li>verify that issued voucher is now listed in Vouchers table</li>
	<li>verify that email notification with &ldquo;Voucher&rdquo; in the title is sent to both sender and recipient, and that text is correct</li>
	<li><b>repeat</b> to create four more vouchers</li>
	<li><b>repeat</b> with two recipients separated by a comma, to delete manually later</li>
	<li><b>repeat</b> with two recipients separated by a semicolon, setting the expiry date to the next calendar day to verify automatic expiration</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="--_authenticated_and_using_a_voucher_--" style="text-align: left;">-- Authenticated and using a voucher --</h2>

<p><b>For voucher uploads, ensure that:</b> you are recognised as &quot;Guest&quot; for both uploads and downloads (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear; use a recipient email addresses different from that of the authenticated voucher issuer and recipient(s), for testing bcc email to voucher issuer<span style="color: rgb(102, 102, 153);"><span style="color: rgb(0, 0, 0);"> (</span></span>bcc of each email is sent to voucher issuer in addition to voucher recipient and uploaded file recipients).</p>

<h3 id="61736369692066696c652075706c6f61642c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e74732c2075706c6f61642070726f6d707473">ASCII file upload, single recipient, default field contents, upload prompts</h3>

<ul>
	<li>title of panel should be &quot;Upload&quot; (Flash only) or &quot;HTML5 Upload&quot; (HTML5)</li>
	<li>leave &ldquo;To&rdquo; field blank, verify tooltip <span style="color: rgb(102, 102, 153);">&quot;Multiple email addresses can be entered separated by comma or semi-colon (, or ;)&quot;</span></li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>leave &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields blank or default (&quot;Voucher&quot; for voucher), to verify defaults</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select the following file sizes (ASCII only):
	<ul>
		<li>zero KB - prompt should appear <span style="color: rgb(102, 102, 153);">&quot;Message - Cannot upload a file of 0 bytes. Please select another file&quot;</span>, &quot;Send&quot; button should *not* appear</li>
		<li>.exe file - prompt should appear <span style="color: rgb(102, 102, 153);">&quot;Invalid file extension - File extension type is invalid or is missing. You may like to zip the file and try again.&quot;</span></li>
		<li>2 GB (and 1 MB below), 4 GB (and 1 MB below), 5 GB and over 5GB<br />
		<b>- Flash only</b> - for files 2 Gb and over, prompt should appear <span style="color: rgb(102, 102, 153);">&quot;File is too large. Please use a HTML5 enabled browser. (Maximum without HTML5: 2.00 GB)&quot;</span>, &quot;Send&quot; button should *not* appear<br />
		<b>- HTML5</b> - over the configured HTML5 limit, prompt should appear <span style="color: rgb(102, 102, 153);">&quot;File size is too large (Max: [X] GB)&quot;<span style="color: rgb(0, 0, 0);">&nbsp;(where X is the configured maximum), &quot;Send&quot; button should *not* appear</span></span></li>
		<li>small ASCII text file&nbsp; - file size should be displayed, &ldquo;Send&rdquo; button *should* now appear</li>
	</ul>
	</li>
	<li>do not check the &ldquo;I accept the terms and conditions of this service&rdquo; (AuP) box, click on &ldquo;Send&rdquo; button - prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Message. Please check email address&rdquo;</span></li>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>do not check the AuP box, click on &ldquo;Send&rdquo; button - prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Message. You MUST agree to the terms and conditions.&rdquo;</span></li>
	<li>read the AuP terms and conditions, check the AuP box</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear, when complete new page should be displayed with text <span style="color: rgb(102, 102, 153);">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
	<li>click on the filename in the My Files table of uploaded ASCII file</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button</li>
	<li>verify that file has downloaded and can be opened</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li>click on link in email again to verify that the file can be downloaded more than once (no additional download notification emails would be triggered)</li>
	<li><b>repeat</b> using voucher</li>
</ul>

<h3 id="69736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382066696c652075706c6f61642c20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">ISO-8859-1 / non-ISO-8859-1 UTF8 file upload, recipients separated by comma / semi-colon, custom field contents</h3>

<ul>
	<li>repeat the following for these uploaded file entries:
	<ul>
		<li><a href="/spaces/file_sender/documents/drg4ko9Ryr37zXeJe5cbCb/download?filename=utf8-iso8859-1-%C3%A7%C3%9F%C3%B8%C3%BE-test.txt">utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt</a> - ISO-8859-1 file, recipients separated by comma, custom &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields with <b>&lt;tag&gt; bl&aring;b&aelig;rsyltet&oslash;y &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></li>
		<li><a href="/spaces/file_sender/documents/dNfthu9Ryr35RVeJe5cbCb/download?filename=utf8-latin-extended-a-%C5%A1%C5%99%C5%AC%C5%B4-test.txt">utf8-latin-extended-a-šřŬŴ-test.txt</a> - non-ISO-8859-1 UTF8 file, recipients separated by semi-colon), custom &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields with <b>&lt;tag&gt; žćčđ&scaron; &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></li>
	</ul>
	</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s address</li>
	<li>enter over the configured maximum number of recipient email addresses in the &ldquo;To&rdquo; field, separated by &quot;, &quot; or &quot;; &quot; as detailed above</li>
	<li>enter subject and message, as detailed above</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select file - filename and size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session) (check box when using a voucher)</li>
	<li>click on &ldquo;Send&rdquo; button - message should appear <span style="color: rgb(102, 102, 153);">&quot;The maximum number of email addresses allowed is [X]&quot;</span> (where X is the configured maximum)</li>
	<li>enter two recipient email addresses, separated by &quot;, &quot; or &quot;; &quot; as detailed above, and click on &quot;Send&quot; button again</li>
	<li>progress bar should appear, when complete new page should be displayed with text <span style="color: rgb(102, 102, 153);">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and both recipients, and that the content matches the input, with a different url for each recipient</li>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly (with no white space infront of second email address)</li>
	<li>for voucher, verify that voucher has been deleted from Voucher list, and click on voucher link again to verify that voucher cannot be used a second time - text should appear <span style="color: rgb(102, 102, 153);">&quot;This file/voucher is no longer available&quot;</span></li>
	<li>click on the link to the file in one of the emails generated by authenticated upload</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by email addresses of selected recipient</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email address of sender</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - <span style="color: rgb(102, 102, 153);">&ldquo;Your file should start downloading<span style="color: rgb(0, 0, 0);">&rdquo; should appear</span></span></li>
	<li>verify that file has downloaded and can be opened, and that non-ASCII characters are preserved in filename</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li><b>repeat</b> using voucher</li>
</ul>

<h3 id="63616e63656c20616e6420726573746172742028666c61736829206f7220726573756d65202868746d6c35292061757468656e746963617465642075706c6f61642c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Cancel and restart (Flash) or resume (HTML5) authenticated upload, single recipient, custom field contents</h3>

<ul>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>enter into &quot;Subject&quot; and &quot;Message&quot; fields <b>&lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select a largish file (~10 MB should be enough) - file size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session) (check box when using a voucher)</li>
	<li>click on &ldquo;Send&rdquo; button but cancel / pause upload (using cancel button) before completion</li>
	<li>verify that buttons across top of page reappear for authenticated upload, and that all fields reset</li>
	<li>re-enter recipient address, select expiry date and browse for file again and click on &quot;Send&quot; button - progress bar should appear, file upload should start from the beginning for Flash only (0%) or from point where upload was paused for HTML5, when complete new page should be displayed with text <span style="color: rgb(102, 102, 153);">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
	<li>click on the link to file in email generated by restarted authenticated upload</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by email addresses of recipient</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email address of sender</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - <span style="color: rgb(102, 102, 153);">&ldquo;Your file should start downloading&rdquo;<span style="color: rgb(0, 0, 0);"> should appear</span></span></li>
	<li>verify that file has downloaded and can be opened</li>
	<li>compare MD5 / SHA-1 etc. hash for uploaded and downloaded file</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li><b>repeat</b> using voucher</li>
</ul>

<h3 id="6c617267652066696c652075706c6f6164206f76657220322067622c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473202868746d6c35206f6e6c7929">large file upload over 2 GB, single recipient, default field contents (HTML5 only)</h3>

<ul>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select a file over 2 GB - file size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session) (check box when using a voucher)</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear, when complete new page should be displayed with text <span style="color: rgb(102, 102, 153);">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
	<li>click on the link in email generated by authenticated large file upload over 2 GB using HTML5</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by recipient&#39;s email address</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by sender&#39;s email address</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - <span style="color: rgb(102, 102, 153);">&ldquo;Your file should start downloading&rdquo;<span style="color: rgb(0, 0, 0);"> should appear</span></span></li>
	<li>verify that file has downloaded and can be opened</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li>compare MD5 / SHA-1 etc. hash for uploaded and downloaded file</li>
	<li><b>repeat</b> using voucher</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="--_authenticated_only_--">-- Authenticated only --</h2>

<h3 id="re-send_new_email">Re-Send New Email</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to the uploaded ASCII file entry, click on &ldquo;Re-Send Email&rdquo; button on the left - a prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Re-send. Are you sure you want to re-send this Email?&rdquo;</span>, click on &ldquo;Cancel&rdquo; button, view should return to table</li>
	<li>click on &ldquo;Re-Send Email&rdquo; button again, click on &ldquo;OK&rdquo; button, another prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Email has been sent&rdquo;</span></li>
	<li>verify receipt of email to both sender and recipient(s)</li>
</ul>

<h3 id="616464206e657720726563697069656e742c2061736369692c2073696e676c6520726563697069656e742cc2a06f726967696e616c206669656c6420636f6e74656e7473">Add New Recipient, ASCII, single recipient,&nbsp;original field contents</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>click on &ldquo;Add New Recipient&rdquo; button to the left of uploaded ASCII file entry - a prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Add Recipient&rdquo;</span>:</li>
	<li>leave &ldquo;To&rdquo; field blank</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>leave &ldquo;Subject&rdquo; and &quot;Message&quot; fields unchanged, as per original upload</li>
	<li>select expiry date</li>
	<li>verify that &ldquo;File to be Redistributed&rdquo; and &ldquo;Size&rdquo; fields are correct</li>
	<li>click on &ldquo;Send&rdquo; button</li>
	<li>prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Please check email address&quot;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>enter recipient one email address (only) in the &ldquo;To&rdquo; field, and click on &ldquo;Send&rdquo; button again</li>
	<li>another prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Email has been sent&rdquo;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table for new recipient and that details are displayed correctly</li>
</ul>

<h3 id="616464206e657720726563697069656e742c2069736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382c2074776f20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">Add New Recipient, ISO-8859-1 / non-ISO-8859-1 UTF8, two recipients separated by comma / semi-colon, custom field contents</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>repeat the following for these uploaded file entries:
	<ul>
		<li><a href="/spaces/file_sender/documents/drg4ko9Ryr37zXeJe5cbCb/download?filename=utf8-iso8859-1-%C3%A7%C3%9F%C3%B8%C3%BE-test.txt">utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt</a> - ISO-8859-1 file,&nbsp;two recipients separated by comma, custom &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields with <b>&lt;tag&gt; bl&aring;b&aelig;rsyltet&oslash;y &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></li>
		<li><a href="/spaces/file_sender/documents/dNfthu9Ryr35RVeJe5cbCb/download?filename=utf8-latin-extended-a-%C5%A1%C5%99%C5%AC%C5%B4-test.txt">utf8-latin-extended-a-šřŬŴ-test.txt</a> - non-ISO-8859-1 UTF8 file,&nbsp;two recipients separated by semi-colon, custom &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields with <b>&lt;tag&gt; žćčđ&scaron; &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></li>
	</ul>
	</li>
</ul>

<ul>
	<li>next to an uploaded file entry, click on &ldquo;Add New Recipient&rdquo; button on the left - a prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Add Recipient&rdquo;</span></li>
	<li>enter over the configured maximum number of recipient email addresses in the &ldquo;To&rdquo; field, separated by &quot;, &quot; or &quot;; &quot; as detailed above</li>
	<li>verify subject and message, as detailed above</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>select a different expiry date</li>
	<li>verify that &ldquo;File to be Redistributed&rdquo; and &ldquo;Size&rdquo; fields are correct</li>
	<li>click on &ldquo;Send&rdquo; button - message should appear <span style="color: rgb(102, 102, 153);">&quot;The maximum number of email addresses allowed is [X]&quot;</span> (where X is the configured maximum)</li>
	<li>enter two recipient email addresses, separated by &quot;, &quot; or &quot;; &quot; as detailed above, and click on &quot;Send&quot; button again</li>
	<li>progress bar should appear, when complete new page should be displayed with text <span style="color: rgb(102, 102, 153);">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipients, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly (with no white space infront of second email address)</li>
</ul>

<h3 id="delete_file">Delete File</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to the entry for an authenticated upload file, click on &ldquo;Delete&rdquo; button on the right - a prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Delete File. Are you sure?&rdquo;</span> - click on &ldquo;Cancel&rdquo; button, file should remain in table</li>
	<li>click on &ldquo;Delete&rdquo; button again and click on &ldquo;OK&rdquo; button - file should disappear from table</li>
	<li>verify that an email is sent to uploader and recipients advising that the file has been deleted</li>
	<li>verify that the file can no longer be accessed, message <span style="color: rgb(102, 102, 153);">&quot;This file / Voucher is no longer available&quot;</span></li>
	<li><b>repeat</b> for a file uploaded using a voucher and verify email advice</li>
</ul>

<h3 id="delete_voucher">Delete Voucher</h3>

<ul>
	<li>click on &quot;Vouchers&quot; button</li>
	<li>next to the last voucher that was issued (which may now be the only voucher listed), click on &ldquo;Delete&rdquo; button on the right - a prompt should appear <span style="color: rgb(102, 102, 153);">&ldquo;Delete Voucher. Are you sure?&rdquo;</span> - click on &ldquo;Cancel&rdquo; button, voucher should remain in table</li>
	<li>click on &ldquo;Delete&rdquo; button again and click on &ldquo;OK&rdquo; button - voucher should disappear from table</li>
	<li>verify that deleted voucher is no longer listed in Voucher list</li>
	<li>verify whether an email is sent to voucher issuer and voucher recipient, advising that the voucher has been cancelled</li>
	<li>click on the email link pertaining to the deleted voucher again, to verify that it can no longer be used - text should appear <span style="color: rgb(102, 102, 153);">&quot;This voucher has been cancelled&quot;</span></li>
</ul>

<h3 id="authentication_-_logoff">Authentication - Logoff</h3>

<ul>
	<li>before logging off, open a second FileSender tab in your browser, then logoff in one - if you refresh the tab in which you did not logoff, verify that you are logged out and are presented with the logon screen</li>
	<li>in the tab you logged out in, click on the &ldquo;Back&rdquo; button in your browser - verify that are you still logged out, and are presented with the logon screen.</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<p>My contributions to this project are as a Monash University user, beta-tester and release tester of the <a href="http://www.aarnet.edu.au/" target="_blank">AARNet, the Australian National Research and Educational Network (NREN)</a> and test installations of FileSender. I am not a developer of FileSender. -- <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>.</p>

