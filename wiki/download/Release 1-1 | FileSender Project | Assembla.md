<h2 id="release_version_1.1">Release Version 1.1</h2>

<p>Release date: 5 November 2011</p>

<table border="0">
	<tbody>
		<tr>
			<td><strong>Distribution file</strong></td>
			<td><strong>MD5</strong></td>
			<td><strong>SHA1</strong></td>
		</tr>
		<tr>
			<td><a href="http://download.filesender.org/filesender-1.1.tar.gz">filesender-1.1.tar.gz</a></td>
			<td><span style="font-family: courier new,courier;">eb53b92070cb8039e535a71d3d53a5d2</span></td>
			<td>&nbsp;<span style="font-family: courier new,courier;">5278babd40a2b4e0f5392dab92aa5fd1f9767c78</span></td>
		</tr>
		<tr>
			<td><a href="http://download.filesender.org/filesender-1.1.zip">filesender-1.1.zip</a></td>
			<td><span style="font-family: courier new,courier;">9d0133174561edeba72625b33b9b177f</span></td>
			<td>&nbsp;<span style="font-family: courier new,courier;">5adcfc9b647041c6af17515a5c99da9ff2be4aa2</span></td>
		</tr>
	</tbody>
</table>

<p>Release 1.1 is also available in the <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Debian_Ubuntu" title="Installation - Debian Ubuntu">Debian</a> and <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_RPM" title="Installation - RPM">RPM</a> package repositories and the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.1/">Subversion repository</a>. Currently Release 1.1 is distributed from the <strong>testing</strong> repositories. Release 1.1 switched to HTML5 for uploading large files, if you need still need the previous version using the deprecated Gears plugin please use <a class="wiki_link" href="/wiki/show/file_sender/Release_1-0-1" title="Release 1-0-1">Release 1-0-1</a>.</p>

<h2 id="installation">Installation</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source" title="Installation - Linux Source">Installation - Linux Source</a></p>

<h2 id="upgrade_notes">Upgrade Notes</h2>

<p>When upgrading from a previous beta version (including 1.0(.x) RELEASE) please read the <a class="wiki_link" href="/wiki/show/file_sender/Upgrade_notes" title="Upgrade notes">Upgrade notes</a> <strong>before</strong> upgrading.</p>

<h2 id="changes_since_1.0.1_release">Changes since 1.0.1 RELEASE</h2>

<ul>
	<li>&nbsp;&nbsp;&nbsp; Major change since 1.0.1
	<ul>
		<li>Dropped Gears dependency, upload of large (&gt;2G) files now requires a browser that supports the HTML5 FileAPI, other browsers are limited to 2G uploads using the Flash upload mechanism. This change also obsoletes the following Gears-related issues in 1.0:<br />
		&nbsp;&nbsp; &nbsp;&nbsp; <a href="/spaces/file_sender/tickets/176">#176</a> &gt;2GB upload on MacOS hangs at ~2GB (Gears enabled)<br />
		&nbsp;&nbsp; &nbsp;&nbsp; <a href="/spaces/file_sender/tickets/290">#290</a> File select fails in Linux/Gears for files of 2G or more.<br />
		&nbsp;&nbsp; &nbsp;&nbsp; <a href="/spaces/file_sender/tickets/358">#358</a> Filename accents not displayed in GUI when using Gears</li>
	</ul>
	</li>
</ul>

<p style="padding-left: 90px;">This means that FileSender 1.1 also allows large uploads from the Mac OSX and Linux platforms, provided a supported HTML5 browser is used.</p>

<ul>
	<li>
	<ul>
		<li>Note that only user visible references to Gears have been changed. In the code and config.php references to &#39;gears&#39; are still used. No changes are required in config.php except for the URL pointing to more information on HTML5:<br />
		<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; $config[&#39;gearsURL&#39;] = &#39;http://html5test.com/&#39;;</li>
	</ul>
	</li>
</ul>

<ul>
	<li>Minor fixes and changes
	<ul>
		<li><a href="https://www.assembla.com/code/file_sender/subversion/changesets/993">revision:993</a> filesender_db.sql: make fileauthuseruid character varying(500)<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; When upgrading from previous versions you should fix the relevant<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; column size in the database with:<br />
		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; #sudo -u postgres psql filesender<br />
		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ALTER TABLE files ALTER fileauthuseruid TYPE character varying(500);<br />
		&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; \q</li>
		<li><a href="/spaces/file_sender/tickets/563">#563</a> Compare of UID attribute with admin uid broken when attribute is not in an array</li>
		<li><a href="/spaces/file_sender/tickets/569">#569</a> Case-sensitive references to Files in cron.php</li>
		<li><a href="/spaces/file_sender/tickets/582">#582</a> Inconsistent file size limit warnings</li>
		<li><a href="/spaces/file_sender/tickets/583">#583</a> Email addresses rejected at maximum for uploads &amp; voucher issue</li>
	</ul>
	</li>
</ul>

<ul>
	<li>Packaging
	<ul>
		<li>The Debian package has been adapted to use the default baseurl of the simplesamlphp 1.7+ debian packages which changed from &#39;simplesaml&#39; to &#39;simplesamlphp&#39; to adhere to standard Debian policy.</li>
	</ul>
	</li>
</ul>

<h2 id="known_issues">Known issues</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Known_issues_in_v1-1" title="Known issues in v1-1">Known issues in v1-1</a>.</p>

<h2 id="support_and_feedback">Support and Feedback</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Support_and_Mailinglists" title="Support and Mailinglists">Support and Mailinglists</a> and <a class="wiki_link" href="/wiki/show/file_sender/Feature_requests" title="Feature requests">Feature requests</a>.</p>

