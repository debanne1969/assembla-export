<h2 id="release_version_1.7-beta1">Release Version 1.7-beta1</h2>

<p>Release date:&nbsp; 6 January 2016</p>

<p>Release 1.7-beta1 is the 1.6.(x) codebase with an end-to-end encryption module added.</p>

<table border="0">
	<tbody>
		<tr>
			<td><b>Distribution file</b></td>
			<td><b>MD5</b></td>
			<td><b>SHA1</b></td>
		</tr>
		<tr>
			<td><a href="https://downloads.filesender.org/filesender-1.7-beta1.tar.gz">filesender-1.7-beta1.tar.gz</a></td>
			<td><span style="font-family: courier new,courier;">18536c225a37aab6d02bf0e555ad85d3</span></td>
			<td>1236780da9e708b444f85e3ad66253a2dd3ab1f9</td>
		</tr>
		<tr>
			<td><a href="https://downloads.filesender.org/filesender-1.7-beta1.zip">filesender-1.7-beta1.zip</a></td>
			<td><span style="font-family: courier new,courier;">a9bd69cf3008ecd44a2325c620d06b2e</span></td>
			<td>a1367751ff27c0df5da82d34f52163796ca3c3c8</td>
		</tr>
	</tbody>
</table>

<p>Release 1.7-beta1 is also available in the <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_Debian_Ubuntu" title="Installation_-_Debian_Ubuntu">Debian</a> and <a class="wiki_link" href="/wiki/show/file_sender/Installation_-_RPM" title="Installation_-_RPM">RPM</a> package repositories and the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.7-beta1/">Subversion repository</a>. Currently Release 1.7-beta1 is distributed from the <b>unstable</b> and <b>experimental</b> repositories.</p>

<h2 id="installation">Installation</h2>

<p>Documentation for this release is the same as for 1.6.1 and is available at <a class="wiki_link" href="/wiki/show/file_sender/Documentation_v1-6" title="Documentation v1-6">Documentation v1-6</a>. For now the crypto-module is documented below under the Upgrade Notes.</p>

<p>&nbsp;</p>

<div>
<h2 id="new_feature_since_1.6(.x)">New feature since 1.6(.x)</h2>
&nbsp;&nbsp;&nbsp;&nbsp; - New: experimental crypto module for end-to-end encryption

<h2 id="upgrade_notes">Upgrade Notes</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Upgrade_notes" title="Upgrade notes">Upgrade notes</a> for important upgrade and installation notes when upgrading from previous versions (most notably 1.5 and earlier). Additionally the following items are important when you want to use the encryption module.&nbsp;</p>

<p>&nbsp;</p>
&nbsp;&nbsp;&nbsp; - you MUST (also when using the Debian/RPM packages) <b>manually</b> add one additional column to the<br />
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; files table in the filesender database:</div>

<div>&nbsp;
<pre>
&nbsp;&nbsp;&nbsp; $ psql filesender&nbsp; 
&nbsp;&nbsp;&nbsp; alter table files add column fileencryption int ;</pre>
</div>

<div><br />
&nbsp;&nbsp;&nbsp;&nbsp; - New crypto_* configurables in config.php</div>

<div>&nbsp;</div>

<div>
<pre>
&nbsp;&nbsp;&nbsp; // crypto settings
&nbsp;&nbsp;&nbsp; $config[&quot;crypto_enabled&quot;] = false; // Set to true to enable end2end encryption module
&nbsp;&nbsp;&nbsp; $config[&quot;crypto_default_enabled&quot;] = false; // Set to true to encrypt files by default
&nbsp;&nbsp;&nbsp; $config[&#39;crypto_max_filesize&#39;] = 250*1024*1024 ; // Max filesize for encryption, 0 will allow any size.
</pre>
&nbsp;&nbsp;&nbsp;&nbsp; - Changes in the default mail templates<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Changes in the default en_AU and nl_NL language files<br />
&nbsp;&nbsp;&nbsp;&nbsp; - Default not enabled, enable in config.php
<h2 id="known_issues">Known issues</h2>
&nbsp;Important known issues can be found at <a class="wiki_link" href="/wiki/show/file_sender/Known_issues" title="Known issues">Known issues</a>.&nbsp; See also <a href="https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373">https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373</a> for a current list of 1.6.x issues and <a href="https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u470673">https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u470673</a> for specific crypto module issues.</div>

<div>
<h2 id="support_and_feedback">Support and Feedback</h2>

<p>See <a class="wiki_link" href="/wiki/show/file_sender/Support_and_Mailinglists" title="Support and Mailinglists">Support and Mailinglists</a> and <a class="wiki_link" href="/wiki/show/file_sender/Feature_requests" title="Feature requests">Feature requests</a>.</p>
</div>

