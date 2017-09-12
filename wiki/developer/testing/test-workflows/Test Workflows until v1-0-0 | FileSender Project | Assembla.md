<p>&nbsp;</p>

<p>These tests are based primarily on usage of the <a href="http://www.aarnet.edu.au/" target="_blank">AARNet, the Australian National Research and Educational Network (NREN)</a> installation of FileSender by <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>. Contributions to these workflows also provided by <a href="https://www.assembla.com/profile/xjansen"> Xander Jansen</a> based on the <a href="http://www.surfnet.nl">SURFnet</a> installation of FileSender.</p>

<ul>
	<li><a class="wiki_link" href="#versions_tested" title="Versions Tested">Versions Tested</a></li>
	<li><a class="wiki_link" href="#overview" title="Overview">Overview</a></li>
	<li><a class="wiki_link" href="#general_considerations_throughout_test_workflows" title="General Considerations Throughout Test Workflows">General Considerations Throughout Test Workflows</a>
	<ul>
		<li><a class="wiki_link" href="#flash_and_google_gears_installation_and_file_size_handling" title="Flash and Google Gears Installation and File Size Handling">Flash and Google Gears Installation and File Size Handling</a></li>
		<li><a class="wiki_link" href="#local_configuration" title="Local Configuration">Local Configuration</a></li>
		<li><a class="wiki_link" href="#identity_and_notification" title="Identity and Notification">Identity and Notification</a></li>
		<li><a class="wiki_link" href="#expiration" title="Expiration">Expiration</a></li>
		<li><a class="wiki_link" href="#appearance" title="Appearance">Appearance</a></li>
		<li><a class="wiki_link" href="#refreshing_pages" title="Refreshing Pages">Refreshing Pages</a></li>
	</ul>
	</li>
	<li><a class="wiki_link" href="#test_workflows" title="Test Workflows">Test Workflows</a>
	<ul>
		<li><a class="wiki_link" href="#new_upload" title="New Upload">New Upload</a></li>
		<li><a class="wiki_link" href="#re-send_new_email" title="Re-Send New Email">Re-Send New Email</a></li>
		<li><a class="wiki_link" href="#add_new_recipient" title="Add New Recipient">Add New Recipient</a></li>
		<li><a class="wiki_link" href="#deleting_a_file" title="Deleting a File">Deleting a File</a></li>
		<li><a class="wiki_link" href="#issuing_a_voucher" title="Issuing a Voucher">Issuing a Voucher</a></li>
		<li><a class="wiki_link" href="#using_a_voucher_to_upload_a_file" title="Using a Voucher to Upload a File">Using a Voucher to Upload a File</a></li>
		<li><a class="wiki_link" href="#deleting_a_voucher" title="Deleting a Voucher">Deleting a Voucher</a></li>
		<li><a class="wiki_link" href="#downloading_an_uploaded_file_or_voucher_(complete_for_both)" title="Downloading an Uploaded File or Voucher (complete for both)">Downloading an Uploaded File or Voucher (complete for both)</a></li>
		<li><a class="wiki_link" href="#non-ascii_characters" title="Non-ASCII Characters">Non-ASCII Characters</a></li>
		<li><a class="wiki_link" href="#logoff" title="Logoff">Logoff</a></li>
	</ul>
	</li>
</ul>

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
			<td><a class="wiki_link" href="/wiki/show/file_sender/Beta-1-13" title="Beta-1-13">0.1.13</a></td>
			<td><a href="https://cloudstor1.aarnet.edu.au/">https://cloudstor1.aarnet.edu.au</a></td>
			<td>Complete</td>
			<td>Flash only (no Gears)</td>
			<td>Mac OSX</td>
			<td>FF 3.6.?</td>
			<td>10.?</td>
			<td>N/A</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td><a class="wiki_link" href="/wiki/show/file_sender/Beta-1-15" title="Beta-1-15">0.1.15</a> (patched)</td>
			<td><a href="https://cloudstor1.aarnet.edu.au/">https://cloudstor1.aarnet.edu.au</a></td>
			<td>Complete</td>
			<td>Flash for most tests, repeated basic tests with Gears as described</td>
			<td>Mac OSX</td>
			<td>FF 3.6.8</td>
			<td>10.?</td>
			<td>0.5.36.0</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td><a class="wiki_link" href="/wiki/show/file_sender/Beta-1-16" title="Beta-1-16">0.1.1.6.1</a></td>
			<td><a href="https://cloudstor.aarnet.edu.au">https://cloudstor.aarnet.edu.au</a></td>
			<td>Complete (tested selecting 2GB and 4GB files for upload without Flash, but not actually uploading them using Gears as using a mac)</td>
			<td>Gears for most tests, repeated basic tests with Flash</td>
			<td>Mac OSX</td>
			<td>FF 3.6.10</td>
			<td>10.1.82.76</td>
			<td>0.5.36.0</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td>Pre-0.1.17 development version</td>
			<td><a href="http://apps3.vetvirtual.org/cloudstor/">http://apps3.vetvirtual.org/cloudstor/</a></td>
			<td>Complete - testing of non-ASCII characters, separately for subject, message and filename</td>
			<td>Flash and Gears</td>
			<td>Mac OSX</td>
			<td>FF 3.6.12</td>
			<td>10.1.85.3</td>
			<td>0.5.36.0</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a>, using files created and tested by <a href="https://www.assembla.com/profile/xjansen"> Xander Jansen</a></td>
		</tr>
		<tr>
			<td><a class="wiki_link" href="/wiki/show/file_sender/Beta-1-17" title="Beta-1-17">0.1.17</a></td>
			<td><a href="https://cloudstor.aarnet.edu.au">https://cloudstor.aarnet.edu.au</a></td>
			<td>Complete, except for AuP checkbox which has been disabled in this installation; also tested downloading from MyFiles table</td>
			<td>created tickets <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/339">#339</a></span>, <a href="/spaces/file_sender/tickets/342">#342</a> &amp; <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/347">#347</a></span>, updated <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/325">#325</a></span></td>
			<td>Mac OSX 10.6.5</td>
			<td>FF 3.6.12</td>
			<td>10.1.102.64</td>
			<td>0.5.36.0</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
		<tr>
			<td><a class="wiki_link" href="/wiki/show/file_sender/Beta-1-19" title="Beta-1-19">0.1.19</a></td>
			<td><a href="https://cloudstor.aarnet.edu.au">https://cloudstor.aarnet.edu.au</a></td>
			<td>Complete, except for AuP checkbox which has been disabled in this installation</td>
			<td>created tickets <a href="/spaces/file_sender/tickets/356">#356</a>, <a href="/spaces/file_sender/tickets/357">#357</a></td>
			<td>Mac OSX 10.6.5</td>
			<td>FF 3.6.13</td>
			<td>10.1.102.64</td>
			<td>0.5.36.0</td>
			<td><a href="https://www.assembla.com/profile/wendy_mason">Wendy Mason</a></td>
		</tr>
	</tbody>
</table>

<h2 id="overview">Overview</h2>

<p>The following is a sample list of considerations and workflows for testing the local configuration and functionality of a FileSender beta release installation. Text in square brackets needs to be verified, does not yet happen or requires some other form of attention. Tickets closed prior to the <a class="wiki_link" href="/wiki/show/file_sender/Beta-1-13" title="Beta-1-13">Beta-1-13</a> release are not referenced.</p>

<p>These tests are based on the <a href="http://www.aarnet.edu.au/" target="_blank">AARNet, the Australian National Research and Educational Network (NREN)</a> installation of FileSender. Please note that these are <strong>*sample*</strong> workflows only, and are <strong>*not*</strong> intended to be an exhaustive list of all possible user actions. Also, some aspects of these workflows may become no longer applicable as FileSender develops. If you find anything incorrect, please advise, or correct it yourself if you have access.</p>

<p><strong>Note: </strong>email1 = email address of account holder / sender; email2 = email address of file or voucher recipient.</p>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="general_considerations_throughout_test_workflows">General Considerations Throughout Test Workflows</h2>

<h3 id="flash_and_google_gears_installation_and_file_size_handling">Flash and Google Gears Installation and File Size Handling</h3>

<ul>
	<li><strong>Note: </strong>behaviour may be different with (as opposed to without) <a href="http://gears.google.com/" target="_blank">Google Gears</a> installed (see <a class="wiki_link" href="/wiki/show/file_sender/b516sOlY8r3PPQeJe5afGb#requirements" title="b516sOlY8r3PPQeJe5afGb#Requirements">Requirements section of homepage</a>). Google Gears is required to upload files larger than 2GB (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/255">#255</a>,</span> <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/322">#322</a></span>) (files larger than 4GB (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/249">#249</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/254">#254</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/256">#256</a></span>)). Restarting your browser is required after enabling / disabling the Gears plugin</li>
	<li>if the minimum version of <a href="http://www.adobe.com/products/flashplayer/" target="_blank">Adobe Flash Player</a> is not installed, is a message displayed prompting the user to install / upgrade Flash? (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/108">#108</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/268">#268</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/269">#269</a></span>)</li>
	<li>in the top right hand corner, is the relevant Gears icon displayed, with an &quot;X&quot; if not installed or disabled, or with a tick / check mark if installed and enabled?</li>
</ul>

<h3 id="local_configuration">Local Configuration</h3>

<ul>
	<li>is any local header image displayed (if applicable) (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/293">#293</a></span>)?</li>
	<li>is the local name (as opposed to / in addition to FileSender) reflected in the heading, introductory text (above logon button), browser tab titles, email subject, email autosignatures, &quot;Help&quot; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/191">#191</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/234">#234</a></span>, <a href="/spaces/file_sender/tickets/292">#292</a>) and &quot;About&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/192">#192</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/234">#234</a></span>, <a href="/spaces/file_sender/tickets/292">#292</a>, <a href="/spaces/file_sender/tickets/355">#355</a>)?</li>
	<li>is the local webserver only reachable over HTTPS? (See &ldquo;Warning: Encryption&rdquo; section of the <a class="wiki_link" href="/wiki/show/file_sender/Administrator_reference_manual" title="Administrator_reference_manual">Administrator_reference_manual</a>) and is your connection fully encrypted to prevent eavesdropping, for every step during your FileSender session (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/238">#238</a></span>)?</li>
	<li>does the browser status bar display &ldquo;Done&rdquo; after a page has loaded?</li>
	<li>Is the AuP text box (when uploading files) populated (if included in local configuration)?</li>
</ul>

<h3 id="identity_and_notification">Identity and Notification</h3>

<ul>
	<li>after logging on, is your name displayed correctly in the top left-hand corner (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/200">#200</a></span>)?</li>
	<li>are email1 and email2 always in the correct fields (i.e. not reversed) (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/190">#190</a></span>)</li>
	<li>are email1 and email2 complete in emails (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/180">#180</a></span>)?</li>
	<li>when downloading a shared file, uploading a file with a voucher, or downloading a file from a voucher, are you recognised as Guest, even if you are logged on in another browser tab?</li>
	<li>when logged in, are FileSender buttons and header (version number, Help and About, Gears logo) displayed?</li>
	<li>when recognised as Guest, is the FileSender header (version number, Help and About, Gears logo) displayed, but not FileSender buttons?</li>
	<li>do both the sender and recipient (of file uploads and vouchers, and deletion thereof) receive notification emails, and are they formatted correctly (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/248">#248</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/333">#333</a></span>)?</li>
	<li>is the file uploader / voucher issuer notified when a file has been downloaded or a voucher used?</li>
	<li>is there any difference in behaviour or appearance when downloading a file (uploaded or from voucher) when logged in, versus when logged out?</li>
</ul>

<h3 id="expiration_and_date_formats">Expiration and Date Formats</h3>

<ul>
	<li>when uploading or re-sharing a file, or issuing a voucher, does the expiration date selection start from the following day (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/239">#239</a></span>), default to the local maximum, is that date highlighted in blue (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/270">#270</a></span>), and are you prevented from selecting any date later than this?</li>
	<li>are expiration date formats consistent across emails and tables (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/274">#274</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/295">#295</a></span>)?</li>
	<li>are files and vouchers automatically deleted after expiration (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/240">#240</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/353">#353</a></span>)?</li>
	<li>are expiration dates consistent across FileSender GUI, File download and voucher file download emails, File upload and voucher file upload emails and Voucher issue email? (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/274">#274</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/295">#295</a></span>)</li>
	<li><strong>Note: </strong>testing expiration (i.e. automatic deletion) of uploaded file(s) and voucher(s) requires revisiting the site again after selected expiration date, so selection of the next calendar date is recommended. (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/194">#194</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/195">#195</a></span>)</li>
</ul>

<h3 id="appearance">Appearance</h3>

<ul>
	<li><span style="font-size: medium;">&nbsp;</span>check for consistent font formatting and syntax (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/201">#201</a></span>), background colours, use of new pages versus pop-up boxes, when buttons are greyed out (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/304">#304</a></span>)</li>
</ul>

<h3 id="refreshing_pages">Refreshing Pages</h3>

<ul>
	<li><span style="font-size: medium;">&nbsp;</span>after downloading a file (shared or with voucher), does refreshing the page enable you to access the same file again? (<a href="/spaces/file_sender/tickets/187">#187</a>)</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<h2 id="test_workflows">Test Workflows</h2>

<h3 id="flash_installation_prompt">Flash Installation Prompt</h3>

<ul>
	<li>disable Flash plugin and restart browser</li>
	<li>load FileSender logon page, prompt should appear to install Flash player with a link (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/108">#108</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/237">#237</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/268">#268</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/269">#269</a></span>)</li>
	<li>re-enable Flash plugin and restart browser</li>
	<li>before and after logging on to FileSender, click on the About and help links and verify content (<a href="/spaces/file_sender/tickets/292">#292</a>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/335">#335</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/336">#336</a></span>)</li>
	<li>logon to FileSender for remaining tests with Flash enabled</li>
</ul>

<h3 id="new_upload">New Upload</h3>

<h4 id="2d20666c617368202864697361626c6520676561727320706c7567696e20696620696e7374616c6c65642c20726573746172742062726f7773657229">- Flash (disable Gears plugin if installed, restart browser)</h4>

<ul>
	<li>leave &ldquo;To&rdquo; field blank</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with email1</li>
	<li>leave &ldquo;Subject&rdquo; and &ldquo;Message&rdquo; fields blank, to verify defaults</li>
	<li>select expiry date (see <strong>Expiration</strong> notes above)</li>
	<li>click on &ldquo;Browse&rdquo; button and select a file to upload (that does not contain any non-ASCII characters in the filename) - file size should be displayed, &ldquo;Send&rdquo; button should appear</li>
	<li>do not check the &ldquo;I accept the terms and conditions of this service&rdquo; (AuP) box, click on &ldquo;Send&rdquo; button - pop-up box should appear &ldquo;Message. Please check email address&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/261">#261</a></span>)</li>
	<li>enter email2 (at least one recipient, two are even better) in the &ldquo;To&rdquo; field</li>
	<li>do not check the AuP box, click on &ldquo;Send&rdquo; button - prompt should appear &ldquo;Message. You MUST agree to the terms and conditions.&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/261">#261</a></span>)</li>
	<li>read the AuP terms and conditions, check the AuP box</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear (<a href="/spaces/file_sender/tickets/176">#176</a>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/186">#186</a></span>) and progress steps should be listed, when complete new page should be displayed with text &ldquo;Your file has been uploaded and message sent&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/189">#189</a></span>)</li>
	<li>click on &ldquo;New Upload&rdquo; button, verify that the AuP box remains checked (only need to check once per FileSender session)</li>
	<li>verify receipt of notification email to sender (email1) and recipient (email2), and that the content matches the input (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/248">#248</a></span>)</li>
	<li>verify file is listed in &quot;My Files&quot; table</li>
	<li><strong>repeat</strong> with custom subject, and message with multiple lines of text (ASCII text only) (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/248">#248</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/302">#302</a></span>)</li>
	<li><strong>repeat</strong>, cancelling the upload before completion - do the buttons reappear (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/317">#317</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/319">#319</a></span>)?</li>
	<li><strong>repeat</strong>, trying to upload a file 2 GB (and 1 MB below), which should fail - prompt should appear to install Google Gears (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/313">#313</a></span>)</li>
	<li><strong>repeat</strong>, trying to upload a file 4 GB (and 1 MB below), which should also fail - prompt should appear to install Google Gears (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/305">#305</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/313">#313</a></span>)</li>
</ul>

<h4 id="2d2067656172732028656e61626c6520676561727320706c7567696e2c20726573746172742062726f7773657229">- Gears (enable Gears plugin, restart browser)</h4>

<ul>
	<li>generate and make note of an <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for the file you are uploading</li>
	<li>enter email address, check AuP box, browse for file (that does not contain any non-ASCII characters in the filename) and click on submit</li>
	<li>monitor upload progress to completion (<a href="/spaces/file_sender/tickets/290">#290</a>)</li>
	<li><strong>repeat</strong>, pausing and resuming (using cancel button) during upload (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/84">#84</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/289">#289</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/291">#291</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/310">#310</a></span>)</li>
	<li><strong>repeat</strong>, trying to upload a file 2 GB (and 1 MB below), message &quot;Mac using gears cannot upload a file larger that 2GB (Error <a href="/spaces/file_sender/tickets/032">#032</a>)&quot; (<a href="/spaces/file_sender/tickets/176">#176</a>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/255">#255</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/322">#322</a></span>)</li>
	<li><strong>repeat</strong>, trying to upload a file 4 GB (and 1 MB below), message &quot;Mac using gears cannot upload a file larger that 2GB (Error <a href="/spaces/file_sender/tickets/032">#032</a>)&quot; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/174">#174</a></span>, <a href="/spaces/file_sender/tickets/176">#176</a>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/255">#255</a></span>)</li>
</ul>

<h3 id="re-send_new_email_(flash_or_gears)">Re-Send New Email (Flash or Gears)</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to an uploaded file entry, click on &ldquo;Re-Send Email&rdquo; button on the left - a pop-up window should appear &ldquo;Re-send. Are you sure you want to re-send this Email?&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/273">#273</a></span>), click on &ldquo;Cancel&rdquo; button, view should return to table</li>
	<li>click on &ldquo;Re-Send Email&rdquo; button again, click on &ldquo;OK&rdquo; button, another pop-up window should appear &ldquo;Email has been sent&rdquo;</li>
	<li>verify receipt of email to both email1 and email2</li>
</ul>

<h3 id="add_new_recipient_(flash_or_gears)">Add New Recipient (Flash or Gears)</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to an uploaded file entry, click on &ldquo;Add New Recipient&rdquo; button on the left - a pop-up window should appear &ldquo;Add Recipient&rdquo;</li>
	<li>leave &ldquo;To&rdquo; field blank</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated with email1</li>
	<li>verify that the default &ldquo;Subject&rdquo; and &quot;Message&quot; are the same as original email subject</li>
	<li>leave &ldquo;Message&rdquo; field unchanged, to verify default</li>
	<li>select expiry date (see <strong>Expiration</strong> notes above)</li>
	<li>verify that &ldquo;File to be Redistributed&rdquo; and &ldquo;Size&rdquo; fields are correct</li>
	<li>click on &ldquo;Send&rdquo; button</li>
	<li>pop-up box should appear &ldquo;Please check email address&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/259">#259</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/260">#260</a></span>), click on &ldquo;OK&rdquo; button</li>
	<li>enter new recipient&rsquo;s email address (email2 would be fine)</li>
	<li>another pop-up window should appear &ldquo;Email has been sent&rdquo;, click on &ldquo;OK&rdquo; button</li>
	<li>verify receipt of notification email to sender (email1) and recipient (email2), and that the content matches the input (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/248">#248</a></span>)</li>
	<li><strong>repeat</strong> above steps with modified subject and message</li>
</ul>

<h3 id="issuing_a_voucher_(flash_or_gears)">Issuing a Voucher (Flash or Gears)</h3>

<ul>
	<li>click on &ldquo;Vouchers&rdquo; button</li>
	<li>verify that explanatory text about how to use Vouchers is present (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/197">#197</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/263">#263</a></span>)</li>
	<li>select expiry date (see <strong>Expiration</strong> notes above)</li>
	<li>click on &ldquo;Send Voucher&rdquo; button - pop-up box should appear &ldquo;Message. Please check email address&rdquo;, click on &ldquo;OK&rdquo; button</li>
	<li>in the &ldquo;Send Vouchers to:&rdquo; field, enter email2</li>
	<li>click on &ldquo;Send Voucher&rdquo; button - a pop-up window should appear &ldquo;Voucher Sent&rdquo; - click on &ldquo;OK&rdquo; button</li>
	<li>verify that issued voucher is now listed in Vouchers table</li>
	<li>verify that email notification with &ldquo;Voucher&rdquo; in the title is sent to both email1 and email2, and that text is correct (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/248">#248</a></span>)</li>
	<li><strong>repeat</strong> these step to create a second voucher (to delete later)</li>
	<li><strong>repeat</strong> these step to create a third voucher, setting the expiry date to the next calendar day (to verify automatic expiration)</li>
	<li><strong>repeat</strong> these step to create a fourth voucher, for testing an upload using Gears</li>
</ul>

<h3 id="using_a_voucher_to_upload_a_file">Using a Voucher to Upload a File</h3>

<h4 id="2d20666c617368202864697361626c6520676561727320706c7567696e20696620696e7374616c6c65642c20726573746172742062726f7773657229">- Flash (disable Gears plugin if installed, restart browser)</h4>

<ul>
	<li>click on link in the email pertaining to the first voucher</li>
	<li>verify that you are recognised as Guest (even when you are logged on in another browser tab)</li>
	<li>leave &ldquo;To&rdquo; field blank</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email2</li>
	<li>verify that the default &ldquo;Subject&rdquo; is &ldquo;Voucher&rdquo;</li>
	<li>leave &ldquo;Message&rdquo; field blank, to verify default</li>
	<li>select expiry date (see <strong>Expiration</strong> notes above)</li>
	<li>click on &ldquo;Browse&rdquo; button and select a file to upload (that does not contain any non-ASCII characters in the filename) - file size should be displayed (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/264">#264</a></span>), &ldquo;Send&rdquo; button should appear</li>
	<li>do not check the AuP box, click on &ldquo;Send&rdquo; button - pop-up box should appear &ldquo;Message. Please check email address&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/261">#261</a></span>)</li>
	<li>enter email1 into the &ldquo;To&rdquo; field</li>
	<li>do not check the AuP box, click on &ldquo;Send&rdquo; button- pop-up box should appear &ldquo;Message. You MUST agree to the terms and conditions&quot; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/261">#261</a></span>)</li>
	<li>read the AuP terms and conditions, check the AuP box</li>
	<li>click on &ldquo;Send&rdquo; button - progress bar should appear and progress steps should be listed, when complete new page should be displayed with text &ldquo;Your file has been sent&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/185">#185</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/193">#193</a></span>)</li>
	<li>verify receipt of notification email to sender (email2) and recipient (email1) (plus any others in recipient list), and that the content matches the input and uses the voucher email template (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/230">#230</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/267">#267</a></span>)</li>
	<li>verify that uploaded file is listed in sender&#39;s My Files table</li>
	<li>verify that used voucher is no longer listed in Vouchers table</li>
	<li>click on the link again in the voucher issue email, verify that the voucher cannot be used a second time - text should appear &quot;This file/voucher is no longer available&quot;</li>
	<li><strong>repeat</strong> with custom subject, and message with multiple lines of text (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/248">#248</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/302">#302</a>)</span></li>
	<li><strong>repeat</strong> again but cancel upload during progress and observe behaviour (should still be able to use voucher, voucher should still be listed in Vouchers table)</li>
	<li><strong>repeat</strong>, trying to upload a file 2 GB (and 1 MB below), which should fail - prompt should appear to install Google Gears</li>
	<li><strong>repeat</strong>, trying to upload a file 4 GB (and 1 MB below), which should also fail - prompt should appear to install Google Gears (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/305">#305</a></span>)</li>
</ul>

<h4 id="2d2067656172732028656e61626c6520676561727320706c7567696e2c20726573746172742062726f7773657229">- Gears (enable Gears plugin, restart browser)</h4>

<ul>
	<li>generate and make note of an <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for the file you are uploading</li>
	<li>click on link in the email pertaining to the fourth voucher</li>
	<li>enter email address, check AuP box, browse for file and click on submit</li>
	<li>monitor upload progress to completion (<a href="/spaces/file_sender/tickets/290">#290</a>)</li>
	<li><strong>repeat</strong>, pausing and resuming (using cancel button) during upload (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/84">#84</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/289">#289</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/291">#291</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/310">#310</a></span>)</li>
	<li><strong>repeat</strong>, trying to upload a file 2 GB (and 1 MB below), message &quot;Mac using gears cannot upload a file larger that 2GB (Error <a href="/spaces/file_sender/tickets/032">#032</a>)&quot; (<a href="/spaces/file_sender/tickets/176">#176</a>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/255">#255</a></span>)</li>
	<li><strong>repeat</strong>, trying to upload a file 4 GB (and 1 MB below), message &quot;Mac using gears cannot upload a file larger that 2GB (Error <a href="/spaces/file_sender/tickets/032">#032</a>)&quot; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/174">#174</a></span>, <a href="/spaces/file_sender/tickets/176">#176</a>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/255">#255</a></span>)</li>
</ul>

<h3 id="deleting_a_voucher_(flash_or_gears)">Deleting a Voucher (Flash or Gears)</h3>

<ul>
	<li>in the Vouchers table, delete the last voucher that was issued (which may now be the only voucher listed) by clicking on Delete button on the right</li>
	<li>verify whether an email is sent to email1 and email2 advising that the voucher has been cancelled (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/196">#196</a>,</span> <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/272">#272</a></span>)</li>
	<li>click on the email link pertaining to the deleted voucher again, to verify that it can no longer be used, text should appear &quot;This voucher has been cancelled&quot; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/198">#198</a></span>)</li>
</ul>

<h3 id="646f776e6c6f6164696e6720616e2075706c6f616465642066696c65206f7220766f75636865722028636f6d706c65746520666f7220626f7468292028666c617368206f72206765617273202d2067656172732069736e2774207573656420666f7220646f776e6c6f61647329">Downloading an Uploaded File or Voucher (complete for both) (Flash or Gears - Gears isn&#39;t used for downloads)</h3>

<ul>
	<li>click on the link in email (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/347">#347</a></span>)</li>
	<li>verify that you recognised as Guest (even if you are logged on in another browser tab)</li>
	<li>verify that &ldquo;To&rdquo; is auto-populated by email2 for uploaded file [email1 for voucher file]</li>
	<li>verify that &ldquo;From&rdquo; is auto-populated by email1 for uploaded file [email2 for voucher file]</li>
	<li>verify that all other fields match the input</li>
	<li>click on &ldquo;Start Download&rdquo; button and click on the &quot;Save File&quot; button - new page should appear displaying text &ldquo;Your file should start downloading&rdquo; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/188">#188</a></span>, <span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/247">#247</a></span>, <a href="/spaces/file_sender/tickets/307">#307</a>)</li>
	<li>refresh page - can you download the file a second time (<a href="/spaces/file_sender/tickets/187">#187</a>)???</li>
	<li>verify that file has downloaded and can be opened (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/298">#298</a></span>)</li>
	<li>verify that an email is sent to both email1 and email2 (plus any others in recipient list), notifying that the above file has been downloaded (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/299">#299</a></span>, <a href="/spaces/file_sender/tickets/307">#307</a>)</li>
	<li><strong>repeat</strong> download to verify that the file can be downloaded more than once</li>
	<li>download file from My Files table, and verify as for link from email above (<a href="/spaces/file_sender/tickets/342">#342</a>)</li>
	<li>download and compare <a href="http://en.wikipedia.org/wiki/MD5" target="_blank">MD5</a>&nbsp;/&nbsp;<a href="http://en.wikipedia.org/wiki/SHA-1" target="_blank">SHA-1</a>&nbsp;etc. hash for all files previously uploaded using Gears</li>
</ul>

<h3 id="deleting_a_file_(flash_or_gears)">Deleting a File (Flash or Gears)</h3>

<ul>
	<li>click on &ldquo;My Files&rdquo; button</li>
	<li>next to an uploaded file entry, click on &ldquo;Delete&rdquo; button on the right - a pop-up window should appear &ldquo;Delete File. Are you sure?&rdquo; - click on &ldquo;Cancel&rdquo; button, file should remain in table</li>
	<li>click on &ldquo;Delete&rdquo; button again and click on &ldquo;OK&rdquo; button - file should disappear from table</li>
	<li>verify that an email is sent to email1 and email2 advising that the file has been deleted (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/272">#272</a></span>)</li>
	<li>verify that the file can no longer be accessed, message &quot;This file / Voucher is no longer available&quot; (<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/339">#339</a></span>)</li>
	<li><strong>repeat</strong> for a file uploaded using a voucher and verify email advice</li>
</ul>

<h3 id="6e6f6e2d61736369692063686172616374657273202872657065617420656163682074657374207573696e6720666c61736820616e642067656172732c20726573746172742062726f7773657220616674657220656e61626c696e67202f2064697361626c696e6720676561727320706c7567696e292028233332312c20233332352c2023333435293a">Non-ASCII Characters (repeat each test using Flash and Gears, restart browser after enabling / disabling Gears plugin) (<a href="/spaces/file_sender/tickets/321">#321</a>, <a href="/spaces/file_sender/tickets/325">#325</a>, <a href="/spaces/file_sender/tickets/345">#345</a>):</h3>

<p><strong>TEST 1 (ISO-8859-1</strong><strong>):</strong><strong> subject - </strong>bl&aring;b&aelig;rsyltet&oslash;y; <strong>message -</strong> bl&aring;b&aelig;rsyltet&oslash;y; <strong>filename -</strong> <a href="/spaces/file_sender/documents/drg4ko9Ryr37zXeJe5cbCb/download?filename=utf8-iso8859-1-%C3%A7%C3%9F%C3%B8%C3%BE-test.txt">utf8-iso8859-1-&ccedil;&szlig;&oslash;&thorn;-test.txt</a><br />
<strong>TEST 2 (non-ISO-8859-1 UTF8</strong><strong>):</strong> <strong>subject -</strong> žćčđ&scaron;; <strong>message -</strong> žćčđ&scaron;; <strong>filename -</strong> <a href="/spaces/file_sender/documents/dNfthu9Ryr35RVeJe5cbCb/download?filename=utf8-latin-extended-a-%C5%A1%C5%99%C5%AC%C5%B4-test.txt">utf8-latin-extended-a-šřŬŴ-test.txt</a></p>

<ul>
	<li>upload, download from email, download from MyFiles</li>
	<li>resend email, download from email</li>
	<li>add new recipient, download from email, download from MyFiles, delete both files</li>
	<li>issue voucher, upload from email, download from email, download from MyFiles, delete file</li>
</ul>

<h3 id="logoff">Logoff</h3>

<ul>
	<li>before logging off, open a second FileSender tab in your browser, then logoff in one - if you refresh the tab in which you did not logoff, are you logged out, and are you presented with the logon screen?</li>
	<li>in the tab you logged out in, click on the &ldquo;Back&rdquo; button in your browser - are you still logged out, and are you presented with the logon screen?</li>
	<li>(<span style="text-decoration: line-through;"><a href="/spaces/file_sender/tickets/278">#278</a></span>).</li>
</ul>

<p style="text-align: center;">--------------------------------------------------------------------------------------------------</p>

<p>My contributions to this project are as a Monash University user, beta-tester and release tester of the <a href="http://www.aarnet.edu.au/" target="_blank">AARNet, the Australian National Research and Educational Network (NREN)</a> installation of FileSender. I am not a developer of FileSender. -- <a href="https://www.assembla.com/profile/wendy_mason"> Wendy Mason</a>.</p>

