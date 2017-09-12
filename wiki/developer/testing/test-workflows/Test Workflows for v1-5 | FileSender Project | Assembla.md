<ul>
	<li><a class="wiki_link" href="#overview" title="Overview">Overview</a></li>
	<li><a class="wiki_link" href="#versions_tested" title="Versions Tested">Versions Tested</a></li>
	<li><a class="wiki_link" href="#--_notes_and_extra_steps_--" title="-- Notes and extra steps --">-- Notes and extra steps --</a></li>
	<li><a class="wiki_link" href="#2d2d2062726f7773657220666c61736820706c7567696e2c206a6176617363726970742073657474696e67732c2068746d6c3520646574656374696f6e20616e6420687474707320766572696669636174696f6e202d2d" title="-- Browser Flash plugin, Javascript settings, HTML5 detection and https verification --">-- Browser Flash plugin, Javascript settings, HTML5 detection and https verification --</a></li>
	<li><a class="wiki_link" href="#--_logon_and_authenticated_environment_--" title="-- Logon and authenticated environment --">-- Logon and authenticated environment --</a></li>
	<li><a class="wiki_link" href="#--_issue_vouchers_(authenticated)_--" title="-- Issue Vouchers (authenticated) --">-- Issue Vouchers (authenticated) --</a></li>
	<li><a class="wiki_link" href="#--_uploads_(authenticated_and_using_a_voucher)_--" title="-- Uploads (authenticated and using a voucher) --">-- Uploads (authenticated and using a voucher) --</a></li>
	<li><a class="wiki_link" href="#--_downloads_(unauthenticated)_--" title="-- Downloads (unauthenticated) --">-- Downloads (unauthenticated) --</a></li>
	<li><a class="wiki_link" href="#--_re-send_new_email_(authenticated)_--" title="-- Re-Send New Email (authenticated) --">-- Re-Send New Email (authenticated) --</a></li>
	<li><a class="wiki_link" href="#--_add_new_recipient_(authenticated)_--" title="-- Add New Recipient (authenticated) --">-- Add New Recipient (authenticated) --</a></li>
	<li><a class="wiki_link" href="#--_delete_file_(authenticated)_--" title="-- Delete File (authenticated) --">-- Delete File (authenticated) --</a></li>
	<li><a class="wiki_link" href="#--_delete_voucher_(authenticated)_--" title="-- Delete Voucher (authenticated) --">-- Delete Voucher (authenticated) --</a></li>
	<li><a class="wiki_link" href="#--_automatic_voucher_and_file_deletion_(next_day)_--" title="-- Automatic Voucher and File Deletion (next day) --">-- Automatic Voucher and File Deletion (next day) --</a></li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="overview">Overview</h2>

<p>The following provides a list of considerations and test workflows (both automated and manual) for and during client-side testing of the local configuration and functionality of FileSender prior to the 1.5 release. <span style="background-color: rgb(255, 0, 0);"><span style="background-color: rgb(255, 255, 255);">See <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows" title="Test Workflows">Test Workflows</a> for links to tests conducted for other releases. </span></span></p>

<p>These tests are based primarily on tests conducted by <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>. Contributions to these workflows also provided by <a href="https://www.assembla.com/profile/xjansen"> Xander Jansen</a>.</p>

<p>Please note that these test workflows may not represent an exhaustive list of all possible user actions. Also, some aspects of these workflows may become no longer applicable as FileSender develops. If you find anything incorrect, please advise, or correct it yourself if you have access.</p>

<p><span style="background-color: rgb(255, 255, 136);"><span style="background-color: rgb(255, 255, 255);">Each suite contains links to a series of test scripts. See <a class="wiki_link" href="/wiki/show/file_sender/Automated_Workflow_Test_Matrix" title="Automated Workflow Test Matrix">Automated Workflow Test Matrix</a> for list and links to test suites. </span>Steps currently automated using <a href="http://seleniumhq.org/">Selenium</a> are contained in yellow-shaded boxes below</span>.&nbsp;</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="versions_tested">Versions Tested</h2>

<table align="left" border="0">
	<tbody>
		<tr>
			<td><b>FileSender release</b></td>
			<td><b>Site &amp; installation type (source, .deb, .rpm)</b></td>
			<td><b>Testing status</b></td>
			<td><b>Tests being conducted (e.g. workflow; installation and / or documentation review; field testing)</b></td>
			<td><b>Notes</b></td>
			<td><b>HTML5 or Flash?</b></td>
			<td><b>OS</b></td>
			<td><b>Browser</b></td>
			<td><b>Flash Player version </b></td>
			<td><b>(To be) conducted by</b></td>
		</tr>
		<tr>
			<td>1.5.-beta1</td>
			<td>https://filesender.surfnet.nl/preview/</td>
			<td>Complete</td>
			<td>All authenticated workflow tests (manual); issue voucher, ASCII file upload using voucher (manual)</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.x</td>
			<td>Google Chrome</td>
			<td>&nbsp;</td>
			<td><a href="https://www.assembla.com/profile/meijer">Jan Meijer</a></td>
		</tr>
		<tr>
			<td>1.5-beta2</td>
			<td>https://filesender.surfnet.nl/preview/</td>
			<td>Complete</td>
			<td>All workflow tests (semi-automated using Selenium-IDE Firefox browser plugin), except for uploads (and associated downloads) over 2GB</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8</td>
			<td>Firefox 11.0</td>
			<td><span>11.2.202.22</span></td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Uploads (and associated downloads) over 2 GB (manual)</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OS X 10.5.8</td>
			<td>FireFox 11.0</td>
			<td>&nbsp;-</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>All workflow tests (manual) applicable to Flash case (excludes upload over 2GB)</td>
			<td>&nbsp;</td>
			<td>Flash<span>&nbsp; &nbsp;</span></td>
			<td>Windows 7</td>
			<td>Internet Explorer 9</td>
			<td><span>11.2.202.22</span></td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>1.5-beta3</td>
			<td>https://filesender.surfnet.nl/preview/&nbsp;</td>
			<td>Complete</td>
			<td>All workflow tests (semi-automated using Selenium-IDE Firefox browser plugin), except for uploads (and associated downloads) over 2GB</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8</td>
			<td>Firefox 12.0</td>
			<td>-</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Uploads (and associated downloads) over 2 GB (manual)</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Windows7</td>
			<td>&nbsp;Firefox 12.0 and 13.0beta</td>
			<td>-</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>All workflow tests (semi-automated using Selenium Server) applicable to Flash case, except for uploads (and associated downloads) over 2GB</td>
			<td>&nbsp;</td>
			<td>Flash</td>
			<td>Windows7</td>
			<td>Internet Explorer 9</td>
			<td>11.2.202.235</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;&nbsp;</td>
		</tr>
		<tr>
			<td>1.5-beta4</td>
			<td>https://filesender.surfnet.nl/preview/&nbsp;&nbsp;</td>
			<td>Complete</td>
			<td>All workflow tests (semi-automated using Selenium-IDE Firefox browser plugin), except for uploads (and associated downloads) over 2GB&nbsp;</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8&nbsp;</td>
			<td>Firefox 13.0.1</td>
			<td>-</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete&nbsp;</td>
			<td>All workflow tests (semi-automated using Selenium Server) applicable to Flash case</td>
			<td>&nbsp;</td>
			<td>Flash</td>
			<td>Windows7</td>
			<td>Internet Explorer 9</td>
			<td>11.3.300.265</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Selection of workflows (semi-automated using Selenium-IDE Firefox browser plugin) testing core functionality only</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8</td>
			<td>Firefox 14.0.1</td>
			<td>-</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Uploads (and associated downloads) over 2 GB (semi-automated)&nbsp;</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Windows7</td>
			<td>FireFox 14.0.1</td>
			<td>&nbsp;</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a></td>
		</tr>
		<tr>
			<td>1.5-RC1</td>
			<td>https://filesender.surfnet.nl/preview/</td>
			<td>Complete</td>
			<td>All workflow tests (mostly automated using Selenium-IDE Firefox browser plugin), except for uploads (and associated downloads) over 2GB</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8</td>
			<td>Firefox 15.0</td>
			<td>-</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>All workflow tests (mostly automated using Selenium Server) applicable to Flash case</td>
			<td>&nbsp;</td>
			<td>Flash</td>
			<td>Windows7</td>
			<td>Internet Explorer 9</td>
			<td>11.4.402.265</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Uploads (and associated downloads) over 2 GB (semi-automated)</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Mac OSX 10.5.8</td>
			<td>Firefox 15.0</td>
			<td>&nbsp;</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Uploads (and associated downloads) over 2 GB (semi-automated)&nbsp;</td>
			<td>&nbsp;</td>
			<td>HTML5</td>
			<td>Windows7</td>
			<td>Firefox 15.0</td>
			<td>&nbsp;</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a>&nbsp;</td>
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
			<td>&nbsp;</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="" style="background-color: rgb(255, 255, 255);">&nbsp;</h2>

<h2 id="" style="background-color: rgb(255, 255, 255);">&nbsp;</h2>

<h2 id="2d2d206e6f74657320616e64206578747261207374657073202d2d3c62723e">-- Notes and extra steps --</h2>

<ul>
	<li><span style="font-weight: normal;"><b>Clear browser cache before starting tests </b></span></li>
	<li><span style="font-weight: normal;"><b>General: </b>Conduct each upload and download workflow twice: once for a file uploaded as an authenticated user (</span>logoff after each authenticated upload workflow<span style="font-weight: normal;">), repeated for a file uploaded using a voucher.&nbsp;</span></li>
	<li><b>Help and About: </b>before and after logon, verufy that all links work in Help and About.</li>
	<li><b><b>Tooltips:</b></b> verify tooltips for email recipient fields, for upload (authenticated and using a voucher), adding a new recipient and issuing a voucher.</li>
	<li><b>Voucher recipients: </b>For voucher uploads, use a recipient email addresses different from that of the authenticated voucher issuer and voucher recipient(s), for testing bcc email to the voucher issuer<span style="color: rgb(102, 102, 153);"><span style="color: rgb(0, 0, 0);"> (</span></span>bcc of each email is sent to voucher issuer in addition to voucher recipient and uploaded file recipients).</li>
	<li><b>My Files check:</b> Repeat one voucher upload scenario when logged off, and again logged in as another user (i.e. other than the user who issued the voucher) to ensure that files appear in voucher issuer&#39;s &quot;My Files&quot; table.<span style="color: rgb(0, 0, 0);">&nbsp;</span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>Add new recipient check:</b> For one</span><span style="color: rgb(0, 0, 0);"> test when adding a new recipient, enter / modify all fields, click on cancel, then verify that all fields have reset (to that described in tests) when trying to add a new recipient again. </span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>Voucher deletion permission check:</b> Load one voucher url as [...]?s=vouchers&amp;a=del&amp;id=[voucherid) when logged on as another user</span>, to verify that a user cannot delete another user&#39;s voucher - message should appear <span style="color: rgb(153, 0, 0);">&quot;You do not have permission to do this.&quot;</span><span style="color: rgb(0, 0, 0);">.</span>&nbsp;</li>
	<li><span style="color: rgb(0, 0, 0);"><b>Invalid expiry date check: </b>For file uploads (authenticated and using a voucher), adding a recipient and issuing a voucher, try entering an invalid expiry date &quot;0000&quot; - message should appears <span style="color: rgb(153, 0, 0);">&quot;Invalid expiry Date&quot;</span></span>. Also try manually typing in an expiry date earlier than the minimum and later than the maximum.</li>
	<li><b>Logoff check: </b>On one occassion, logon, open a second FileSender tab in your browser, then logoff in one - if you refresh the tab in which you did not logoff, verify that you are logged out and are presented with the logon screen. in the tab you logged out in, click on the &ldquo;Back&rdquo; button in your browser - verify that are you still logged out, and are presented with the logon screen.<span style="color: rgb(0, 0, 0);">&nbsp;</span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>Characters in email subject check:</b> if email client does not preserve all &#39;dangerous&#39; characters (such as html codes), verify these in another client, for </span>upload (authenticated and using a voucher), resend email, adding a new recipient, downloading a file and file deletion.</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="">&nbsp;</h2>

<h2 id="2d2d2062726f7773657220666c61736820706c7567696e2c206a6176617363726970742073657474696e67732c2068746d6c3520646574656374696f6e20616e6420687474707320766572696669636174696f6e202d2d3c62723e">-- Browser Flash plugin, Javascript settings, HTML5 detection and https verification --</h2>

<ul>
	<li>clear browser cache</li>
	<li>disable Flash plugin and restart browser <b>[leave disabled for HTML5 case</b>]</li>
	<li><b>[Flash case only]:</b> load FileSender logon page and logon, prompt should appear <span style="color: rgb(153, 0, 0);">&quot;This application requires Flash for uploading files. To install Flash Player go to www.adobe.com.&quot;</span> with a hyperlink to www.adobe.com<span style="color: rgb(102, 102, 153);">. </span>Logoff, re-enable Flash plugin and restart browser</li>
	<li>disable Javascript in browser (e.g. Firefox on Mac under Preferences &gt; Content)</li>
	<li>load FileSender logon page again, prompt should appear <span style="color: rgb(153, 0, 0);">&quot;JavaScript is turned off in your web browser. This application will not run without Javascript enabled in your web browser.&quot;</span></li>
	<li>re-enable Javascript (no need to restart browser)</li>
	<li>load FileSender logon page again</li>
	<li>verify that page cannot be reached by http - should be accessible via https only</li>
	<li>verify that the correct &quot;HTML5 [tick]&quot; or &quot;HTML5 X&quot; icon is displayed, which indicates whether the browser (version) does support HTML5 (HTML5 case) or does not (Flash case)</li>
</ul>

<p style="text-align: center;"><span style="font-weight: normal;">-------------------------------------------------------------------------------------------------- </span></p>

<h2 id="2d2d206c6f676f6e20616e642061757468656e7469636174656420656e7669726f6e6d656e74202d2d3c62723e">-- Logon and authenticated environment --</h2>

<p>(logon.html, help_about_unauth.html, logon_enter.html, env_upload.html, help_about_auth.html):</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<p>&nbsp;</p>

			<ul>
				<li>load logon page</li>
				<li><i><b style="color: rgb(11, 83, 148);">(Cancel and restart (Flash) or resume (HTML5) workflows only</b><b style="color: rgb(11, 83, 148);">): </b><span style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents </span></i></li>
				<li>verify welcome heading and text; verify version number; verify HTML5 logo</li>
				<li>logon [to FileSender]</li>
				<li>verify links across top of page (Send File, Guest Voucher, My Files, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner <span style="color: rgb(0, 0, 0);">&quot;Welcome [first name surname]&quot;; </span>verify title of panel is &quot;Send a File&quot;&nbsp;</li>
				<li><i><b style="color: rgb(11, 83, 148);">(Cancel and restart (Flash) or resume (HTML5) workflows only</b><b style="color: rgb(11, 83, 148);">): </b><span style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents&nbsp; </span></i></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
</ul>

<p style="text-align: center;"><span style="font-weight: normal;">-------------------------------------------------------------------------------------------------- </span></p>

<h2 id="2d2d20697373756520766f756368657273202861757468656e7469636174656429202d2d3c62723e">-- Issue Vouchers (authenticated) --</h2>

<p><b>Voucher environment</b> (env_voucher_issue.html; help_about_auth.html):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>[click on &quot;Guest Vouchers&quot; button]</li>
				<li>verify links across top of page (Send File, Guest Voucher, My Files, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner <span style="color: rgb(0, 0, 0);">&quot;Welcome [first name surname]&quot;; </span>verify title of panel is &quot;Guest Voucher&quot;</li>
				<li>verify that explanatory text about how to use Vouchers is present</li>
				<li>verify table headers and action buttons</li>
				<li><i><b style="color: rgb(11, 83, 148);">(Cancel and restart (Flash) or resume (HTML5) upload using voucher only</b><b style="color: rgb(11, 83, 148);">): </b><span style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents&nbsp; </span></i></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<p>&nbsp;</p>

<p><b>Issue voucher to expire tomorrow</b> (voucher_issue_singlerecipient_tomorrowexpiry.html):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>verify &quot;There are currently no vouchers available&quot; in table</li>
				<li>verify but leave &quot;To&quot; field blank</li>
				<li>verify expiry date field, select expiry date tomorrow</li>
				<li>click on &quot;Send Voucher&quot; button - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Invalid or missing email&quot;</span>
				<ul>
					<li>in the &quot;Send voucher to:&quot; field, enter recipient email address - warning should disappear</li>
				</ul>
				</li>
				<li>click on &quot;Send Voucher&quot; button again - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Voucher Sent&quot;</span></li>
				<li>verify that issued voucher is now listed in Vouchers table, verify delete button</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">save the email for the voucher set to expire on the next calendar day, for later verification (see end)&nbsp;&nbsp; </span></i></li>
</ul>

<p><b>Issue voucher with default expiry date&nbsp;</b></p>

<p><b>Note:</b> For use with ASCII file uploads (including cancel/resume) and over 2GB file upload</p>

<p>(voucher_issue_singlerecipient_defaultexpiry.html):</p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>verify but leave &quot;To&quot; field blank</li>
				<li>verify expiry date field, but leave as default to verify in email</li>
				<li>enter recipient email address</li>
				<li>click on &quot;Send Voucher&quot; button - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Voucher Sent&quot;</span></li>
				<li>verify that issued voucher is now listed in Vouchers table, verify delete button</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<p><b>Issue vouchers to two recipients separated by a &quot;,&quot; or &quot;;&quot;</b>&nbsp;</p>

<p><b>Note:</b> For use with ISO-8859-1 / non-ISO-8859-1 UTF8 file uploads</p>

<p>(voucher_issue_tworecipients_comma_customexpiry.html; voucher_issue_tworecipients_semicolon_customexpiry.html) (logoff):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>enter over the configured maximum number of recipient email addresses in the &quot;Send Vouchers to&quot; field separated by [&quot;,&quot; or &quot;;&quot;]</li>
				<li>verify expiry date field, change to custom expiry date</li>
				<li>click on &quot;Send Voucher&quot; button - message should appear <span style="color: rgb(153, 0, 0);">&quot;The maximum number of email addresses allowed is [X]&quot;</span> (where X is the configured maximum)</li>
				<li>enter two recipient email addresses separated by [&quot;,&quot; or &quot;;&quot;] in the &quot;Send Vouchers to&quot; field</li>
				<li>click on &quot;Send Voucher&quot; button again - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Voucher Sent&quot;</span>, message should disappear</li>
				<li>verify that issued vouchers are now listed in Vouchers table, verify delete button</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<div style="text-align: center;">--------------------------------------------------------------------------------------------------</div>

<h2 id="--_uploads_(authenticated_and_using_a_voucher)_--">-- Uploads (authenticated and using a voucher) --</h2>

<h4 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e3c7370616e207374796c653d22666f6e742d7765696768743a206e6f726d616c3b223e3c2f7370616e3e">&nbsp;</h4>

<h3 id="61736369692066696c652075706c6f61642c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e74732c2075706c6f61642070726f6d707473">ASCII file upload, single recipient, default field contents, upload prompts</h3>

<p><b>Using voucher only: </b>(email_voucher_issue_singlerecipient_defaultfields.html; voucher.html; env_upload_voucher.html):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>select email; verify email subject [Voucher]; verify email addresses of sender, recipient and cc; verify email content, store and display voucher link [click on voucher link in email]; delete email</li>
				<li>verify links across top of [Voucher] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify title of panel is &quot;Send a File&quot;</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<h2 id="">&nbsp;</h2>

<p><b>Authenticated and using Voucher: </b>(upload_ASCII_singlerecipient_defaultfields_HTML5.html, upload_ASCII_singlerecipient_defaultfields_HTML5_voucher.html, upload_ASCII_singlerecipient_defaultfields_Flash.html, upload_ASCII_singlerecipient_defaultfields_Flash_voucher.html):</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<p>&nbsp;</p>

			<ul>
				<li>verify but leave &quot;To&quot; field blank</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>verify, but leave &quot;Subject&quot; and &quot;Message&quot; fields blank or default to verify defaults in email</li>
				<li>verify expiry date field, but leave as default to verify in email</li>
				<li>verify &quot;I accept the terms and conditions of this service&quot; AUP box and that it is not checked, but do not check box</li>
				<li>click on &quot;Browse&quot; button and select the following ASCII files:
				<ul>
					<li><b>[HTML5 and Flash cases]:</b>
					<blockquote>- <b>no file extension</b> - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;The name of the file you are uploading is invalid. Please rename your file and try again.&quot;</span>, file name and size should not be displayed, &quot;Send&quot; button should *not* appear</blockquote>

					<blockquote>- <b>invalid characters</b> [not on Windows] - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;The name of the file you are uploading is invalid. Please rename your file and try again.&quot;</span>, file name and size should not be displayed, &quot;Send&quot; button should *not* appear</blockquote>

					<blockquote>- <b>zero KB</b> - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;File size cannot be 0. Please select another file.&quot;</span>, file name and size should not be displayed, &quot;Send&quot; button should *not* appear</blockquote>

					<blockquote>- <b>.bat file, .exe file</b> - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Invalid file extension. Please select another file.&quot;</span>, file name and size should not be displayed, &quot;Send&quot; button should *not* appear</blockquote>

					<blockquote>- <b>.ex file</b> - file name and size should be displayed, &quot;Send&quot; button *should* now appear</blockquote>
					</li>
					<li><b>[HTML5 case only]:</b>
					<blockquote>- <b>2 GB (and 1 MB below), 4 GB (and 1 MB below), 5 GB</b>&nbsp; - file name and size should be displayed, &quot;Send&quot; button *should* now appear</blockquote>

					<blockquote>- <b>over 5GB</b> - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;File size cannot be greater than X GB [where X is the configured maximum]. Please select another file.&quot;</span>, file name and size should not be displayed, &quot;Send&quot; button should *not* appear</blockquote>

					<blockquote>- <b>small ASCII text file</b>&nbsp; - file name and size should be displayed, &quot;Send&quot; button *should* now appear&nbsp;</blockquote>
					</li>
					<li><b>[Flash case only]:</b>
					<blockquote>- <b>2 GB</b> - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;File size cannot be greater than 2 GB. Please select another file or use a HTML5 enabled browser to upload larger files.&quot;</span>, file<br />
					name and size should not be displayed, &quot;Send&quot; button *should not* appear&nbsp;</blockquote>

					<blockquote>- <b>1 MB below 2 GB</b> - file name and size should be displayed, &quot;Send&quot; button *should* now appear</blockquote>

					<blockquote>- <b>4 GB (and 1 MB below), 5 GB and over 5 GB</b> - prompt should appear <span style="color: rgb(153, 0, 0);">&quot;File size cannot be greater than 2 GB. Please select another file or use a HTML5 enabled browser to upload larger files.&quot;</span>, file name and size should not be displayed, &quot;Send&quot; button *should not* appear</blockquote>

					<blockquote>- <b>small ASCII text file</b>&nbsp; - file name and size should be displayed, &quot;Send&quot; button *should* now appear</blockquote>
					</li>
				</ul>
				</li>
				<li>click on &quot;Send&quot; button, prompts should appear: <span style="color: rgb(153, 0, 0);">&quot;Invalid or missing email&quot;</span> and <span style="color: rgb(153, 0, 0);">&quot;You MUST agree to the terms and conditions.&quot;</span></li>
				<li>enter one recipient email address (only) in the &quot;To&quot; field</li>
				<li>click on &quot;Send&quot; button again</li>
				<li>prompt should appear: <span style="color: rgb(153, 0, 0);">&quot;You MUST agree to the terms and conditions.&quot;</span></li>
				<li>show and verify AUP text, hide AUP text, check the AuP box</li>
				<li>click on &quot;Send&quot; button again, progress bar should appear, when complete new page should be displayed with text <span style="color: rgb(153, 0, 0);">&quot;Your file has been uploaded and message sent&quot;</span></li>
				<li><b>Authenticated only: </b><span style="color: rgb(153, 0, 0);"><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);">verify that file is listed in &quot;My Files&quot; table</span></span> </span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul style="color: rgb(11, 83, 148);">
	<li><i>click on the filename in the &quot;My Files&quot; table of uploaded ASCII file to download the file; verify that file has downloaded and can be opened</i></li>
	<li><i>click on link in the &quot;My File&quot;s table again to verify that the file can be downloaded more than once.</i></li>
</ul>

<p>&nbsp;</p>

<p><span style="font-weight: normal;">(env_myfiles.html; env_upload_end.html; logoff.html):</span></p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only:&nbsp;</b></span></span>verify links across top of [&quot;My Files&quot;] page (Send File, Guest Voucher, My Files, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;My Files&quot;; verify table headers (To, From, File Name, Size, Subject, Message, Created, Expiry) and action buttons (Re-send Email, Add new recipient, Delete)</li>
				<li><b>Authenticated only: </b>[click on &quot;Send File&quot; button]; verify links across top of&nbsp;page (Send File, Guest Voucher, My FIles, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;Send a file&quot;; <b>verify AUP box is now checked (only need to check once per FileSender session) (need to check box when using a voucher)</b>;<b> </b>logoff [from FileSender]</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p>&nbsp;</p>
(<span style="font-weight: normal;">voucher.html; env_upload_voucher_end.html; voucher_used.html)</span>:

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><b>Using Voucher only: </b>verify links across top of [&quot;Guest Voucher&quot;] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner</li>
				<li><b>Using Voucher only: </b>[click on voucher link in email again]; verify links across top of page (Help, About, Logon); verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify message <span style="color: rgb(153, 0, 0);">&quot;This voucher has already been used.&quot;</span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</li>
	<li>follow <b><a class="wiki_link" href="#file_download" title="File download">File download</a></b> instructions below to verify contents of upload notification email (no need to download file again).</li>
</ul>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<h3 id="63616e63656c20616e6420726573746172742028666c61736829206f7220726573756d65202868746d6c35292061757468656e746963617465642075706c6f61642c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Cancel and restart (Flash) or resume (HTML5) authenticated upload, single recipient, custom field contents</h3>

<p><b>Using voucher only: </b>(email_voucher_issue_singlerecipient_defaultfields.html; voucher.html; env_upload_voucher.html; <span style="font-weight: normal;">help_about_unauth.html</span>):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>select email; verify email subject [Voucher]; verify email addresses of sender, recipient and cc; verify email content, store and display voucher link [click on voucher link in email]; delete email</li>
				<li>verify links across top of [Voucher] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify title of panel is &quot;Send a File&quot;; <i style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents </i></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>(upload_ASCII_singlerecipient_defaultfields_cancelresume.html; upload_ASCII_singlerecipient_defaultfields_cancelresume_voucher.html):</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>enter one recipient email address (only) in the &quot;To&quot; field</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>enter custom &quot;Subject&quot; and &quot;Message&quot; fields with:</li>
			</ul>

			<blockquote>
			<pre>
<b>&lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></pre>
			</blockquote>

			<ul>
				<li>select expiry date as the next calendar day (for testing automatic file deletion)</li>
				<li>click on &quot;Browse&quot; button and select a largish file (~10 MB should be enough) - file size should be displayed, &quot;Send&quot; button should appear</li>
				<li>verify AUP text, verify that AUP box is not checked, check box</li>
				<li>click on &quot;Send&quot; button, but cancel / pause upload (using cancel button) before completion [click on &quot;No&quot;, then &quot;Yes&quot; - verify that buttons across top of page reappear for authenticated upload, and that all fields reset</li>
				<li>enter one recipient email address (only) in the &quot;To&quot; field</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>enter custom &quot;Subject&quot; and &quot;Message&quot; fields with:</li>
			</ul>

			<blockquote>
			<pre>
<b>&lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b>&nbsp;</pre>
			</blockquote>

			<ul>
				<li>select expiry date as the next calendar day (for testing automatic file deletion)</li>
				<li>click on &quot;Browse&quot; button and select a largish file (~10 MB should be enough) - file size should be displayed, &quot;Send&quot; button should appear</li>
				<li>verify that the AUP box remains checked from above upload (only need to check once per FileSender session) (need to check box when using a voucher)</li>
				<li>click on &quot;Send&quot; button again - progress bar should appear, file upload should start from the beginning for Flash only (0%) or from point where upload was paused for HTML5, click on &quot;Send&quot; two more times during upload [should only be possible using script], when complete new page should be displayed with text <span style="color: rgb(153, 0, 0);">&quot;Your file has been uploaded and message sent&quot;</span></li>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only: </b></span></span>verify file is listed in &quot;My Files&quot; table</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p><span style="font-weight: normal;">(env_myfiles.html; </span><span style="font-weight: normal;">help_about_auth.html; </span><span style="font-weight: normal;">env_upload_end.html; </span><span style="font-weight: normal;">logoff.html):</span></p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only:&nbsp;</b></span></span>verify links across top of [&quot;My Files&quot;] page (Send File, Guest Voucher, My Files, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;My Files&quot;; verify table headers (To, From, File Name, Size, Subject, Message, Created, Expiry) and action buttons (Re-send Email, Add new recipient, Delete); <i style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents </i></li>
				<li><b>Authenticated only: </b>[click on &quot;Send File&quot; button]; verify links across top of&nbsp;page (Send File, Guest Voucher, My FIles, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;Send a file&quot;; <b>verify AUP box is now checked (only need to check once per FileSender session) (need to check box when using a voucher)</b>;<b> </b>logoff [from FileSender]</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>(<span style="font-weight: normal;">voucher.html; env_upload_voucher_end.html; help_about_unauth.html; voucher_used.html)</span>:</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><b>Using Voucher only: </b>verify links across top of [&quot;Guest Voucher&quot;] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; <i style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents </i></li>
				<li><b>Using Voucher only: </b>[click on voucher link in email again]; verify links across top of page (Help, About, Logon); verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify message <span style="color: rgb(153, 0, 0);">&quot;This voucher has already been used.&quot;; <i style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents</i></span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</li>
	<li>follow <b><a class="wiki_link" href="#file_download" title="File download">File download</a></b> instructions below to download the uploaded file, <i style="color: rgb(11, 83, 148);">saving the emails for the files set to expire on the next calendar day, for later verification (see end)</i><span style="color: rgb(102, 102, 153);"><i style="color: rgb(11, 83, 148);"> </i></span></li>
	<li style="color: rgb(11, 83, 148);"><i>compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file</i></li>
</ul>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<h3 id="69736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382066696c652075706c6f61642c20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">ISO-8859-1 / non-ISO-8859-1 UTF8 file upload, recipients separated by comma / semi-colon, custom field contents</h3>

<p><b>Using voucher only: </b>(email_voucher_issue_singlerecipient_defaultfields.html; voucher.html; env_upload_voucher.html):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>select email; verify email subject [Voucher]; verify email addresses of sender, recipient and cc; verify email content, store and display voucher link [click on voucher link in email]; delete email</li>
				<li>verify links across top of [Voucher] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify title of panel is &quot;Send a File&quot;</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>(upload_ISO-8859-1_tworecipients_comma_customfields.html; upload_ISO-8859-1_tworecipients_comma_customfields_voucher.html)&nbsp; (upload_non-ISO-8859-1_tworecipients_semicolon_customfields.html; upload_non-ISO-8859-1_tworecipients_semicolon_customfields_voucher.html):</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<p>&nbsp;</p>

			<ul>
				<li>enter over the configured maximum number of recipient email addresses in the &quot;To&quot; field separated by [&quot;,&quot;for ISO-8859-1 case or &quot;;&quot; for non-ISO-8859-1 case] - message should appear <span style="color: rgb(153, 0, 0);">&quot;The maximum number of email addresses allowed is [X]&quot;</span> (where X is the configured maximum)</li>
				<li>enter two recipient email addresses separated by [&quot;,&quot;for ISO-8859-1 case or &quot;;&quot; for non-ISO-8859-1 case] in the &quot;To&quot; field - message should disappear</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>enter custom &quot;Subject&quot; and &quot;Message&quot; fields with:&nbsp;
				<ul>
					<li>[for ISO-8859-1 case]:</li>
				</ul>
				</li>
			</ul>

			<blockquote style="">
			<blockquote>
			<pre>
<b>&lt;tag&gt; bl&aring;b&aelig;rsyltet&oslash;y &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></pre>
			</blockquote>
			</blockquote>

			<ul>
				<li>
				<ul>
					<li>&nbsp;[for non-ISO-8859-1 UTF8 case]:</li>
				</ul>
				</li>
			</ul>

			<blockquote style="">
			<blockquote>
			<pre>
<b>&lt;tag&gt; žćčđ&scaron; &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></pre>
			</blockquote>
			</blockquote>

			<ul>
				<li>select expiry date</li>
				<li>click on &quot;Browse&quot; button and select [corresponding file listed below] - filename and size should be displayed, &quot;Send&quot; button should appear
				<ul>
					<li>[for ISO-8859-1 case]: <b><a href="/spaces/file_sender/documents/drg4ko9Ryr37zXeJe5cbCb/download?filename=utf8-iso8859-1-%C3%A7%C3%9F%C3%B8%C3%BE-test.txt">utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt</a></b></li>
					<li>[for non-ISO-8859-1 UTF8 case]: <b><a href="/spaces/file_sender/documents/dNfthu9Ryr35RVeJe5cbCb/download?filename=utf8-latin-extended-a-%C5%A1%C5%99%C5%AC%C5%B4-test.txt">utf8-latin-extended-a-šřŬŴ-test.txt</a> </b></li>
				</ul>
				</li>
				<li>verify AUP text, verify that AUP box is not checked, check box</li>
				<li>click on &quot;Send&quot; button three times in quick succession before progress bar appears, when complete new page should be displayed with text <span style="color: rgb(153, 0, 0);">&quot;Your file has been uploaded and message sent&quot;</span></li>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only: </b></span></span>verify file is listed in &quot;My Files&quot; table for each recipient</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p><span style="font-weight: normal;">(env_myfiles.html; env_upload_end.html; logoff.html):</span></p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only: </b></span></span>verify links across top of [&quot;My Files&quot;] page (Send File, Guest Voucher, My Files, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;My Files&quot;; verify table headers (To, From, File Name, Size, Subject, Message, Created, Expiry) and action buttons (Re-send Email, Add new recipient, Delete)</li>
				<li><b>Authenticated only: </b>[click on &quot;Send File&quot; button]; verify links across top of&nbsp;page (Send File, Guest Voucher, My FIles, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;Send a file&quot;; <b>verify AUP box is now checked (only need to check once per FileSender session) (need to check box when using a voucher)</b>;<b> </b>logoff [from FileSender]</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>(<span style="font-weight: normal;">voucher.html; env_upload_voucher_end.html; voucher_used.html)</span>:</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><b>Using Voucher only: </b>verify links across top of [&quot;Guest Voucher&quot;] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner</li>
				<li><b>Using Voucher only: </b>[click on voucher link in email again]; verify links across top of page (Help, About, Logon); verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify message <span style="color: rgb(153, 0, 0);">&quot;This voucher has already been used.&quot;</span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</li>
	<li>follow <b><a class="wiki_link" href="#file_download" title="File download">File download</a></b> instructions below to download the uploaded file</li>
</ul>

<h3 id="6c617267652066696c652075706c6f6164206f76657220322067622c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473202868746d6c35206f6e6c7929">Large file upload over 2 GB, single recipient, default field contents (HTML5 only)</h3>

<p><b>Using voucher only: </b>(email_voucher_issue_singlerecipient_defaultfields.html; voucher.html; env_upload_voucher.html):</p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>select email; verify email subject [Voucher]; verify email addresses of sender, recipient and cc; verify email content, store and display voucher link [click on voucher link in email]; delete email</li>
				<li>verify links across top of [Voucher] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify title of panel is &quot;Send a File&quot;</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>(upload_over2GB_singlerecipient_defaultfields_HTML5.html; upload_over2GB_singlerecipient_defaultfields_HTML5_voucher.html):</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>enter one recipient email address (only) in the &quot;To&quot; field</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>verify, but leave &quot;Subject&quot; and &quot;Message&quot; fields blank to verify defaults in email</li>
				<li>select expiry date</li>
				<li>click on &quot;Browse&quot; button and select a file over 2 GB - filename and size should be displayed, &quot;Send&quot; button should appear</li>
				<li>verify AUP text, verify that AUP box is not checked, check box</li>
				<li>click on &quot;Send&quot; button, progress bar should appear, when complete new page should be displayed with text <span style="color: rgb(153, 0, 0);">&quot;Your file has been uploaded and message sent&quot;</span></li>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only: </b></span></span>verify file is listed in &quot;My Files&quot; table</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p><span style="font-weight: normal;">(env_myfiles.html; env_upload_end.html; logoff.html):</span></p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><span style="color: rgb(153, 0, 0);"><span style="color: rgb(0, 0, 0);"><b>Authenticated only:&nbsp;</b></span></span>verify links across top of [&quot;My Files&quot;] page (Send File, Guest Voucher, My Files, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;My Files&quot;; verify table headers (To, From, File Name, Size, Subject, Message, Created, Expiry) and action buttons (Re-send Email, Add new recipient, Delete)</li>
				<li><b>Authenticated only: </b>[click on &quot;Send File&quot; button]; verify links across top of&nbsp;page (Send File, Guest Voucher, My FIles, Help, About, Log Off); verify version number; verify HTML5 logo; verify that name is displayed in top left corner &quot;Welcome [first name surname]&quot;; verify title of panel is &quot;Send a file&quot;; <b>verify AUP box is now checked (only need to check once per FileSender session) (need to check box when using a voucher)</b>;<b> </b>logoff [from FileSender]</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>(<span style="font-weight: normal;">voucher.html; env_upload_voucher_end.html; voucher_used.html)</span>:</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li><b>Using Voucher only: </b>verify links across top of [&quot;Guest Voucher&quot;] page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner</li>
				<li><b>Using Voucher only: </b>[click on voucher link in email again]; verify links across top of page (Help, About, Logon); verify that &quot;Welcome Guest&quot; (no name) is displayed in top left corner; verify message <span style="color: rgb(153, 0, 0);">&quot;This voucher has already been used.&quot;</span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</li>
	<li>follow <b><a class="wiki_link" href="#file_download" title="File download">File download</a></b> instructions below to download the uploaded file</li>
	<li style="color: rgb(11, 83, 148);"><i>compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file</i></li>
</ul>

<p style="text-align: center;"><span style="font-weight: normal;">-------------------------------------------------------------------------------------------------- </span></p>

<h2 id="--_downloads_(unauthenticated)_--">-- Downloads (unauthenticated) --</h2>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p><b>upload notification email</b> <span style="font-weight: normal;">(logon_email.html; reload_email.html)&nbsp; (email_ASCII_singlerecipient_defaultfields.html; email_ASCII_singlerecipient_defaultfields_voucher.html; email_ASCII_singlerecipient_defaultfields_cancelresume.html; email_ASCII_singlerecipient_defaultfields_cancelresume_voucher.html; email_ISO-8859-1_tworecipients_comma_customfields.html; email_ISO-8859-1_tworecipients_comma_customfields_voucher.html; email_non-ISO-8859-1_tworecipients_semicolon_customfields.html; email_non-ISO-8859-1_tworecipients_semicolon_customfields_voucher.html; email_over2GB_singlerecipient_defaultfields.html; email_over2GB_singlerecipient_defaultfields_voucher.html):</span></p>

<p><i><span style="color: rgb(11, 83, 148);"><b>(for all uploads except for ASCII file upload, single recipient, default field contents, upload prompts)</b></span></i><b><i><span style="color: rgb(11, 83, 148);"> </span></i></b></p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>logon to email account; select email; verify email subject; verify email addresses of sender, recipient and cc <b>[bcc email sent to voucher issuer]</b>; verify email content, store and display download link [load download link in new browser tab]</li>
				<li>delete email</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);"><b>For ASCII file uploads and large file upload over 2 GB only:</b> verify that (empty) message field is not displayed in email</span></i></li>
</ul>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>delete email</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p><b>download </b><span style="font-weight: normal;">(download.html; env_download.html; help_about_unauth.html) (download_ASCII_singlerecipient_defaultfields_cancelresume.html; download_ASCII_singlerecipient_defaultfields_cancelresume_voucher.html; download_ISO-8859-1_tworecipients_comma_customfields.html; download_ISO-8859-1_tworecipients_comma_customfields_voucher.html; download_non-ISO-8859-1_tworecipients_semicolon_customfields.html; download_non-ISO-8859-1_tworecipients_semicolon_customfields_voucher.html; download_over2GB_singlerecipient_defaultfields.html; download_over2GB_singlerecipient_defaultfields_voucher.html) (env_download.html; help_about_unauth.html)</span>:</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>verify links across top of page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is not displayed in top left corner; verify title of panel is &quot;Download&quot;</li>
				<li style="color: rgb(11, 83, 148);"><i><b>(Cancel and restart (Flash) or resume (HTML5) workflows only</b><b>): </b>click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents</i></li>
				<li>verify that &quot;To&quot; is autopopulated with recipient&#39;s email address</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>verify &quot;Subject&quot; and &quot;Message&quot; fields [...]</li>
				<li>verify filename and size of [...] file</li>
				<li>verify expiry date</li>
				<li>click on &quot;Start Download&quot; button, message should appear: <span style="color: rgb(153, 0, 0);">&quot;Your file should start downloading.&quot;</span></li>
				<li>verify links across top of page (Help, About, Logon); verify version number; verify HTML5 logo; verify that &quot;Welcome Guest&quot; (no name) is not displayed in top left corner; verify title of panel is &quot;Download&quot;</li>
				<li><i><b style="color: rgb(11, 83, 148);">(Cancel and restart (Flash) or resume (HTML5) workflows only</b><b style="color: rgb(11, 83, 148);">): </b><span style="color: rgb(11, 83, 148);">click on &quot;Help&quot; button and verify Help contents; click on HTML5 logo and verify Help contents; click on &quot;About&quot; button and verify About contents </span></i></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e">&nbsp;</h3>

<h3 id="">&nbsp;</h3>

<ul>
	<li>verify that file has downloaded and can be opened; verify that any non-ASCII characters (ISO-8859-1 / non-ISO-8859-1 UTF8 files) are preserved in the filename</li>
</ul>

<p><b>download notification email </b><span style="font-weight: normal;">(reload_email.html) (email_ASCII_singlerecipient_defaultfields_cancelresume_end.html; email_ASCII_singlerecipient_defaultfields_cancelresume_end_voucher.html; email_ISO-8859-1_tworecipients_comma_customfields_end.html; email_ISO-8859-1_tworecipients_comma_customfields_end_voucher.html; email_non-ISO-8859-1_tworecipients_semicolon_customfields_end.html; email_non-ISO-8859-1_tworecipients_semicolon_customfields_end_voucher.html; email_over2GB_singlerecipient_defaultfields_end.html; email_over2GB_singlerecipient_defaultfields_end_voucher.html) (logoff_email.html):</span></p>

<p>&nbsp;</p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>select email; verify email subject; verify email addresses of sender, recipient and cc <b>[bcc email sent to voucher issuer]</b>; verify email content, verify download link; delete email <span style="color: rgb(11, 83, 148);">[if not keeping to verify automatic file deletion]</span></li>
				<li>logoff [from email account</li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h3 id="">&nbsp;</h3>

<h2 id="--_re-send_new_email_(authenticated)_--">-- Re-Send New Email (authenticated) --</h2>

<h3 id="72652d73656e64206e657720656d61696c2c2061736369692c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Re-Send New Email, ASCII, single recipient, custom field contents</h3>

<ul>
	<li>click on &quot;My Files&quot; button</li>
	<li>next to the entry for the authenticated ASCII file upload, click on &quot;Re-Send Email&quot; button on the left - a prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Re-send Email. Are you sure you want to re-send this email?&quot;</span>, click on &ldquo;No&rdquo; button, view should return to table</li>
	<li>click on &quot;Re-Send Email&quot; button again, click on &quot;Yes&quot; button, another prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Message Re-sent&quot;</span></li>
	<li>verify receipt of email to both sender and recipient(s)</li>
	<li>repeat for the entry for the ASCII file uploaded using a voucher</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="2d2d20616464206e657720726563697069656e74202861757468656e7469636174656429202d2d3c62723e">-- Add New Recipient (authenticated) --</h2>

<h3 id="616464206e657720726563697069656e742c2061736369692c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Add New Recipient, ASCII, single recipient, custom field contents</h3>

<p>&nbsp;</p>

<ul>
	<li>click on &quot;My Files&quot; button</li>
	<li>click on &quot;Add New Recipient&quot; button to the left of uploaded ASCII file entry - a popup should appear <span style="color: rgb(0, 0, 0);">&quot;Add new recipient&quot;</span></li>
</ul>

<p>(addrecipient_ASCII_singlerecipient_customfields.html):<span style="color: rgb(0, 0, 0);"> </span></p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<ul>
				<li>verify but leave &quot;To&quot; field blank</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>verify that the default &quot;Subject&quot; and &quot;Message&quot; are same as original (i.e. blank), then enter custom subject and message:</li>
			</ul>

			<blockquote>
			<pre>
<b>&lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></pre>
			</blockquote>

			<ul>
				<li>verify that expiry date is the default</li>
				<li>verify that &quot;File to be Redistributed&quot; and &quot;Size&quot; fields are correct</li>
				<li>click on &quot;Send&quot; button, prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Invalid or missing email&quot;</span></li>
				<li>enter one recipient email address (only) in the &quot;To&quot; field</li>
				<li>click on &quot;Send&quot; button again, message should appear <span style="color: rgb(153, 0, 0);">&quot;Message Sent&quot;</span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li>verify file is listed in &quot;My Files&quot; table for new recipient and that details are displayed correctly</li>
	<li>verify receipt of notification email to sender and recipient, and that the content matches the input</li>
</ul>

<h3 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283137302c203235352c20313730293b223e3c2f7370616e3e616464206e657720726563697069656e742c2069736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382c2074776f20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">Add New Recipient, ISO-8859-1 / non-ISO-8859-1 UTF8, two recipients separated by comma / semi-colon, custom field contents</h3>

<p>&nbsp;</p>

<ul>
	<li>click on &quot;My Files&quot; button</li>
	<li>next to the relevant uploaded file entry, click on &ldquo;Add New Recipient&rdquo; button on the left - a popup should appear <span style="color: rgb(0, 0, 0);">&quot;Add new recipient&quot;</span></li>
</ul>

<p>(addrecipient_ISO-8859-1_tworecipients_comma_customfields.html; addrecipient_non-ISO-8859-1_tworecipients_semicolon_customfields.html):<span style="color: rgb(0, 0, 0);"> </span></p>

<table border="0" style="background-color: rgb(255, 255, 204);">
	<tbody>
		<tr>
			<td>
			<p>&nbsp;</p>

			<p>&nbsp;</p>

			<ul>
				<li>enter over the configured maximum number of recipient email addresses in the &quot;To&quot; field, separated by [&quot;,&quot;for ISO-8859-1 case or &quot;;&quot; for non-ISO-8859-1 case] - message should appear <span style="color: rgb(153, 0, 0);">&quot;The maximum number of email addresses allowed is [X]&quot;</span> (where X is the configured maximum)</li>
				<li>enter two recipient email addresses, separated by [&quot;,&quot;for ISO-8859-1 case or &quot;;&quot; for non-ISO-8859-1 case]</li>
				<li>verify that &quot;From&quot; is auto-populated with sender&#39;s email address</li>
				<li>verify that the default &quot;Subject&quot; and &quot;Message&quot; are the same as original email:</li>
			</ul>

			<ul>
				<li>
				<ul>
					<li>[for ISO-8859-1 case]:</li>
				</ul>
				</li>
			</ul>

			<blockquote style="">
			<blockquote>
			<pre>
<b>&lt;tag&gt; bl&aring;b&aelig;rsyltet&oslash;y &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></pre>
			</blockquote>
			</blockquote>

			<ul>
				<li>
				<ul>
					<li>&nbsp;[for non-ISO-8859-1 UTF8 case]:</li>
				</ul>
				</li>
			</ul>

			<blockquote style="">
			<blockquote>
			<pre>
<b>&lt;tag&gt; žćčđ&scaron; &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</b></pre>
			</blockquote>
			</blockquote>

			<ul>
				<li>select a different expiry date</li>
				<li>verify that &quot;File to be Redistributed&quot; and &quot;Size&quot; fields are correct:
				<ul>
					<li>[for ISO-8859-1 case]: <b><a href="/spaces/file_sender/documents/drg4ko9Ryr37zXeJe5cbCb/download?filename=utf8-iso8859-1-%C3%A7%C3%9F%C3%B8%C3%BE-test.txt">utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt</a></b></li>
					<li>[for non-ISO-8859-1 UTF8 case]: <b><a href="/spaces/file_sender/documents/dNfthu9Ryr35RVeJe5cbCb/download?filename=utf8-latin-extended-a-%C5%A1%C5%99%C5%AC%C5%B4-test.txt">utf8-latin-extended-a-šřŬŴ-test.txt</a> </b></li>
				</ul>
				</li>
				<li>click on &quot;Send&quot; button, message should appear <span style="color: rgb(153, 0, 0);">&quot;Message Sent&quot;</span></li>
			</ul>
			</td>
		</tr>
	</tbody>
</table>

<ul>
	<li>verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly</li>
	<li>verify receipt of notification email to sender and recipients, and that the content matches the input</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="2d2d2064656c6574652066696c65202861757468656e7469636174656429202d2d3c62723e">-- Delete File (authenticated) --</h2>

<ul>
	<li>click on &quot;My Files&quot; button</li>
	<li>next to the entry for an authenticated upload file, click on &quot;Delete&quot; button on the right - a prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Delete File. Are you sure you want to delete this File?&quot;</span> - click on &quot;No&quot; button, file should remain in table</li>
	<li>click on &quot;Delete&quot; button again and click on &quot;Yes&quot; button - file should disappear from table - message should appear <span style="color: rgb(153, 0, 0);">&quot;This file has been deleted.&quot;</span></li>
	<li>verify that an email is sent to uploader and recipients advising that the file has been deleted</li>
	<li>verify that the file can no longer be accessed - message should appear <span style="color: rgb(153, 0, 0);">&quot;This file has been deleted.&quot;</span></li>
	<li><b>repeat</b> for a file uploaded using a voucher and verify email advice</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="2d2d2064656c65746520766f7563686572202861757468656e7469636174656429202d2d3c62723e">-- Delete Voucher (authenticated) --</h2>

<ul>
	<li>click on &quot;Vouchers&quot; button</li>
	<li>next to the last voucher that was issued (which may now be the only voucher listed), click on &quot;Delete&quot; button on the right - a prompt should appear <span style="color: rgb(153, 0, 0);">&quot;Delete Voucher. Are you sure you want to delete this voucher?&quot;</span> - click on &quot;No&quot; button, voucher should remain in table</li>
	<li>click on &ldquo;Delete&rdquo; button again and click on &quot;Yes&quot; button - voucher should disappear from table, message should appear <span style="color: rgb(153, 0, 0);">&quot;Voucher Deleted.&quot;</span></li>
	<li>verify that deleted voucher is no longer listed in Voucher list</li>
	<li>verify whether an email is sent to voucher issuer and voucher recipient, advising that the voucher has been cancelled</li>
	<li>click on the email link pertaining to the deleted voucher again, to verify that it can no longer be used - message should appear <span style="color: rgb(153, 0, 0);">&quot;This voucher has been cancelled.&quot;</span></li>
</ul>
&nbsp;

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="2d2d206175746f6d6174696320766f756368657220616e642066696c652064656c6574696f6e20286e6578742064617929202d2d3c62723e">-- Automatic Voucher and File Deletion (next day) --</h2>

<ul>
	<li>click on the url in the email for the voucher that was set to expire on the next calendar day - message should appear <span style="color: rgb(153, 0, 0);">&quot;This voucher has been cancelled.&quot;</span></li>
	<li>confirm that corresponding voucher is no longer listed in the &quot;Guest Vouchers&quot; table</li>
	<li>click on the urls in the emails for the files (authenticated upload and upload using a voucher) that were set to expire on the next calendar day - message should appear <span style="color: rgb(153, 0, 0);">&quot;This file has been deleted.&quot;</span>.</li>
	<li>confirm that corresponding files are no longer listed in the &quot;My Files&quot; table</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<p>My contributions to this project involve client-side workflow testing of FileSender test installations and associated documentation. I am not a developer of FileSender. -- <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>.</p>

