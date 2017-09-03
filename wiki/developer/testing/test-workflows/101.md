<ul>
	<li><a class="wiki_link" href="#overview" title="Overview">Overview</a></li>
	<li><a class="wiki_link" href="#versions_tested" title="Versions Tested">Versions Tested</a></li>
	<li><a class="wiki_link" href="#features_to_be_tested" title="Features to be Tested">Features to be Tested</a></li>
	<li><a class="wiki_link" href="#test_matrix" title="Test Matrix">Test Matrix</a></li>
	<li><a class="wiki_link" href="#62726f7773657220666c61736820706c7567696e2026616d703b206a6176617363726970742073657474696e677320646574656374696f6e" title="Browser Flash plugin &amp; Javascript settings detection">Browser Flash plugin &amp; Javascript settings detection</a></li>
	<li><a class="wiki_link" href="#612e20666c617368202d2061757468656e746963617465642075706c6f6164732026616d703b206173736f63696174656420677565737420646f776e6c6f616473" title="A. Flash - authenticated uploads &amp; associated Guest downloads">A. Flash - authenticated uploads &amp; associated Guest downloads</a></li>
	<li><a class="wiki_link" href="#622e20666c617368202d20697373756520766f7563686572732c2067756573742075706c6f6164732026616d703b206173736f63696174656420677565737420646f776e6c6f616473" title="B. Flash - issue vouchers, Guest uploads &amp; associated Guest downloads">B. Flash - issue vouchers, Guest uploads &amp; associated Guest downloads</a></li>
	<li><a class="wiki_link" href="#632e206765617273202d2061757468656e746963617465642075706c6f6164732c2075706c6f616473207573696e6720766f75636865722c20706175736520616e6420726573756d652075706c6f61647320616e64206173736f63696174656420646f776e6c6f616473" title="C. Gears - authenticated uploads, uploads using voucher, pause and resume uploads and associated downloads">C. Gears - authenticated uploads, uploads using voucher, pause and resume uploads and associated downloads</a></li>
	<li><a class="wiki_link" href="#642e20666c617368206f72206765617273202d2072652d73656e6420656d61696c2c2061646420726563697069656e742c2064656c6574652066696c652c2064656c65746520766f7563686572" title="D. Flash or Gears - re-send email, add recipient, delete file, delete voucher">D. Flash or Gears - re-send email, add recipient, delete file, delete voucher</a></li>
	<li><a class="wiki_link" href="#authentication_-_logoff" title="Authentication - Logoff">Authentication - Logoff</a></li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="overview">Overview</h2>

<p>The following provides a list of considerations and workflows for and during testing of the local configuration and functionality of FileSender prior to release, for releases after 1.0. <span style="background-color: #ff0000;"><span style="background-color: #ffffff;">See <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows_until_v1-0" title="Test Workflows until v1-0">Test Workflows until v1-0</a> for tests conducted prior to the 1.0 release. </span></span></p>

<p>These tests are based primarily on usage by <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a> of the <a href="http://www.aarnet.edu.au/"> AARNet</a> installation of FileSender. Contributions to these workflows also provided by <a href="https://www.assembla.com/profile/xjansen"> Xander Jansen</a> based on the <a href="http://www.surfnet.nl">SURFnet</a> installation of FileSender.</p>

<p>Please note that these test workflows may not represent an exhaustive list of all possible user actions. Also, some aspects of these workflows may become no longer applicable as FileSender develops. If you find anything incorrect, please advise, or correct it yourself if you have access.</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="versions_tested">Versions Tested</h2>

<table border="0">
	<tbody>
		<tr>
			<td><strong>FileSender Release</strong></td>
			<td><strong>Installation</strong></td>
			<td><strong>Testing Status</strong></td>
			<td><strong>Notes</strong></td>
			<td><strong>OS</strong></td>
			<td><strong>Browser</strong></td>
			<td><strong>Flash</strong></td>
			<td><strong>Gears</strong></td>
			<td><strong>Conducted by</strong></td>
		</tr>
		<tr>
			<td rowspan="4">1.0.1 (see <a class="wiki_link" href="/wiki/show/file_sender/Notes_on_1-0-1_fixes_and_stuff" title="Notes on 1-0-1 fixes and stuff">Notes on 1-0-1 fixes and stuff</a>)</td>
			<td>Test with SSP 1.6.3</td>
			<td>Complete</td>
			<td>Full set as detailed below; also tested three recipients separated by comma and semicolon, for uploads (authenticated and using voucher), adding recipients and issuing vouchers (Flash and Gears)</td>
			<td>OSX 10.6.7</td>
			<td>FF 3.6.16</td>
			<td>Yes</td>
			<td>Yes</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td rowspan="3">Test with SSP 1.8</td>
			<td rowspan="3">Completed OK (logon, A, B (except voucher expiry and deletion), logoff)</td>
			<td rowspan="3">Flash subset: logon, authenticated upload, issue voucher, upload file using voucher</td>
			<td>OSX 10.5.8</td>
			<td>Opera 11.10/Safari 5.05/FF 3.6.17</td>
			<td rowspan="3">Yes</td>
			<td rowspan="3">N/A</td>
			<td rowspan="3"><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a></td>
		</tr>
		<tr>
			<td>Win7</td>
			<td>IE8</td>
		</tr>
		<tr>
			<td>Ubuntu 11.04</td>
			<td>FF 4.0.1</td>
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
			<td>&nbsp;</td>
		</tr>
	</tbody>
</table>

<h2 id="features_to_be_tested">Features to be Tested</h2>

<ul>
	<li><strong>Flash versus Gears:</strong> Flash installation prompt (with Flash plugin disabled); Flash versus Gears (no need to repeat workflow aspects that are handled by Flash regardless); cancelling Flash upload; pausing during Gears upload, including MD5 hash comparison of uploaded and downloaded files.</li>
	<li><strong>Broad workflows (verify all emails are received and contents match input):</strong> logon; authenticated upload; download uploaded file from url in email; download uploaded file from link in My Files table; resend email; add recipient(s); download uploaded file; issue voucher; upload file using voucher; download file uploaded using a voucher; delete file manually from My Files table (removed from My Files table and can no longer be accessed); delete voucher from Vouchers table (removed from Voucher table and can no longer be used); logoff.</li>
	<li><strong>GUI, prompts and automation:</strong> authenticated user&#39;s name is displayed after logon; Guest displayed for non-authenticated session (e.g. using a voucher, downloading a file); on-screen help text is present (e.g. description of how to use Vouchers); help and about pages are populated; automatic population of fields (e.g. sender&#39;s address); defaults when leaving optional fields blank (e.g. email subject and message, expiry date); prompts when leaving essential fields blank (e.g. recipient email address, AuP checkbox); prompts when attempting illegal operations (e.g. selecting a 2GB or greater file on a mac or on other OS without Gears; selecting a zero-sized file); workflow does not continue after illegal operation warning, until appropriate action is taken by user (e.g. select file smaller than limit in warning); files delete at expiry when cron job runs on server (no longer listed in My Files table and can no longer be accessed); vouchers are deleted after use (no longer listed in Voucher table and can no longer be used); unused vouchers delete at expiry when cron job runs on server (no longer listed in Voucher table and can no longer be used).</li>
	<li><strong>Variations:</strong> single recipient; multiple recipients, using both &quot;,&nbsp; and &quot;; &quot;; ASCII, ISO-8859-1 and non-ISO-8859-1 UTF8 character sets; file sizes: zero, small, just under 2 GB, 2 GB, just under 4 GB, 4 GB and 5 GB.</li>
	<li>See also <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows_until_v1-0#general_considerations_throughout_test_workflows" title="Test Workflows until v1-0#General Considerations Throughout Test Workflows">Test Workflows until v1-0#General Considerations Throughout Test Workflows</a>.</li>
</ul>

<p><span style="background-color: #ffffff;"><strong>&nbsp;</strong></span></p>

<h2 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20236666666666663b223e3c7374726f6e673e74657374206d61747269783c2f7374726f6e673e3c2f7370616e3e"><span style="background-color: #ffffff;"><strong>Test Matrix</strong></span></h2>

<table border="0">
	<tbody>
		<tr style="text-align: center;">
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;"><strong>Test Set</strong></span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">auth upload</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">download from auth upload email</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">issue voucher</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">upload using voucher</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">download from voucher upload email</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">cancel / pause and resume</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">download from My Files</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">resend</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">add recipients</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">delete file</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">delete voucher</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">single recipient</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">,</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">default field contents</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">custom field contents</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">ascii</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">ISO-8859-1</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">non-ISO-8859-1 UTF8</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">upload prompts</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">Flash</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">Gears</span></span></td>
		</tr>
		<tr>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;"><strong>A</strong></span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
		</tr>
		<tr>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;"><strong>B</strong></span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;"><strong>C</strong></span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">(uses vouchers issued with Flash)</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td>&nbsp;</td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
		</tr>
		<tr>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;"><strong>D</strong></span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">&nbsp;</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">X </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">N/A </span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">either</span></span></td>
			<td><span style="font-family: times new roman,times;"><span style="font-size: xx-small;">either </span></span></td>
		</tr>
	</tbody>
</table>

<p style="text-align: left;"><strong>Note:</strong> In test matrix table above, X = included.</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="62726f7773657220666c61736820706c7567696e2026616d703b206a6176617363726970742073657474696e677320646574656374696f6e" style="text-align: left;">Browser Flash plugin &amp; Javascript settings detection</h2>

<h3 id="flash_detection_and_disable_gears_plugin">Flash detection and disable Gears plugin</h3>

<ul>
	<li>disable Flash and Gears plugins and restart browser</li>
	<li>load FileSender logon page, prompt should appear <span style="color: #666699;">&quot;Install Flash Player. This application requires Flash Player. To install Flash Player go to Adobe.com&quot;</span> with a link to <span style="color: #666699;">&quot;Get Flash&quot;</span></li>
	<li>re-enable Flash plugin restart browser</li>
	<li>load FileSender logon page again, verify &quot;Gears X&quot; icon is displayed in top right-hand corner, which designates Flash-only (no Gears) mode</li>
</ul>

<h3 id="javascript_detection">Javascript detection</h3>

<ul>
	<li>disable Javascript in browser (e.g. FF on Mac under Preferences &gt; Content)</li>
	<li>load FileSender logon page, prompt should appear <span style="color: #666699;">&quot;JavaScript is turned off in your web browser. This application will not run without Javascript enabled in your web browser.&quot;</span></li>
	<li>re-enable Javascript (no need to restart browser)</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="authentication_-_logon">Authentication - Logon</h2>

<ul>
	<li>load FileSender logon page</li>
	<li>verify that page cannot be reached by http - should be accessible via https only</li>
	<li>click on the About and help links and verify content, before and after logging on to FileSender</li>
	<li>verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot; after logon</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="3c7374726f6e673e3c7374726f6e673e3c7374726f6e673e3c7374726f6e673e612e20666c617368202d2061757468656e746963617465642075706c6f6164732026616d703b206173736f63696174656420677565737420646f776e6c6f6164733c2f7374726f6e673e3c2f7374726f6e673e3c2f7374726f6e673e3c2f7374726f6e673e"><strong><strong><strong><strong>A. Flash - authenticated uploads &amp; associated Guest downloads</strong></strong></strong></strong></h2>

<p><strong><strong><strong><strong>Note:</strong></strong></strong></strong> Gears plugin should be disabled</p>

<h3 id="61312e2061757468656e746963617465642061736369692066696c652075706c6f61642c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e74732c2075706c6f61642070726f6d707473">A1. Authenticated ASCII file upload, single recipient, default field contents, upload prompts</h3>

<ul>
	<li>title of panel should be &quot;Upload&quot;</li>
	<li>leave &ldquo;To&rdquo; field blank, verify tooltip <span style="color: #666699;">&quot;Multiple email addresses can be entered separated by comma or semi-colon (, or ;)&quot;</span></li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>leave &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields blank, to verify defaults</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select the following file sizes (ASCII only):
	<ul>
		<li>zero KB - prompt should appear <span style="color: #666699;">&quot;Message - Cannot upload a file of 0 bytes. Please select another file&quot;</span>, &quot;Send&quot; button should *not* appear</li>
		<li>2 GB (and 1 MB below), 4 GB (and 1 MB below), 5 GB and over 5GB - prompt should appear <span style="color: #666699;">&quot;File is too large. If using Windows, please install Google Gears (*see top right hand corner*) to upload large files (not possible on Mac OSX and Linux). (Maximum without Gears: X MB)&quot;</span> (where X is the configurable maximum without Gears), &quot;Send&quot; button should *not* appear</li>
		<li>small ASCII text file&nbsp; - file size should be displayed, &ldquo;Send&rdquo; button *should* now appear</li>
	</ul>
	</li>
	<li>do not check the &ldquo;I accept the terms and conditions of this service&rdquo; (AuP) box, click on &ldquo;Send&rdquo; button - prompt should appear <span style="color: #666699;">&ldquo;Message. Please check email address&rdquo;</span></li>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>do not check the AuP box, click on &ldquo;Send&rdquo; button - prompt should appear <span style="color: #666699;">&ldquo;Message. You MUST agree to the terms and conditions.&rdquo;</span></li>
	<li>read the AuP terms and conditions, check the AuP box</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear, when complete new page should be displayed with text <span style="color: #666699;">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
</ul>

<h3 id="a2._download_ascii_file_(authenticated_upload)_from_my_files_table">A2. Download ASCII file (authenticated upload) from My Files table</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>click on the filename in the My Files table of uploaded ASCII file</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button</li>
	<li>verify that file has downloaded and can be opened</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
</ul>

<h3 id="61332e2061757468656e746963617465642069736f2d383835392d312066696c652075706c6f61642c2074776f20726563697069656e74732073657061726174656420627920636f6d6d612c20637573746f6d2069736f2d383835392d31206669656c6420636f6e74656e7473">A3. Authenticated ISO-8859-1 file upload, two recipients separated by comma, custom ISO-8859-1 field contents</h3>

<ul>
	<li>enter two recipient email addresses separated by &quot;, &quot; in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s address</li>
	<li>enter custom &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields with &quot;bl&aring;b&aelig;rsyltet&oslash;y&quot;</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select <a href="/spaces/file_sender/documents/drg4ko9Ryr37zXeJe5cbCb/download?filename=utf8-iso8859-1-%C3%A7%C3%9F%C3%B8%C3%BE-test.txt">utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt</a> - filename and size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session)</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear, when complete new page should be displayed with text &ldquo;Your file has been uploaded and message sent&rdquo;</li>
	<li>verify receipt of notification email to sender and both recipients, and that the content matches the input, with a different url for each recipient</li>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly (with no white space infront of second email address)</li>
</ul>

<h3 id="a4._download_iso-8859-1_file_(authenticated_upload)_from_email">A4. Download ISO-8859-1 file (authenticated upload) from email</h3>

<ul>
	<li>click on the link to utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt in one of the emails generated by authenticated upload</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by email addresses of selected recipient</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email address of sender</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - new page should appear displaying text <span style="color: #666699;">&ldquo;Your file should start downloading&rdquo;</span></li>
	<li>verify that file has downloaded and can be opened, and that non-ASCII characters are preserved in filename</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li><strong>repeat</strong> download to verify that the file can be downloaded more than once (no additional download notification emails will be triggered)</li>
</ul>

<h3 id="61352e2061757468656e74696361746564206e3c7374726f6e673e6f6e2d69736f2d383835392d3120757466382066696c652075706c6f61643c2f7374726f6e673e2c2074776f20726563697069656e7473207365706172617465642062792073656d692d636f6c6f6e2c20637573746f6d203c7374726f6e673e6e6f6e2d69736f2d383835392d312075746638203c2f7374726f6e673e6669656c6420636f6e74656e7473">A5. Authenticated n<strong>on-ISO-8859-1 UTF8 file upload</strong>, two recipients separated by semi-colon, custom <strong>non-ISO-8859-1 UTF8 </strong>field contents</h3>

<ul>
	<li>enter two recipient email addresses separated by &quot;; &quot; in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s address</li>
	<li>enter custom &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields with &quot;žćčđ&scaron;&quot;</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select <a href="/spaces/file_sender/documents/dNfthu9Ryr35RVeJe5cbCb/download?filename=utf8-latin-extended-a-%C5%A1%C5%99%C5%AC%C5%B4-test.txt">utf8-latin-extended-a-šřŬŴ-test.txt</a> - file size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session)</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear, when complete new page should be displayed with text <span style="color: #666699;">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and both recipients, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly (with no white space infront of second email address)</li>
</ul>

<h3 id="61362e20646f776e6c6f6164203c7374726f6e673e3c7374726f6e673e6e6f6e2d69736f2d383835392d312075746638203c2f7374726f6e673e3c2f7374726f6e673e66696c652066726f6d20656d61696c">A6. Download <strong><strong>non-ISO-8859-1 UTF8 </strong></strong>file from email</h3>

<ul>
	<li>click on the link to utf8-latin-extended-a-šřŬŴ-test.txt in email generated by authenticated upload</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by email addresses of selected recipient</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email address of sender</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - new page should appear displaying text <span style="color: #666699;">&ldquo;Your file should start downloading&rdquo;</span></li>
	<li>verify that file has downloaded and can be opened, and that non-ASCII characters are preserved in filename</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li><strong>repeat</strong> download to verify that the file can be downloaded more than once (no additional download notification emails will be triggered)</li>
</ul>

<h3 id="3c7374726f6e673e3c7374726f6e673e3c7374726f6e673e3c7374726f6e673e61372e2063616e63656c20616e6420726573746172742061757468656e746963617465642075706c6f61643c2f7374726f6e673e3c2f7374726f6e673e3c2f7374726f6e673e3c2f7374726f6e673e" style="text-align: left;"><strong><strong><strong><strong>A7. Cancel and restart authenticated upload</strong></strong></strong></strong></h3>

<ul>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select a largish file (~25 MB should be enough) - file size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session)</li>
	<li>click on &ldquo;Send&rdquo; button but cancel upload before completion</li>
	<li>verify that buttons across top of page reappear and that all fields reset</li>
	<li>re-enter recipient address, select expiry date and browse for file again and click on &quot;Send&quot; button - progress bar should appear, file upload should start from the beginning (0%), when complete new page should be displayed with text <span style="color: #666699;">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
</ul>

<h3 id="61382e20646f776e6c6f6164203c7374726f6e673e3c7374726f6e673e7265737461727465642061757468656e746963617465642075706c6f61643c2f7374726f6e673e3c2f7374726f6e673e2066726f6d20656d61696c">A8. Download <strong><strong>restarted authenticated upload</strong></strong> from email</h3>

<ul>
	<li>click on the link to file in email generated by restarted authenticated upload</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by email addresses of recipient</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email address of sender</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - new page should appear displaying text <span style="color: #666699;">&ldquo;Your file should start downloading&rdquo;</span></li>
	<li>verify that file has downloaded and can be opened</li>
	<li>compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li><strong>repeat</strong> download to verify that the file can be downloaded more than once (no additional download notification emails will be triggered)</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="3c7374726f6e673e3c7374726f6e673e3c7374726f6e673e3c7374726f6e673e622e20666c617368202d20697373756520766f7563686572732c2067756573742075706c6f6164732026616d703b206173736f63696174656420677565737420646f776e6c6f6164733c2f7374726f6e673e3c2f7374726f6e673e3c2f7374726f6e673e3c2f7374726f6e673e"><strong><strong><strong><strong>B. Flash - issue vouchers, Guest uploads &amp; associated Guest downloads</strong></strong></strong></strong></h2>

<h3 id="62312e20697373756520766f7563686572732c2073696e676c6520616e64206d756c7469706c6520726563697069656e74732073657061726174656420627920636f6c6f6e202f2073656d69636f6c6f6e">B1. Issue vouchers, single and multiple recipients separated by colon / semicolon</h3>

<ul>
	<li>click on &ldquo;Vouchers&rdquo; button</li>
	<li>verify that explanatory text about how to use Vouchers is present</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Send Voucher&rdquo; button - prompt should appear <span style="color: #666699;">&ldquo;Message. Please check email address&rdquo;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>in the &ldquo;Send Vouchers to:&rdquo; field, enter recipient email address</li>
	<li>click on &ldquo;Send Voucher&rdquo; button - prompt should appear <span style="color: #666699;">&ldquo;Voucher Sent&rdquo;</span> - click on &ldquo;OK&rdquo; button</li>
	<li>verify that issued voucher is now listed in Vouchers table</li>
	<li>verify that email notification with &ldquo;Voucher&rdquo; in the title is sent to both sender and recipient, and that text is correct</li>
	<li><strong>repeat</strong> to create eight more vouchers, for testing uploads using Flash and Gears</li>
	<li><strong>repeat</strong> with two recipients separated by a comma, to delete manually later</li>
	<li><strong>repeat</strong> with two recipients separated by a semicolon, setting the expiry date to the next calendar day to verify automatic expiration</li>
</ul>

<h3 id="b2._guest_uploads_using_vouchers_and_associated_downloads">B2. Guest uploads using vouchers and associated downloads</h3>

<ul>
	<li>repeat Flash upload tests using issued vouchers and associated download tests, ensuring that:
	<ul>
		<li>you are recognised as &quot;Guest&quot; for both uploads and downloads (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
		<li>recipient email addresses used differ from that of the authenticated voucher issuer and recipient(s), for testing bcc email to voucher issuer</li>
		<li>subject default is &quot;Voucher&quot;</li>
		<li>AuP box is *not* pre-checked</li>
		<li>vouchers are automatically deleted after use and cannot be used a second time - text should appear <span style="color: #666699;">&quot;This file/voucher is no longer available&quot;</span></li>
		<li>bcc of each email is sent to voucher issuer in addition to voucher recipient and uploaded file recipients</li>
	</ul>
	</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="632e206765617273202d203c7374726f6e673e3c7374726f6e673e61757468656e746963617465642075706c6f6164732c203c7374726f6e673e3c7374726f6e673e75706c6f616473207573696e6720766f75636865722c20706175736520616e6420726573756d65203c2f7374726f6e673e3c2f7374726f6e673e75706c6f61647320616e64206173736f63696174656420646f776e6c6f6164733c2f7374726f6e673e3c2f7374726f6e673e">C. Gears - <strong><strong>authenticated uploads, <strong><strong>uploads using voucher, pause and resume </strong></strong>uploads and associated downloads</strong></strong></h2>

<p>Enable Gears browser plugin, restart browser. Load FileSender logon page again, verify &quot;Gears [tick]&quot; (where tick represents a check mark) icon is displayed in top right-hand corner, which designates Gears mode. title of panel should be &quot;Gears Upload&quot;.</p>

<h3 id="c1._repeat_flash_upload_and_upload_using_voucher_tests_using_gears">C1. Repeat Flash upload and upload using voucher tests using Gears</h3>

<ul>
	<li>using Gears, repeat upload tests A1 - A6 and corresponding tests uploading and downloading using issued vouchers detailed in B2</li>
	<li>repeat tests A1 and A2 uploading and downloading a file over 2 GB on Windows (only)</li>
	<li><strong>Note:</strong>when testing file size prompts, for file sizes:
	<ul>
		<li>over 1.95 GB but under Gears limit, on a mac prompt should appear: <span style="color: #666699;">&quot;Mac using gears cannot upload a file larger than 2 GB (Error <a href="/spaces/file_sender/tickets/032">#032</a>)&quot;</span><span style="color: #000000;">, while on </span>Linux nothing happens i.e. no message (known issue)</li>
		<li>over the set Gears limit, on mac, Linux or Windows, prompt should appear <span style="color: #666699;">&quot;Message - File is too large (Max: X MB)&quot;</span> (where X is the configurable maximum with Gears), &quot;Send&quot; button should *not* appear</li>
	</ul>
	</li>
</ul>

<h3 id="63322e2061757468656e7469636174656420706175736520616e6420726573756d652066696c652075706c6f61642c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473">C2. Authenticated pause and resume file upload, single recipient, default field contents</h3>

<ul>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select a largish file (~25 MB should be enough) - file size should be displayed, &ldquo;Send&rdquo; button *should* now appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session)</li>
	<li>click on &ldquo;Send&rdquo; button, pausing and resuming (using cancel button) during upload - verify that buttons reappear across top of page and that all fields reset, progress bar should appear, when complete new page should be displayed with text <span style="color: #666699;">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
	<li><strong>repeat</strong> using voucher, verifying that you are recognised as &quot;Guest&quot; (even if you are logged on in another browser tab), ensuring that the recipient email addresses differ from that of the authenticated voucher issuer, and verifying that the voucher is automatically deleted after use and cannot be used a second time - text should appear <span style="color: #666699;">&quot;This file/voucher is no longer available&quot;</span></li>
</ul>

<h3 id="c3._download_paused_gears_authenticated_upload_file">C3. Download paused Gears authenticated upload file</h3>

<ul>
	<li>click on the link in email generated by paused authenticated upload using Gears</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by recipient&#39;s email address</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by sender&#39;s email address</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - new page should appear displaying text <span style="color: #666699;">&ldquo;Your file should start downloading&rdquo;</span></li>
	<li>verify that file has downloaded and can be opened</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li>compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file</li>
	<li><strong>repeat</strong> download to verify that the file can be downloaded more than once</li>
	<li><strong>repeat</strong> for file uploaded using a voucher, ensuring that bcc email is sent to voucher issuer in addition to voucher recipient and uploaded file recipients</li>
</ul>

<h3 id="63342e2061757468656e74696361746564206c617267652066696c652075706c6f6164206f76657220322067622c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473202877696e646f7773206f6e6c7929">C4. Authenticated large file upload over 2 GB, single recipient, default field contents (Windows only)</h3>

<ul>
	<li><strong>Note:</strong> this test can only be conducted on Windows</li>
	<li>enter one recipient email address (only) in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>select expiry date</li>
	<li>click on &ldquo;Browse&rdquo; button and select a file over 2 GB - file size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>verify that the AuP box remains checked from previous test (only need to check once per FileSender session)</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear, when complete new page should be displayed with text <span style="color: #666699;">&ldquo;Your file has been uploaded and message sent&rdquo;</span></li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
	<li><strong>repeat</strong> using voucher, verifying that you are recognised as &quot;Guest&quot; (even if you are logged on in another browser tab), ensuring that the recipient email addresses differ from that of the authenticated voucher issuer, and verifying that the voucher is automatically deleted after use and cannot be used a second time - text should appear <span style="color: #666699;">&quot;This file/voucher is no longer available&quot;</span></li>
</ul>

<h3 id="c5._download_gears_authenticated_large_file_upload_over_2_gb">C5. Download Gears authenticated large file upload over 2 GB</h3>

<ul>
	<li>click on the link in email generated by authenticated large file upload over 2 GB using Gears</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab), and that &quot;New Upload&quot;, &quot;Voucher&quot;, &quot;My Files&quot; and &quot;Log Off&quot; buttons do *not* appear</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by recipient&#39;s email address</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by sender&#39;s email address</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - new page should appear displaying text <span style="color: #666699;">&ldquo;Your file should start downloading&rdquo;</span></li>
	<li>verify that file has downloaded and can be opened</li>
	<li>verify that an email is sent to both sender and recipient to whom link was sent, notifying that the above file has been downloaded</li>
	<li>compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file</li>
	<li><strong>repeat</strong> for file uploaded using a voucher, ensuring that bcc email is sent to voucher issuer in addition to voucher recipient and uploaded file recipients</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="642e20666c617368206f72206765617273202d2072652d73656e6420656d61696c2c2061646420726563697069656e742c2064656c6574652066696c652c2064656c65746520766f7563686572">D. Flash or Gears - re-send email, add recipient, delete file, delete voucher</h2>

<h3 id="d1._re-send_new_email">D1. Re-Send New Email</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to the uploaded ASCII file entry, click on &ldquo;Re-Send Email&rdquo; button on the left - a prompt should appear <span style="color: #666699;">&ldquo;Re-send. Are you sure you want to re-send this Email?&rdquo;</span>, click on &ldquo;Cancel&rdquo; button, view should return to table</li>
	<li>click on &ldquo;Re-Send Email&rdquo; button again, click on &ldquo;OK&rdquo; button, another prompt should appear <span style="color: #666699;">&ldquo;Email has been sent&rdquo;</span></li>
	<li>verify receipt of email to both sender and recipient(s)</li>
</ul>

<h3 id="64322e20616464206e657720726563697069656e742c2061736369692c2073696e676c6520726563697069656e742cc2a06f726967696e616c206669656c6420636f6e74656e7473">D2. Add New Recipient, ASCII, single recipient,&nbsp;original field contents</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>click on &ldquo;Add New Recipient&rdquo; button to the left of uploaded ASCII file entry - a prompt should appear <span style="color: #666699;">&ldquo;Add Recipient&rdquo;</span>:</li>
	<li>leave &ldquo;To&rdquo; field blank</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>verify that the default &ldquo;Subject&rdquo; and &quot;Message&quot; are the same as original email subject</li>
	<li>leave &ldquo;Message&rdquo; field unchanged, to verify default</li>
	<li>select expiry date</li>
	<li>verify that &ldquo;File to be Redistributed&rdquo; and &ldquo;Size&rdquo; fields are correct</li>
	<li>click on &ldquo;Send&rdquo; button</li>
	<li>prompt should appear <span style="color: #666699;">&ldquo;Please check email address&quot;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>enter recipient one email address (only) in the &ldquo;To&rdquo; field, and click on &ldquo;Send&rdquo; button again</li>
	<li>another prompt should appear <span style="color: #666699;">&ldquo;Email has been sent&rdquo;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly</li>
</ul>

<h3 id="64332e20616464206e657720726563697069656e742c2069736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382c2074776f20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">D3. Add New Recipient, ISO-8859-1 / non-ISO-8859-1 UTF8, two recipients separated by comma / semi-colon, custom field contents</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>repeat the following for these uploaded file entries:
	<ul>
		<li>utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt (ISO-8859-1 file,&nbsp;two recipients separated by comma)</li>
		<li>utf8-latin-extended-a-šřŬŴ-test.txt (non-ISO-8859-1 UTF8 file,&nbsp;two recipients separated by semi-colon)</li>
	</ul>
	</li>
</ul>

<ul>
	<li>next to an uploaded file entry, click on &ldquo;Add New Recipient&rdquo; button on the left - a prompt should appear <span style="color: #666699;">&ldquo;Add Recipient&rdquo;</span></li>
	<li>enter two recipient email addresses separated by &quot;, &quot; or &quot;; &quot; (as listed above) in the &ldquo;To&rdquo; field</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with sender&#39;s email address</li>
	<li>modify default &ldquo;Subject&rdquo; and &quot;Message&quot; by adding text to each</li>
	<li>select a different expiry date</li>
	<li>verify that &ldquo;File to be Redistributed&rdquo; and &ldquo;Size&rdquo; fields are correct</li>
	<li>click on &ldquo;Send&rdquo; button</li>
	<li>a prompt should appear <span style="color: #666699;">&ldquo;Email has been sent&rdquo;</span>, click on &ldquo;OK&rdquo; button</li>
	<li>verify receipt of notification email to sender and recipients, and that the content matches the input</li>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly (with no white space infront of second email address)</li>
</ul>

<h3 id="d4._delete_file">D4. Delete File</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to the entry for an authenticated upload file, click on &ldquo;Delete&rdquo; button on the right - a prompt should appear <span style="color: #666699;">&ldquo;Delete File. Are you sure?&rdquo;</span> - click on &ldquo;Cancel&rdquo; button, file should remain in table</li>
	<li>click on &ldquo;Delete&rdquo; button again and click on &ldquo;OK&rdquo; button - file should disappear from table</li>
	<li>verify that an email is sent to uploader and recipients advising that the file has been deleted</li>
	<li>verify that the file can no longer be accessed, message <span style="color: #666699;">&quot;This file / Voucher is no longer available&quot;</span></li>
	<li><strong>repeat</strong> for a file uploaded using a voucher and verify email advice</li>
</ul>

<h3 id="d5._delete_voucher">D5. Delete Voucher</h3>

<ul>
	<li>in the Vouchers table, delete the last voucher that was issued (which may now be the only voucher listed) by clicking on Delete button on the right</li>
	<li>verify that deleted voucher is no longer listed in Voucher list</li>
	<li>verify whether an email is sent to voucher issuer and voucher recipient, advising that the voucher has been cancelled</li>
	<li>click on the email link pertaining to the deleted voucher again, to verify that it can no longer be used - text should appear <span style="color: #666699;">&quot;This voucher has been cancelled&quot;</span></li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h3 id="authentication_-_logoff">Authentication - Logoff</h3>

<ul>
	<li>before logging off, open a second FileSender tab in your browser, then logoff in one - if you refresh the tab in which you did not logoff, verify that you are logged out and are presented with the logon screen</li>
	<li>in the tab you logged out in, click on the &ldquo;Back&rdquo; button in your browser - verify that are you still logged out, and are presented with the logon screen.</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<p>My contributions to this project are as a Monash University user, beta-tester and release tester of the <a href="http://www.aarnet.edu.au/" target="_blank">AARNet, the Australian National Research and Educational Network (NREN)</a> and test installations of FileSender. I am not a developer of FileSender. -- <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>.</p>

