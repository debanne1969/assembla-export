<p>&nbsp;</p>

<h1 id="case_1_-_test_report_up-_and_downloading_large_files_(filesender_0.1.15)">Case 1 - Test report up- and downloading large files (FileSender 0.1.15)</h1>

<h2 id="636f6e6475637465642062793a">Conducted by:</h2>

<p><a href="https://www.assembla.com/profile/xjansen">Xander Jansen</a></p>

<p>These tests were conducted against the filesender-0.1.16.201008310000 nightly build with two non published developer files (filesender.swf and download.php). The two developer files contained preliminary code for the move from download through the Flash-interface to a download using the standard browser download functionality through a PHP backend (to eliminate all kinds of 32bits stuff preventing the download of very large files on some platforms).</p>

<h2 id="summary">Summary</h2>

<ul>
	<li>All major browsers except for Safari tested on a Win7 platform. All browsers can download very large files (&gt; 4GB) using the PHP download function.</li>
	<li>Specifying a download location with a dialog box is browser-dependent. Can this be forced by filesender to always ask for a location (and name) to save the file?</li>
	<li>Uploading is relatively slow which triggers a 8 hour simplesaml session duration limit. See notes for details.</li>
	<li>Using SSL still impacts the download speed (not using SSL will triple the download rates in our test setup)</li>
	<li>(local) storage performance is a significant factor when downloading (fast local disk versus slow(er) network share). In our test setup download speeds were doubled when using only fast local storage.</li>
	<li>IE8 and Safari use a temporary file on the disk with the user profile (default setup) and appear to &#39;ignore&#39; disk full situations.</li>
</ul>

<h2 id="uploading">Uploading</h2>

<p>Source file was created on a Linux machine with dd containing random data:</p>

<ul>
	<li><strong>Size in bytes:</strong> 107352743800 100GB-random.dat</li>
	<li><strong>MD5: </strong>580b805cc0e82744af7a7294f64e8a58 100GB-random.dat</li>
</ul>

<p>File was uploaded from a Windows 7 VM with good connectivity (1Gbps) and a short path to the filesender instance. Upload speeds of 113 Mbps with scp (!) are possible.</p>

<p>The 100GB file was located on a samba share (introducing additional network IO between the share and the VM). Note that downloading to a (fast) local disk can double/triple the download speeds as opposed to downloading to a (slowish) network share.</p>

<p>The upload initially was done from the VM with FireFox, reaching a max speed of about 4 Mbps (with Gears). Due to a 8 hour limit in simplsaml (see below) the upload had to be done in a few steps. The last part was done with Google Chrome which appeared to be twice as fast (8 Mbps) in this specific setup where the source file was located on a network share.</p>

<p><strong>Important:</strong> default authenticated session duration is 8 hours. This will break uploads taking longer than 8 hours. Workaround, increase session.duration in the simplesaml config.php. It might be worthwhile to research a better solution (more &#39;intelligent&#39; checking of authN stuff during a long upload or similar). Also the &#39;not authenticated&#39; error handling might be improved.</p>

<h2 id="downloading">Downloading</h2>

<p>All downloads were done on a Windows 7 VM with around 45G free (local) disk space. Due to the size of the file the file needed to be saved to a networkshare. This will have some impact on the download-speed. For comparison also a 40GB file was up- and downloaded to local storage (where possible, see IE notes). All downloads were done using a developer build of the Flash app with a &#39;Test button&#39; to force a PHP-download and circumventing Flash.</p>

<p>&nbsp;</p>

<table border="0">
	<tbody>
		<tr>
			<td><strong>Browser</strong></td>
			<td><strong>Version</strong></td>
			<td><strong>OS</strong></td>
			<td><strong>SSL</strong></td>
			<td><strong>100GB</strong></td>
			<td><strong>(share)</strong></td>
			<td><strong>40 GB</strong></td>
			<td>(local)</td>
		</tr>
		<tr>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td><em>hh:mm</em></td>
			<td><em>Mbps</em></td>
			<td><em>mm:ss</em></td>
			<td><em>Mbps</em></td>
		</tr>
		<tr>
			<td><strong>IE8</strong></td>
			<td>&nbsp;</td>
			<td>Win7</td>
			<td>+</td>
			<td>-</td>
			<td>-</td>
			<td>27:20 (<strong>1:20:00</strong>)</td>
			<td>200 (<strong>70</strong>)</td>
		</tr>
		<tr>
			<td><strong>Chrome</strong></td>
			<td>&nbsp;</td>
			<td>Win7</td>
			<td>+</td>
			<td>4:34</td>
			<td>50</td>
			<td>57:51</td>
			<td>94</td>
		</tr>
		<tr>
			<td><strong>FireFox</strong></td>
			<td>&nbsp;</td>
			<td>Win7</td>
			<td>+</td>
			<td>7:15</td>
			<td>31</td>
			<td>56:09</td>
			<td>97</td>
		</tr>
		<tr>
			<td><strong>Opera</strong></td>
			<td>&nbsp;</td>
			<td>Win7</td>
			<td>+</td>
			<td>8:36</td>
			<td>26</td>
			<td>45:56</td>
			<td>119</td>
		</tr>
		<tr>
			<td><strong>Safari</strong></td>
			<td>5.0.2</td>
			<td>Win7</td>
			<td>TLSv1 RC4-SHA</td>
			<td>-</td>
			<td>-</td>
			<td>1:46:26</td>
			<td>52</td>
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

<p>&nbsp;</p>

<table border="0">
	<tbody>
		<tr>
			<td><strong>Browser</strong></td>
			<td><strong>OS</strong></td>
			<td><strong>Comments</strong></td>
			<td><strong>100 GB</strong></td>
			<td><strong>40 GB (to local storage)</strong></td>
		</tr>
		<tr>
			<td><strong>IE8</strong></td>
			<td>Win7</td>
			<td>&nbsp;</td>
			<td>- starts and downloads smoothly (between 50 Mbps and 200 Mbps approx).<br />
			- only 14 GB downloaded although IE8 reports a complete transfer of the 100GB. Cause: IE8 downloads to a temp file on the local storage and apparently stops when that partition is full. It then copies the temp file to the actual given location (in this case on a share with plenty available space). Apparently a full disk for the temp file isn&#39;t correctly handled by IE8. App note: when downloading large files with IE8 the maximum size of the file to be downloaded is determined by the available free space on the partition where the &#39;personal profile&#39; of the user is stored. If you are downloading to that same partition the available space has to be at least twice the size of the file to be downloaded (due to a copy instead of a move of the tempfile). The Tempfile is stored in the &#39;Temporary Internet Items&#39; folder. Its location can be changed under Tools, Internet Options, General, Browsing History Settings. Be careful to take a note/screenshot of the current location in case you want to revert back to the standard location of the &#39;Temporary Internet Files&#39; folder. Note that it appears to be impossible to &#39;move&#39; the Temporary Internet Items folder to a share. Given these restrictions I could not test a complete 100G download with IE8.</td>
			<td>Start: [05/Sep/2010:11:15:44 +0200]<br />
			Stop: 5 Sep 2010 11:43:04 +0200<br />
			Total: 27:20 mm:ss<br />
			= 200 Mbps - 25 MB/s<br />
			<br />
			Note that this was only the download speed, after that IE had to copy the tempfile to the final location which took a long time. According to IE total &#39;transfer rate&#39; was 1 hour and 20 minutes at 8.43MB/s, including the copy to (in this case) a network share.</td>
		</tr>
		<tr>
			<td><strong>Google Chrome</strong></td>
			<td>Win7</td>
			<td>Default a file will be downloaded to default download dir without dialog, set preference to always ask for save location. File will be directly downloaded to the given location, no temporary storage or move/copy action after download. Took about 5 hours, 6 MB/s according to Chrome.</td>
			<td>Start: [03/Sep/2010:15:18:26 +0200]<br />
			Stop: 3 Sep 2010 19:52:36 +0200<br />
			Total: 4:34 hh:mm<br />
			= 50 Mbps - 6.2 MB/s</td>
			<td>Start: [05/Sep/2010:12:40:35 +0200]<br />
			Stop: 5 Sep 2010 13:38:26 +0200<br />
			Total 57:51 mm:ss<br />
			= 94 Mbps - 11.8 MB/s</td>
		</tr>
		<tr>
			<td><strong>Opera</strong></td>
			<td>Win7</td>
			<td>Opera asks for specific location, after that it &#39;hangs&#39; for a while (not responding) but recovers from the hang and starts downloading. As with Chrome to the specified location without temporary stuff.</td>
			<td>Start: [03/Sep/2010:20:11:31 +0200]<br />
			Stop: 4/sep/2010 04:47<br />
			Total 8:36 hh:mm<br />
			= 26 Mbps - 3.3 MB/s (Opera: 3513.5 KB/s)</td>
			<td>Start: [05/Sep/2010:17:28:01 +0200]<br />
			Stop: 5 Sep 2010 18:13:57<br />
			Total: 45:56 mm:ss<br />
			= 119 Mbps - 14.9 MB/s</td>
		</tr>
		<tr>
			<td><strong>FireFox</strong></td>
			<td>Win7</td>
			<td>Default file will be downloaded to default download dir without dialog, set preference to always ask for save location. File will be directly downloaded to the given location.</td>
			<td>Start: [04/Sep/2010:07:28:50 +0200]<br />
			Stop: 4 Sep 2010 14:43:12<br />
			Total: 7:15 hh:mm<br />
			= 31 Mbps - 4 MB/s</td>
			<td>Start: [05/Sep/2010:15:17:04 +0200]<br />
			Stop: 5 Sep 2010 16:13:13<br />
			Total: 56:09 mm:ss<br />
			= 97 Mbps - 12.2 MB/s</td>
		</tr>
		<tr>
			<td>
			<p><strong>Safari for Windows</strong></p>
			</td>
			<td>Win7</td>
			<td>Testing failed, files larger than a few MB stall after the first 50 to 100 MB.&nbsp; This appears to be unrelated to the download stuff and looks like some local issue (direct downloads circumventing the php stuff also fail, large downloads from other sites are OK). Might be some weird interaction between high speed and download over SSL, direct downloads without SSL are OK (and bloody fast, 380Mbps).<br />
			<br />
			Other tests show that Safari also uses a temporary file when downloading (stored in the local &#39;user profile&#39;). And, as with IE8, it does appear to ignore &#39;disk full&#39; situations, it just goes on downloading (network traffic continues) even when zero space is available. Might be a Win7 local issue?<br />
			Disabling keepalive for Safari on the server (Apache) seems to help a bit</td>
			<td>&nbsp;</td>
			<td>Start: 18/Sep/2010:20:03:46<br />
			Stop: 18 Sep 2010 21:50:12<br />
			Total: 1:46:26<br />
			52 Mbps</td>
		</tr>
	</tbody>
</table>

