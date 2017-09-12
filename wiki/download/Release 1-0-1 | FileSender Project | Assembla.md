<h2 id="release_version_1.0.1">Release Version 1.0.1</h2>

<p>Release date: 18 May 2011</p>

<table border="0">
	<tbody>
		<tr>
			<td><strong>Distribution file</strong></td>
			<td><strong>MD5</strong></td>
			<td><strong>SHA1</strong></td>
		</tr>
		<tr>
			<td><a href="http://download.filesender.org/filesender-1.0.1.tar.gz">filesender-1.0.1.tar.gz</a></td>
			<td><span style="font-family: courier new,courier;">72218ad9b3d42c7803189fabb9b90b3a</span></td>
			<td>&nbsp;<span style="font-family: courier new,courier;">3116e47ef7bcbaa64944fb54fefb44422875eed9</span></td>
		</tr>
		<tr>
			<td><a href="http://download.filesender.org/filesender-1.0.1.zip">filesender-1.0.1.zip</a></td>
			<td><span style="font-family: courier new,courier;">16092a84be235f690ec58c40a003269d</span></td>
			<td>&nbsp;<span style="font-family: courier new,courier;">26fe9891c272df6d5ac1e3f7573dfffc9d8358c5</span></td>
		</tr>
	</tbody>
</table>

<p>Release 1.0.1 is also available in the <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Debian_Ubuntu" title="Installation - Debian Ubuntu">Debian</a> and <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_RPM" title="Installation - RPM">RPM</a> package repositories and the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.0.1/">Subversion repository</a>.</p>

<h2 id="installation">Installation</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Linux_Source" title="Installation - Linux Source">Installation - Linux Source</a></p>

<h2 id="upgrade_notes">Upgrade Notes</h2>

<p>When upgrading from a previous beta version (including 1.0 RELEASE) please read the <a class="wiki_link" href="/wiki/show/file_sender/Upgrade_notes" title="Upgrade notes">Upgrade notes</a> <strong>before</strong> upgrading.</p>

<h2 id="changes_since_1.0_release">Changes since 1.0 RELEASE</h2>

<ul>
	<li>Experimental feature
	<ul>
		<li>&nbsp;Mail bounce handling (for details see<br />
		&nbsp; <a class="wiki_link" href="/wiki/show/file_sender/Mail_Bounce_Handling" title="Mail_Bounce_Handling">http://www.assembla.com/wiki/show/file_sender/Mail_Bounce_Handling</a></li>
	</ul>
	</li>
</ul>

<ul>
	<li>Packaging
	<ul>
		<li>Added filesender-php.ini with recommended PHP settings</li>
	</ul>
	</li>
</ul>

<ul>
	<li>Fixes and changes
	<ul>
		<li><a href="/spaces/file_sender/tickets/271">#271</a> compatibility fix for SimpleSAMLphp 1.7+</li>
		<li><a href="/spaces/file_sender/tickets/379">#379</a> Log IPv6 address of connecting client. When upgrading from<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; previous versions you should fix the relevant column size in the<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; database with:<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; #sudo -u postgres psql filesender<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ALTER TABLE files ALTER fileip6address TYPE character varying(45);<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; \q</li>
		<li><a href="/spaces/file_sender/tickets/380">#380</a>, <a href="/spaces/file_sender/tickets/389">#389</a>, <a href="/spaces/file_sender/tickets/390">#390</a>&nbsp; fix the max_gears_upload_size check.</li>
		<li><a href="/spaces/file_sender/tickets/381">#381</a> allow multiple email addresses to be separated by both a<br />
		&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; comma and a semi-colon</li>
		<li><a href="/spaces/file_sender/tickets/383">#383</a> trim whitespace from email-addresses</li>
		<li><a href="/spaces/file_sender/tickets/394">#394</a> &quot;File too large, use Gears&quot; warnings fixups</li>
		<li><a href="/spaces/file_sender/tickets/396">#396</a> Confirmation when cancelling Flash upload</li>
		<li><a href="/spaces/file_sender/tickets/397">#397</a> Wrapping of Subject field in My Files table</li>
	</ul>
	</li>
</ul>

<h2 id="known_issues">Known issues</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Known_issues_in_v1-0" title="Known issues in v1-0">Known issues in v1-0</a>.</p>

<h2 id="support_and_feedback">Support and Feedback</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Support_and_Mailinglists" title="Support and Mailinglists">Support and Mailinglists</a> and <a class="wiki_link" href="/wiki/show/file_sender/Feature_requests" title="Feature requests">Feature requests</a>.</p>

