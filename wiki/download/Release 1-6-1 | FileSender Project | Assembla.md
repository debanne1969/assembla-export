<h2 id="release_version_1.6.1">Release Version 1.6.1</h2>

<p>Release date:&nbsp; 30 December 2015</p>

<table border="0">
	<tbody>
		<tr>
			<td><b>Distribution file</b></td>
			<td><b>MD5</b></td>
			<td><b>SHA1</b></td>
		</tr>
		<tr>
			<td><a href="https://downloads.filesender.org/filesender-1.6.1.tar.gz">filesender-1.6.1.tar.gz</a></td>
			<td><span style="font-family: courier new,courier;">03b30c8812d9240365039171dcde0e0d</span></td>
			<td>75e95efdf639f82a27b277c1d29f85f140867c3b</td>
		</tr>
		<tr>
			<td><a href="https://downloads.filesender.org/filesender-1.6.1.zip">filesender-1.6.1.zip</a></td>
			<td><span style="font-family: courier new,courier;">bbad7057f45f6352c65598da653d1a37</span></td>
			<td>87001c778ccaa561cf2a5243f06211303521f6b7</td>
		</tr>
	</tbody>
</table>

<p>Release 1.6.1 is also available in the <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Debian_Ubuntu" title="Installation_-_Debian_Ubuntu">Debian</a> and <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_RPM" title="Installation_-_RPM">RPM</a> package repositories and the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.6.1/">Subversion repository</a>. Currently Release 1.6.1 is distributed from the <b>testing</b> repositories.</p>

<h2 id="installation">Installation</h2>

<p>Documentation for this release is available at <a class="wiki_link" href="/wiki/show/file_sender/Documentation_v1-6" title="Documentation v1-6">Documentation v1-6</a></p>

<p>&nbsp;</p>

<div>
<h2 id="upgrade_notes">Upgrade Notes</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Upgrade_notes" title="Upgrade notes">Upgrade notes</a> for important upgrade and installation notes.&nbsp;&nbsp;</p>

<p>&nbsp;</p>

<h2 id="major_changes_since_1.5">Major changes since 1.5</h2>

<p>&nbsp;&nbsp;&nbsp;&nbsp; - New: high-speed upload module &#39;TeraSender&#39; (<a href="/spaces/file_sender/tickets/891">#891</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: auto-complete in the To: field (<a href="/spaces/file_sender/tickets/821">#821</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: refactored MyFiles, file downloaded dates provide audit<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; trail when download Cc:s switched off<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: support for configurable footer via language file (<a href="/spaces/file_sender/tickets/871">#871</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: support for optional Subject and Message in guest use voucher<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (<a href="/spaces/file_sender/tickets/637">#637</a>, <a href="/spaces/file_sender/tickets/774">#774</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: support for multiple From: addresses from authentication<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; source (<a href="/spaces/file_sender/tickets/184">#184</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: configurable option &#39;download_confirmation_to_downloader&#39; for<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; sending download email receipt to file recipients (default &#39;true&#39;)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (<a href="/spaces/file_sender/tickets/985">#985</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: download pause/resume now possible with browsers supporting<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; partial download (most notably Firefox, IE11, curl and wget) (<a href="/spaces/file_sender/tickets/1076">#1076</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New: support for SQLite (<a href="/spaces/file_sender/tickets/898">#898</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New language: Finnish (<a href="/spaces/file_sender/tickets/981">#981</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Change: logout.php is now called in the same way as all other pages,<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; practical for header/footer. Change your site_logouturl!(<a href="/spaces/file_sender/tickets/904">#904</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Change: Upgrade JQuery and JQueryUI to 1.10.2, Upgrade Smoothness<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; to 1.10.2. (<a href="/spaces/file_sender/tickets/819">#819</a>)<br />
&nbsp;</p>

<h2 id="changes_since_1.6">Changes since 1.6</h2>

<p>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Fix: upload problem with Safari 9.0.x (<a href="/spaces/file_sender/tickets/1217">#1217</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Change: new HEAnet and UNINETT logo (<a href="/spaces/file_sender/tickets/1218">#1218</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Security: escape PHP_SELF variable in admin page (<a href="/spaces/file_sender/tickets/1240">#1240</a>)</p>

<h2 id="changes_since_1.6-rc1">Changes since 1.6-rc1</h2>

<p><br />
&nbsp;&nbsp;&nbsp;&nbsp; - Languages: Add Finnish translation contributed by Tomi Salmi<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; of CSC/Funet (<a href="/spaces/file_sender/tickets/981">#981</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Debian packaging: Only define Apache &lt;Directory&gt; permissions<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; for the &lt;filesenderbase&gt;/www subtree (<a href="/spaces/file_sender/tickets/1089">#1089</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Supporting scripts: add shell script to check for missing or<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; unknown language tags (<a href="/spaces/file_sender/tickets/1101">#1101</a>)<br />
&nbsp;</p>

<h2 id="changes_since_1.6-beta1">Changes since 1.6-beta1</h2>

<p>&nbsp;&nbsp;&nbsp;&nbsp; - Download pause/resume now possible with browsers supporting<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; partial download (most notably Firefox, IE11, curl and wget)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (<a href="/spaces/file_sender/tickets/1076">#1076</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - &#39;terasender&#39; default disabled in config-dist.php (<a href="/spaces/file_sender/tickets/1077">#1077</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Added IE10+ and Safari 6+ to supported browsers in HELP text<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; for en, no and nl languages (<a href="/spaces/file_sender/tickets/1063">#1063</a>)</p>

<h2 id="fixes_since_1.6-beta1">Fixes since 1.6-beta1</h2>

<p>&nbsp;&nbsp;&nbsp;&nbsp; - Security: also escape single quotes for externally supplied<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; output (<a href="/spaces/file_sender/tickets/1079">#1079</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Security: encode MMredirectURL in Flash detection code (<a href="/spaces/file_sender/tickets/1078">#1078</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Security: strict type comparison in XSFR check (<a href="/spaces/file_sender/tickets/1080">#1080</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - &#39;friendly name&#39; extraction fixed (<a href="/spaces/file_sender/tickets/1068">#1068</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Various fixes and improvements in the partial download code (<a href="/spaces/file_sender/tickets/1076">#1076</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - chunked reading and buffering to prevent server side memory<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; exhaustion with large range requests<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - more robust range request detection to make actual pause/resume<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; possible</p>

<h2 id="major_changes_since_1.5">Major changes since 1.5</h2>
&nbsp;&nbsp;&nbsp;&nbsp; - Add TeraSender code (<a href="/spaces/file_sender/tickets/885">#885</a>, <a href="/spaces/file_sender/tickets/899">#899</a>, <a href="/spaces/file_sender/tickets/1064">#1064</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Allows for faster HTML5 uploads<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Upgrade note: new configuration options<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Default not enabled, enable in config.php<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New layout of My Files page (<a href="/spaces/file_sender/tickets/597">#597</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - add number of downloads<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - expandable per file details view<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - removed &#39;me&#39; substition<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Add optional personal message and subject to guest vouchers (<a href="/spaces/file_sender/tickets/637">#637</a>,<a href="/spaces/file_sender/tickets/963">#963</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Upgrade note: change in configuration mail template<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Recipient address autocomplete based on previous recipients (<a href="/spaces/file_sender/tickets/821">#821</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Upgrade note: new configuration options<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Add selector when multiple mail adresses are available (<a href="/spaces/file_sender/tickets/184">#184</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Modified patch from Thijs Kinkhorst
<h2 id="changes_since_1.5">Changes since 1.5</h2>
&nbsp;&nbsp;&nbsp;&nbsp; - Upgrade of JQuery and JQueryUI to 1.10.2 (<a href="/spaces/file_sender/tickets/819">#819</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Default Voucher Subject configurable (<a href="/spaces/file_sender/tickets/774">#774</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Patch contributed by Thijs Kinkhorst<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Add a customisable footer through the language definitions (<a href="/spaces/file_sender/tickets/871">#871</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Modified patch from Jean-Philippe Evrard, BELNET<br />
&nbsp;&nbsp;&nbsp;&nbsp; - logout.php and invalidvoucher.php removed and integrated in<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; the core index.php (<a href="/spaces/file_sender/tickets/904">#904</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - Upgrade note: needs change in config.php when upgrading,<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; logout page breaks if config.php isn&#39;t adapted<br />
&nbsp;&nbsp;&nbsp;&nbsp; - New download.php (<a href="/spaces/file_sender/tickets/858">#858</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - redo logic for mail sending and logging<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - added partial download (HTTP range) functionality (not used yet)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; - some cleanup<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Add option to suppress carbon copy of download confirmation mail<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; to downloader (<a href="/spaces/file_sender/tickets/985">#985</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Add sqlite init-script and &#39;how to&#39; (<a href="/spaces/file_sender/tickets/898">#898</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Patch contributed by Dick Visser<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Minor layout changes (<a href="/spaces/file_sender/tickets/965">#965</a>,<a href="/spaces/file_sender/tickets/966">#966</a>)

<h2 id="fixes_since_1.5">Fixes since 1.5</h2>
&nbsp;&nbsp;&nbsp;&nbsp; - Optimise PDO Query row count statements (<a href="/spaces/file_sender/tickets/888">#888</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Patch from Dick Visser<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Remove unused validVoucher() function<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Patch from Thijs Kinkhorst<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Hash fileuid for pending/validateupload entry (<a href="/spaces/file_sender/tickets/884">#884</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; Bug noticed by Dick Visser<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Replace $_REQUEST[&#39;PHPSESSID&#39;] with session_id() (<a href="/spaces/file_sender/tickets/897">#897</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Fix declarations for fileexpirydate and logdate in mysql init script (<a href="/spaces/file_sender/tickets/932">#932</a>)<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Fixed use of single quote in filename with Flash uploads (<a href="/spaces/file_sender/tickets/895">#895</a>)

<h2 id="known_issues">Known issues</h2>
&nbsp;Important known issues can be found at <a class="wiki_link" href="/wiki/show/file_sender/Known_issues" title="Known issues">Known issues</a>.&nbsp; See also <a href="https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373">https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373</a> for a current list of issues.</div>

<div>
<h2 id="support_and_feedback">Support and Feedback</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Support_and_Mailinglists" title="Support and Mailinglists">Support and Mailinglists</a> and <a class="wiki_link" href="/wiki/show/file_sender/Feature_requests" title="Feature requests">Feature requests</a>.</p>
</div>

