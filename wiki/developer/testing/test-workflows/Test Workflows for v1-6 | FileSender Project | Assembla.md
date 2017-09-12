<p>&nbsp;</p>

<h2 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20726762283235352c203235352c20323535293b223e6f766572766965773c2f7370616e3e"><span style="background-color: rgb(255, 255, 255);">Overview</span></h2>

<p><span style="background-color: rgb(255, 255, 255);">The following provides a list of considerations and test workflows (both automated and manual) for and during client-side workflow testing of the local configuration and functionality of FileSender prior to the 1.6 release. See <a class="wiki_link" href="/wiki/show/file_sender/Test_Workflows" title="Test_Workflows">Test_Workflows</a> for links to details of tests conducted for other releases. </span><span style="background-color: rgb(255, 255, 255);">See <a class="wiki_link" href="/wiki/show/file_sender/Automated_Workflow_Tests" title="Automated_Workflow_Tests">Automated_Workflow_Tests</a> for details of workflow test automation.</span></p>

<p><span style="background-color: rgb(255, 255, 255);">These tests are based primarily on tests conducted by <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>. Contributions to these workflows also provided by <a href="https://www.assembla.com/profile/xjansen"> Xander Jansen</a>.</span></p>

<p><span style="background-color: rgb(255, 255, 255);">Please note that these test workflows may not represent an exhaustive list of all possible user actions. Also, some aspects of these workflows may become no longer applicable as FileSender develops. If you find anything incorrect, please advise, or correct it yourself if you have access.</span></p>

<p><span style="background-color: rgb(255, 255, 255);">Some related tickets from the 1.6 releases (only) are listed throughout for context. Other related tickets from the 1.6 releases include <a href="/spaces/file_sender/tickets/637">#637</a>, <a href="/spaces/file_sender/tickets/871">#871</a>, <a href="/spaces/file_sender/tickets/904">#904</a>, <a href="/spaces/file_sender/tickets/949">#949</a>, <a href="/spaces/file_sender/tickets/963">#963</a>, <a href="/spaces/file_sender/tickets/965">#965</a>, <a href="/spaces/file_sender/tickets/966">#966</a> and <a href="/spaces/file_sender/tickets/969">#969</a>.</span></p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="versions_tested">Versions Tested</h2>

<table align="left" border="0">
	<tbody>
		<tr>
			<td><b>FileSender release</b></td>
			<td><b>Installation </b></td>
			<td><b>Testing status</b></td>
			<td><b>Tests (to be) conducted</b></td>
			<td><b>HTML5 or Flash?</b></td>
			<td><b>OS</b></td>
			<td><b>Browser</b></td>
			<td><b>Flash Player version</b></td>
			<td><b>(To be) conducted by</b></td>
		</tr>
		<tr>
			<td>1.6-beta-1</td>
			<td>Terasender on</td>
			<td>Complete</td>
			<td>Basic functionality test (fully automated); all applicable to HTML5 case, except for over 2GB (mostly automated)</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8</td>
			<td>Firefox 25.0.1</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Basic functionality test, plus resending, adding recipients and deleting files and vouchers (only) (partly automated)</td>
			<td>HTML5</td>
			<td>Windows 7</td>
			<td>IE11</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Basic functionality test (partly automated); all applicable to Flash case (excludes over 2G) (partly automated)</td>
			<td>Flash</td>
			<td>Mac OSX 10.6.8</td>
			<td>Safari 5.1.10</td>
			<td>11.9.900.170</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Over 2 GB (only)</td>
			<td>HTML5</td>
			<td>Windows 7 SP1</td>
			<td>Firefox 26.0</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>Terasender off</td>
			<td>Complete</td>
			<td>Basic functionality test (only) (fully automated)</td>
			<td>HTML5</td>
			<td>Mac OSX 10.6.8</td>
			<td>Firefox 25.0.1</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Basic functionality test (only) (partly automated)</td>
			<td>HTML5</td>
			<td>Windows 7</td>
			<td>IE11</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Basic functionality test (only) (partly automated)</td>
			<td>Flash</td>
			<td>Mac OSX 10.6.8</td>
			<td>Safari 5.1.10</td>
			<td>11.9.900.170</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>Complete</td>
			<td>Over 2 GB (only)</td>
			<td>HTML5</td>
			<td>Windows 7 SP1</td>
			<td>Firefox 26.0</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a>&nbsp;</td>
		</tr>
	</tbody>
</table>

<p style="text-align: center;"><span style="background-color: rgb(255, 255, 255);">-------------------------------------------------------------------------------------------------- </span></p>

<h2 id="2d2d2062617369632066756e6374696f6e616c6974792074657374202d2d203c62723e">-- Basic Functionality Test --</h2>

<ul>
	<li>basic_functionality_testsuite.html</li>
	<li>conducted periodically during development and prior to full workflow testing; excludes verifying most fields and text.</li>
</ul>

<div style="text-align: center;"><span style="background-color: rgb(255, 255, 255);">-------------------------------------------------------------------------------------------------- </span></div>

<h2 id="--_notes_--">-- Notes --</h2>

<ul>
	<li><span style="font-weight: normal;"><b>Manual steps</b> are described below in blue italicised font.<b> </b></span></li>
	<li><span style="font-weight: normal;"><b>Each upload and download workflow is conducted twice:</b> once for a file uploaded as an authenticated user (</span>logoff after each authenticated upload workflow<span style="font-weight: normal;">), repeated for a file uploaded using a voucher. </span><b>&nbsp;</b></li>
	<li><b>Note about voucher recipient email addresses: </b>For voucher uploads, a recipient email addresses different from that of the authenticated voucher issuer and voucher recipient(s) is used for testing bcc email to the voucher issuer<span style="color: rgb(102, 102, 153);"><span style="color: rgb(0, 0, 0);"> (</span></span>bcc of each email is sent to voucher issuer in addition to voucher recipient and uploaded file recipients).&nbsp;</li>
</ul>

<h2 id="2d2d206578747261207374657073202d2d3c62723e">-- Extra steps --</h2>

<ul>
	<li><span style="font-weight: normal;"><b>Clear browser cache before starting tests </b></span></li>
	<li><b>Help and About: </b>before and after logon, verify that all links work in Help and About.</li>
	<li><b><b>Tooltips:</b></b> verify tooltips for email recipient fields, for upload (authenticated and using a voucher), adding a new recipient and issuing a voucher.</li>
	<li><b>My Files check:</b> Repeat one voucher upload scenario when logged off, and again logged in as another user (i.e. other than the user who issued the voucher) to ensure that files appear in voucher issuer&#39;s &quot;My Files&quot; table.<span style="color: rgb(0, 0, 0);">&nbsp;</span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>Add new recipient check:</b> For one</span><span style="color: rgb(0, 0, 0);"> test when adding a new recipient, enter / modify all fields, click on cancel, then verify that all fields have reset (to that described in tests) when trying to add a new recipient again. </span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>Voucher deletion permission check:</b> Load one voucher url as [...]?s=vouchers&amp;a=del&amp;id=[voucherid] when logged on as another user</span>, to verify that a user cannot delete another user&#39;s voucher - message should appear <i><span style="color: rgb(153, 0, 0);">&quot;You do not have permission to do this.&quot;</span></i><span style="color: rgb(0, 0, 0);">.</span>&nbsp;</li>
	<li><span style="color: rgb(0, 0, 0);"><b>Invalid expiry date check: </b>For file uploads (authenticated and using a voucher), adding a recipient and issuing a voucher, try entering an invalid expiry date &quot;0000&quot; - message should appears <i><span style="color: rgb(153, 0, 0);">&quot;Invalid expiry Date&quot;</span></i></span>. Also try manually typing in an expiry date earlier than the minimum and later than the maximum.</li>
	<li><b>Invalid voucher check:</b> Add download.php before the ? in the url of emailed but expired voucher and file download URLs (from authenticated upload and upload using a voucher) - message should appear <i><span style="color: rgb(153, 0, 0);">&quot;This Voucher is no longer Valid. Please contact the person that issued this voucher&quot;</span></i>, on a standard logon page when not logged on, or on a green background when logged on [<a href="/spaces/file_sender/tickets/904">#904</a>].</li>
	<li><b>Logoff checks: </b>On one occassion, logon, open a second FileSender tab in your browser, then logoff in one - if you refresh the tab in which you did not logoff, verify that you are logged out and are presented with the logon screen; in the tab you logged out in, click on the &quot;Back&quot; button in your browser - verify that are you still logged out, and are presented with the logon screen.<span style="color: rgb(0, 0, 0);"> Also try logging off then logging on from the logoff screen.</span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>AUP check:</b> </span><span style="color: rgb(0, 0, 0);">logon, upload a file, log off and back on (during the same browser session), verify that AUP box is no longer checked [<a href="/spaces/file_sender/tickets/1023">#1023</a>].</span></li>
	<li><span style="color: rgb(0, 0, 0);"><b>Characters in email subject check:</b> if email client does not preserve all &#39;dangerous&#39; characters (such as html codes), verify these in another client, for </span>upload (authenticated and using a voucher), resend email, adding a new recipient, downloading a file and voucher and file deletion.</li>
	<li><b>Keyboard keys and popup checks:</b> Compare the behaviour of Esc, Return and Space keys and clicking on &quot;X&quot;, &quot;No&quot; and &quot;Cancel&quot; buttons (where applicable) for: Logon (before logging on and after logging off) / Upload / Guest Voucher / My Files pages; Help and About (before and after logon); Upload progress popup (authenticated and using voucher); &quot;Cancel upload&quot; popup when canceling upload (authenticated and using voucher); Re-Send Email / Add new recipient / Delete File / Delete Voucher popups</li>
	<li><b>Extra manual steps: </b>verify recipient email address autocomplete (authenticated upload, upload using a voucher, issuing a voucher and adding a recipient); verify &quot;No file selected&quot; [Firefox only] prior to selecting a file to upload (authenticated upload and upload using a voucher); verify download status in MyFiles (for downloads directly from table and from emails) [<a href="/spaces/file_sender/tickets/597">#597</a>]; verify alternating MyFiles row colour [<a href="/spaces/file_sender/tickets/933">#933</a>], heading formatting [<a href="/spaces/file_sender/tickets/987">#987</a>] and message formatting [<a href="/spaces/file_sender/tickets/964">#964</a>]; verify sender and recipient email addresses in MyFiles and Guest Voucher tables; try clicking on &quot;Send&quot; and &quot;Send Voucher&quot; multiple times when adding recipient and issuing Guest Voucher.</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="">&nbsp;</h2>

<h2 id="2d2d2062726f7773657220666c61736820706c7567696e2c206a6176617363726970742073657474696e67732c2068746d6c3520646574656374696f6e20616e6420687474707320766572696669636174696f6e202d2d">-- Browser Flash plugin, Javascript settings, HTML5 detection and https verification --</h2>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">clear browser cache</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">disable Flash plugin and restart browser <b>[leave disabled for HTML5 case</b>]</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><b>[Flash case only]:</b> load FileSender logon page and logon, prompt should appear </span><span style="color: rgb(153, 0, 0);">&quot;This application requires Flash for uploading files. To install Flash Player go to www.adobe.com.&quot;</span><span style="color: rgb(11, 83, 148);"> with a hyperlink to www.adobe.com. Logoff, re-enable Flash plugin and restart browser</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">disable Javascript in browser</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">load FileSender logon page again, prompt should appear </span><span style="color: rgb(153, 0, 0);">&quot;JavaScript is turned off in your web browser. This application will not run without Javascript enabled in your web browser.&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">re-enable Javascript (no need to restart browser)</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">load FileSender logon page again</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that page cannot be reached by http (before and after logon) - should be accessible via https only</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that the correct &quot;HTML5 [tick]&quot; or &quot;HTML5 X&quot; icon is displayed, which indicates whether the browser (version) does support HTML5 (HTML5 case) or does not (Flash case) </span></i></li>
</ul>

<div style="text-align: center;"><span style="font-weight: normal;">-------------------------------------------------------------------------------------------------- </span></div>

<h2 id="--_issue_vouchers_(authenticated)_--">-- Issue Vouchers (authenticated) --</h2>

<ul>
	<li>voucher_issue_singlerecipient_tomorrowexpiry_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suite includes:</span></b><span style="font-size: 10pt; font-family: Arial;"> verify but leave &quot;To&quot; field blank;</span></span><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;"><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">custom &quot;Subject&quot; and &quot;Message&quot; fields with: &lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;;</span></span> select expiry date tomorrow; </span></span><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">enter one recipient email address (only) in the &quot;Send Vouchers To&quot; field</span></span></p>
	<style type="text/css">
	</style>
	</li>
</ul>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">save the email for the voucher set to expire on the next calendar day, for later verification (see end)&nbsp;</span></i></li>
	<li>[Related tickets: <a href="/spaces/file_sender/tickets/637">#637</a>, <a href="/spaces/file_sender/tickets/963">#963</a>]</li>
</ul>

<h3 id="c2a02d2d2075706c6f616473202861757468656e7469636174656420616e64207573696e67206120766f75636865722920616e6420646f776e6c6f616473202d2d">&nbsp;-- Uploads (authenticated and using a voucher) and downloads --</h3>

<h4 id="61736369692066696c652075706c6f61642c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473">ASCII file upload, single recipient, default field contents</h4>

<ul>
	<li>ASCII_singlerecipient_defaultfields_HTML5_testsuite.html</li>
	<li>ASCII_singlerecipient_defaultfields_HTML5_voucher_testsuite.html</li>
	<li>ASCII_singlerecipient_defaultfields_Flash_testsuite.html</li>
	<li>ASCII_singlerecipient_defaultfields_Flash_voucher_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include:</span></b><span style="font-size: 10pt; font-family: Arial;"> verify but leave &quot;To&quot; field blank; verify, but leave &quot;Subject&quot; and &quot;Message&quot; fields blank or default to verify defaults in email; verify expiry date field, but leave as default to verify in email; verify &quot;I accept the terms and conditions of this service&quot; AUP box and that it is not checked, but do not check box; select files with no file extension, invalid characters (HTML5 only), zero KB, .bat file, .exe file, .ex file, 2 GB (and 1 MB below), 4 GB (and 1 MB below), 5 GB, over 5 GB; upload small ASCII text file; enter one recipient email address (only) in the &quot;To&quot; field and check AUP box</span></span></p>
	<style type="text/css">
	</style>
	</li>
</ul>

<table>
	<tbody>
		<tr>
			<td><b>Notes on expected email recipient logic:</b></td>
			<td colspan="3" style="text-align: center;"><b>Upload</b></td>
			<td colspan="3" style="text-align: center;"><b>Download &nbsp; &nbsp;</b></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td style="text-align: center;"><b>Sender / cc</b></td>
			<td style="text-align: center;"><b>Recipient </b></td>
			<td style="text-align: center;"><b>Bcc </b></td>
			<td style="text-align: center;"><b>Sender / cc</b></td>
			<td style="text-align: center;"><b>Recipient</b></td>
			<td style="text-align: center;"><b>Bcc </b></td>
		</tr>
		<tr>
			<td><span style="color: rgb(53, 28, 117);">email1</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(53, 28, 117);">email1</span> issue voucher to <span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(204, 0, 0);">email2</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span> using voucher issued by <span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1 </span></td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<ul>
	<li><span style="color: rgb(11, 83, 148);"><i>click on the filename in the &quot;My Files&quot; table of uploaded ASCII file to download the file; verify that file can be opened</i></span></li>
	<li><span style="color: rgb(11, 83, 148);"><i>click on link in the &quot;My File&quot;s table again to verify that the file can be downloaded more than once</i></span></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify contents of upload notification email (no need to download file again), including</span><span style="color: rgb(11, 83, 148);"><span style="color: rgb(11, 83, 148);">that (empty) message field is not displayed in email</span></span> </i></li>
	<li><span style="color: rgb(11, 83, 148);"><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</span></li>
</ul>

<h4 id="61736369692066696c652075706c6f61642c206d756c7469706c652073656e646572732c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473c2a0">ASCII file upload, multiple senders, single recipient, default field contents&nbsp;</h4>

<ul>
	<li>ASCII_singlerecipient_defaultfields_multisender_testsuite.html</li>
	<li>ASCII_singlerecipient_defaultfields_multisender_voucher_testsuite.html</li>
	<li><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include:</span></b></span><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;"><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;"><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">enter one recipient email address (only) in the &quot;To&quot; field;</span></span> verify, but leave &quot;Subject&quot; and &quot;Message&quot; fields blank to verify defaults in email; verify expiry date field, but leave as default to verify in email; select small ASCII text file with single quote in filename; check AUP box</span></span></span></span></li>
</ul>

<p>&nbsp;</p>

<table>
	<tbody>
		<tr>
			<td><b>Notes on expected email recipient logic:</b></td>
			<td colspan="3" style="text-align: center;"><b>Upload</b></td>
			<td colspan="3" style="text-align: center;"><b>Download &nbsp; &nbsp;</b></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td style="text-align: center;"><b>Sender / cc</b></td>
			<td style="text-align: center;"><b>Recipient </b></td>
			<td style="text-align: center;"><b>Bcc </b></td>
			<td style="text-align: center;"><b>Sender / cc</b></td>
			<td style="text-align: center;"><b>Recipient</b></td>
			<td style="text-align: center;"><b>Bcc </b></td>
		</tr>
		<tr>
			<td><span style="color: rgb(61, 133, 198);">email4</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span></td>
			<td style="text-align: center;"><span style="color: rgb(111, 168, 220);">email4</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(111, 168, 220);">email4 </span></td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(106, 168, 79);">email5</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span></td>
			<td style="text-align: center;"><span style="color: rgb(106, 168, 79);">email5</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(106, 168, 79);">email5 </span></td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(61, 133, 198);">email4</span> issue voucher to <span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(111, 168, 220);">email4 </span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(106, 168, 79);">email5</span> issue voucher to <span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(106, 168, 79);">email5 </span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(204, 0, 0);">email2</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span> using voucher issued by <span style="color: rgb(111, 168, 220);">email4</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(111, 168, 220);">email4 </span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;"><span style="color: rgb(111, 168, 220);">email4 </span></td>
		</tr>
		<tr>
			<td><span style="color: rgb(204, 0, 0);">email2</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span> using voucher issued by <span style="color: rgb(106, 168, 79);">email5</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3</span></td>
			<td style="text-align: center;"><span style="color: rgb(106, 168, 79);">email5 </span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(106, 168, 79);">email5</span></td>
		</tr>
	</tbody>
</table>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">autocomplete recipient email address(es) </span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that the downloaded file can be opened</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);"><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</span></i></span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);"><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;"><span style="color: rgb(0, 0, 0);">[Related tickets: <a href="/spaces/file_sender/tickets/184">#184</a>, <a href="/spaces/file_sender/tickets/821">#821</a>, <a href="/spaces/file_sender/tickets/895">#895</a>, <a href="/spaces/file_sender/tickets/949">#949</a>]</span></span></span>&nbsp;</span></i> </span></i></li>
</ul>

<p>&nbsp;</p>

<h4 id="63616e63656c20616e6420726573746172742028666c61736829206f7220726573756d65202868746d6c35292061757468656e746963617465642075706c6f61642c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Cancel and restart (Flash) or resume (HTML5) authenticated upload, single recipient, custom field contents</h4>

<ul>
	<li>ASCII_singlerecipient_defaultfields_cancelresume_testsuite.html</li>
	<li>ASCII_singlerecipient_defaultfields_cancelresume_voucher_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include: </span></b><span style="font-size: 10pt; font-family: Arial;">enter one recipient email address (only) in the &quot;To&quot; field; custom &quot;Subject&quot; and &quot;Message&quot; fields with: &lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;; select expiry date as the next calendar day (for testing automatic file deletion); select a largish file (~10 MB should be enough); check AUP box; cancel / pause upload; verify that AUP box remains checked from cancelled / paused upload;</span></span><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;"><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">restart / resume upload; </span></span>click on &quot;Send&quot; two more times during upload (should only be possible using script); throughout click on &quot;Help&quot; button and verify Help contents, click on HTML5 logo and verify Help contents, click on &quot;About&quot; button and verify About contents</span></span></p>
	<style type="text/css">
	</style>
	</li>
	<li><i><span style="color: rgb(11, 83, 148);">** verify that HTML5 upload resumes from where it left off **</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">save the emails for the files set to expire on the next calendar day, for later verification (see end) </span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that the downloaded file can be opened</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file<i><span style="color: rgb(11, 83, 148);"><b>&nbsp;</b></span></i></span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);"><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</span></i> </span></i></li>
	<li>[Related ticket: <a href="/spaces/file_sender/tickets/1048">#1048</a>]</li>
</ul>

<h4 id="69736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382066696c652075706c6f61642c20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">ISO-8859-1 / non-ISO-8859-1 UTF8 file upload, recipients separated by comma / semi-colon, custom field contents</h4>

<ul>
	<li>ISO-8859-1_tworecipients_comma_customfields_testsuite.html</li>
	<li>ISO-8859-1_tworecipients_comma_customfields_voucher_testsuite.html</li>
	<li>non-ISO-8859-1_tworecipients_semicolon_customfields_testsuite.html</li>
	<li>non-ISO-8859-1_tworecipients_semicolon_customfields_voucher_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include:</span></b><span style="font-size: 10pt; font-family: Arial;"> enter over the configured maximum number of recipient email addresses, and then two recipient email addresses, in the &quot;To&quot; field separated by &quot;,&quot;for ISO-8859-1 case or &quot;;&quot; for non-ISO-8859-1 case; custom &quot;Subject&quot; and &quot;Message&quot; fields, for ISO-8859-1 case: &lt;tag&gt; bl&aring;b&aelig;rsyltet&oslash;y &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;, for non-ISO-8859-1 UTF8 case: &lt;tag&gt; žćčđ&scaron; &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;; select expiry date; select for ISO-8859-1 case:</span><span style="font-size: 10pt; font-family: Arial;">utf8-iso8859-1-ç&szlig;&oslash;&thorn;-test.txt, for non-ISO-8859-1 UTF8 case: utf8-latin-extended-a-šřŬŴ-test.txt; </span><span style="font-size: 10pt; font-family: Arial;">check AUP box; click on &quot;Send&quot; button three times in quick succession before progress bar appears</span></span></p>
	</li>
</ul>

<table>
	<tbody>
		<tr>
			<td><b>Notes on expected email recipient logic:</b></td>
			<td colspan="3" style="text-align: center;"><b>Upload</b></td>
			<td colspan="3" style="text-align: center;"><b>Download &nbsp; &nbsp;</b></td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td style="text-align: center;"><b>Sender / cc</b></td>
			<td style="text-align: center;"><b>Recipient </b></td>
			<td style="text-align: center;"><b>Bcc </b></td>
			<td style="text-align: center;"><b>Sender / cc</b></td>
			<td style="text-align: center;"><b>Recipient</b></td>
			<td style="text-align: center;"><b>Bcc </b></td>
		</tr>
		<tr>
			<td><span style="color: rgb(53, 28, 117);">email1</span> upload file to <span style="color: rgb(230, 145, 56);">email3<span style="color: rgb(0, 0, 0);"> and </span><span style="color: rgb(111, 168, 220);">email4</span></span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3<span style="color: rgb(0, 0, 0);">, </span><span style="color: rgb(111, 168, 220);">email4</span></span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(53, 28, 117);">email1</span> issue voucher to <span style="color: rgb(204, 0, 0);">email2<span style="color: rgb(0, 0, 0);"> and </span><span style="color: rgb(106, 168, 79);">email5</span></span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2<span style="color: rgb(0, 0, 0);">, </span><span style="color: rgb(106, 168, 79);">email5</span></span></td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
			<td style="text-align: center;">-</td>
		</tr>
		<tr>
			<td><span style="color: rgb(204, 0, 0);">email2</span> upload file to <span style="color: rgb(230, 145, 56);">email3</span> and <span style="color: rgb(111, 168, 220);">email4</span> using voucher issued by <span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3</span><span style="color: rgb(230, 145, 56);"><span style="color: rgb(0, 0, 0);">, </span><span style="color: rgb(111, 168, 220);">email4</span></span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
			<td style="text-align: center;"><span style="color: rgb(230, 145, 56);">email3 </span></td>
			<td style="text-align: center;"><span style="color: rgb(204, 0, 0);">email2 </span></td>
			<td style="text-align: center;"><span style="color: rgb(53, 28, 117);">email1</span></td>
		</tr>
	</tbody>
</table>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">verify that the downloaded file can be opened</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that any non-ASCII characters (ISO-8859-1 / non-ISO-8859-1 UTF8 files) are preserved in the filename</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);"><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list</span></i> </span></i></li>
	<li>[Related tickets: <a href="/spaces/file_sender/tickets/637">#637</a> and <a href="/spaces/file_sender/tickets/963">#963</a>]</li>
</ul>

<h4 id="6c617267652066696c652075706c6f6164206f76657220322067622c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473202868746d6c35206f6e6c7929">Large file upload over 2 GB, single recipient, default field contents (HTML5 only)</h4>

<ul>
	<li>over2GB_singlerecipient_defaultfields_HTML5_testsuite.html</li>
	<li>over2GB_singlerecipient_defaultfields_HTML5_voucher_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include:</span></b><span style="font-size: 10pt; font-family: Arial;"> enter one recipient email address (only) in the &quot;To&quot; field; verify, but leave &quot;Subject&quot; and &quot;Message&quot; fields blank to verify defaults in email; select expiry date</span><span style="font-size: 10pt; font-family: Arial;">; select a file over 2 GB; check AUP box</span></span></p>
	<style type="text/css">
	</style>
	</li>
</ul>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);">verify that</span><span style="color: rgb(11, 83, 148);"><span style="color: rgb(11, 83, 148);"> (empty) message field is not displayed in email</span></span> </i></span></i></span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that the downloaded file can be opened</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for uploaded and downloaded file</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><b>Using Voucher only: </b>verify that the used voucher has been deleted from the Voucher list<i><span style="color: rgb(11, 83, 148);"><i><span style="color: rgb(11, 83, 148);"> </span></i></span></i></span></i></li>
</ul>

<h3 id="--_re-send_new_email_(authenticated)_--">-- Re-Send New Email (authenticated) --</h3>

<p id="6c617267652066696c652075706c6f6164206f76657220322067622c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473202868746d6c35206f6e6c7929">&nbsp;</p>

<h4 id="72652d73656e64206e657720656d61696c2c2061736369692c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Re-Send New Email, ASCII, single recipient, custom field contents</h4>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;My Files&quot; button</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">next to the entry for the authenticated ASCII file upload, click on &quot;Re-Send Email&quot; button on the left - a prompt should appear </span><span style="color: rgb(153, 0, 0);">&quot;Re-send Email. Are you sure you want to re-send this email?&quot;</span><span style="color: rgb(11, 83, 148);">, click on &quot;No&quot; button, view should return to table</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;Re-Send Email&quot; button again, click on &quot;Yes&quot; button, another prompt should appear </span><span style="color: rgb(153, 0, 0);">&quot;Message Re-sent&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify receipt of email to both sender and recipient(s)</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">repeat for the entry for the ASCII file uploaded using a voucher </span></i></li>
</ul>

<h3 id="--_add_new_recipient_(authenticated)_--">-- Add New Recipient (authenticated) --</h3>

<h4 id="616464206e657720726563697069656e742c2061736369692c2073696e676c6520726563697069656e742c20637573746f6d206669656c6420636f6e74656e7473">Add New Recipient, ASCII, single recipient, custom field contents</h4>

<ul>
	<li>addrecipient_ASCII_singlerecipient_customfields_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suite includes:</span></b><span style="font-size: 10pt; font-family: Arial;"> verify but leave &quot;To&quot; field blank; enter custom subject and message: &lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;; verify that expiry date is the default; verify that file and size are correct</span></span></p>
	<style type="text/css">
	</style>
	</li>
</ul>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;My Files&quot; button</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;Add New Recipient&quot; button to the left of uploaded ASCII file entry - a popup should appear &quot;Add new recipient&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify file is listed in &quot;My Files&quot; table for new recipient and that details are displayed correctly</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify receipt of notification email to sender and recipient, and that the content matches the input</span></i></li>
</ul>

<h4 id="616464206e657720726563697069656e742c2069736f2d383835392d31202f206e6f6e2d69736f2d383835392d3120757466382c2074776f20726563697069656e74732073657061726174656420627920636f6d6d61202f2073656d692d636f6c6f6e2c20637573746f6d206669656c6420636f6e74656e7473">Add New Recipient, ISO-8859-1 / non-ISO-8859-1 UTF8, two recipients separated by comma / semi-colon, custom field contents</h4>

<ul>
	<li>addrecipient_ISO-8859-1_tworecipients_comma_customfields_testsuite.html</li>
	<li>addrecipient_non-ISO-8859-1_tworecipients_semicolon_customfields_testsuite.html</li>
	<li>
	<p><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include: </span></b><span style="font-size: 10pt; font-family: Arial;">enter over the configured maximum number of recipient email addresses, and then two recipient email addresses, in the &quot;To&quot; field separated by &quot;,&quot;for ISO-8859-1 case or &quot;;&quot; for non-ISO-8859-1 case; verify that the default &quot;Subject&quot; and &quot;Message&quot; are the same as original email, for ISO-8859-1 case: &lt;tag&gt; bl&aring;b&aelig;rsyltet&oslash;y &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;, for non-ISO-8859-1 UTF8 case: &lt;tag&gt; žćčđ&scaron; &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;; select a different expiry date</span></span><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">; verify that file and size are correct</span></span></p>
	<style type="text/css">
	</style>
	</li>
</ul>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;My Files&quot; button</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">next to the relevant uploaded file entry, click on &quot;Add New Recipient&quot; button on the left - a popup should appear &quot;Add new recipient&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify receipt of notification email to sender and recipients, and that the content matches the input</span></i></li>
</ul>

<h4 id="616464206e657720726563697069656e742c2061736369692066696c652075706c6f61642c20616c7465726e61746976652073656e646572732c2073696e676c6520726563697069656e742c2064656661756c74206669656c6420636f6e74656e7473203c62723e">Add New Recipient, ASCII file upload, alternative senders, single recipient, default field contents</h4>

<ul>
	<li>addrecipient_ASCII_singlerecipient_multisender_email4.html</li>
	<li>addrecipient_ASCII_singlerecipient_multisender_email5.html</li>
</ul>

<ul>
	<li><span style="color: rgb(56, 118, 29);"><b style=""><span style="font-size: 10pt; font-family: Arial;">Test suites include: </span></b><span style=""><span style="font-size: 10pt; font-family: Arial;">enter one recipient email address (only) in the &quot;To&quot; field</span></span>; enter custom subject and message:</span><span style="color: rgb(56, 118, 29);"><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">&lt;tag&gt; text &amp;&quot;&#39;&gt;&lt;/?\n&#39;&quot;</span></span>; verify that expiry date is the default</span><span style="color: rgb(56, 118, 29);"><span style="font-size: 10pt; font-family: Arial;">; verify that file and size are correct</span></span></li>
</ul>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;My Files&quot; button</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">next to the relevant uploaded file entry, click on &quot;Add New Recipient&quot; button on the left - a popup should appear &quot;Add new recipient&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify file is listed in &quot;My Files&quot; table for each recipient and that details are displayed correctly</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify receipt of notification email to sender and recipients, and that the content matches the input</span></i></li>
</ul>

<h3 id="--_delete_file_(authenticated)_--">-- Delete File (authenticated) --</h3>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;My Files&quot; button</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">next to the entry for an authenticated upload file, click on &quot;Delete&quot; button on the right - a prompt should appear </span><span style="color: rgb(153, 0, 0);">&quot;Delete File. Are you sure you want to delete this File?&quot;</span><span style="color: rgb(11, 83, 148);"> - click on &quot;No&quot; button, file should remain in table</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;Delete&quot; button again and click on &quot;Yes&quot; button - file should disappear from table - message should appear </span><span style="color: rgb(153, 0, 0);">&quot;This file has been deleted.&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that an email is sent to uploader and recipient(s) advising that the file <span style="color: rgb(153, 0, 0);">&quot;has been deleted and is no longer available for download&quot;</span></span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that the file can no longer be accessed - message should appear </span><span style="color: rgb(153, 0, 0);">&quot;This file has been deleted.&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);"><b>repeat</b> for a file uploaded using a voucher and verify email advice</span></i></li>
</ul>

<h3 id="--_delete_voucher_(authenticated)_--">-- Delete Voucher (authenticated) --</h3>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;Vouchers&quot; button</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">next to the last voucher that was issued (which may now be the only voucher listed), click on &quot;Delete&quot; button on the right - a prompt should appear </span><span style="color: rgb(153, 0, 0);">&quot;Delete Voucher. Are you sure you want to delete this voucher?&quot;</span><span style="color: rgb(11, 83, 148);"> - click on &quot;No&quot; button, voucher should remain in table</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">click on &quot;Delete&quot; button again and click on &quot;Yes&quot; button - voucher should disappear from table, message should appear </span><span style="color: rgb(153, 0, 0);">&quot;Voucher Deleted.&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that deleted voucher is no longer listed in Voucher list </span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">verify that an email is sent to voucher issuer and recipient(s), advising that the <span style="color: rgb(153, 0, 0);">&quot;voucher has been cancelled&quot;</span></span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">click on the email link pertaining to the deleted voucher again, to verify that it can no longer be used - message should appear </span><span style="color: rgb(153, 0, 0);">&quot;This voucher has been cancelled.&quot;</span></i></li>
</ul>

<p id="2d2d2064656c6574652066696c65202861757468656e7469636174656429202d2d3c62723e">&nbsp;</p>

<h3 id="--_automatic_voucher_and_file_deletion_(next_day)_--">-- Automatic Voucher and File Deletion (next day) --</h3>

<ul>
	<li><i><span style="color: rgb(11, 83, 148);">click on the url in the email for the voucher that was set to expire on the next calendar day - message should appear </span><span style="color: rgb(153, 0, 0);">&quot;This voucher has been cancelled.&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">confirm that corresponding voucher is no longer listed in the &quot;Guest Vouchers&quot; table </span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">click on the urls in the emails for the files (authenticated upload and upload using a voucher) that were set to expire on the next calendar day - message should appear </span><span style="color: rgb(153, 0, 0);">&quot;This file has been deleted.&quot;</span></i></li>
	<li><i><span style="color: rgb(11, 83, 148);">confirm that corresponding files are no longer listed in the &quot;My Files&quot; table </span></i></li>
</ul>

<div style="text-align: center;"><span style="background-color: rgb(255, 255, 255);">-------------------------------------------------------------------------------------------------- </span></div>

<p><span style="background-color: rgb(255, 255, 255);">My contributions to this project involve client-side workflow testing of FileSender test installations and associated documentation. I am not a developer of FileSender. -- <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>.</span></p>

<p>&nbsp;</p>

