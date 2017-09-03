<p>This page outlines the current release planning for FileSender.&nbsp; When reading the release planning, keep in mind we will usually release multiple beta versions to get to the stability and maturity required for a stable release.&nbsp; Do check the SVN playgrounds to get an idea what we&#39;re working on besides the releases.</p>

<h2 id="66696c6573656e64657220322e302028636f6465206e616d653a206d756c746966696c65293c62723e">FileSender 2.0 (code name: MultiFile)</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>Release</b></td>
			<td><b>Planned date</b></td>
			<td><b>Release date</b></td>
			<td><b>Release will include/fix</b></td>
		</tr>
		<tr>
			<td>2.0</td>
			<td>2015</td>
			<td>&nbsp;</td>
			<td>transferring multiple files in one transaction (select, upload, myfiles, download).&nbsp; Will include drag &amp; drop.</td>
		</tr>
		<tr>
			<td>2.0-beta2</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>2.0-beta1</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>2.0-alpha1</td>
			<td>&nbsp;Q1 2015</td>
			<td>status 1 feb 2015: &nbsp;code available, security audit done, documentation not entirely sufficient</td>
			<td>multi-file, email receipt control, REST API, basic code security audit</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<h2 id="66696c6573656e64657220312e372028636f6465206e616d653a2063727970746f293c62723e">FileSender 1.7 (code name: Crypto)</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>Release</b></td>
			<td><b>Planned date</b></td>
			<td><b>Release date</b></td>
			<td><b>Release will include/fix</b></td>
		</tr>
		<tr>
			<td>&nbsp;1.7-beta1</td>
			<td>&nbsp;</td>
			<td>&nbsp;6 January 2016</td>
			<td>&nbsp;End-to-end encryption module</td>
		</tr>
	</tbody>
</table>

<h2 id="66696c6573656e64657220312e362028636f6465206e616d653a207465726173656e646572293c62723e">FileSender 1.6 (code name: TeraSender)</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>Release</b></td>
			<td><b>Planned date</b></td>
			<td><b>Release date</b></td>
			<td><b>Release will include/fix</b></td>
		</tr>
		<tr>
			<td>&nbsp;1.6.1</td>
			<td>&nbsp;</td>
			<td>&nbsp;30 December 2015</td>
			<td>&nbsp;bugfix release</td>
		</tr>
		<tr>
			<td>1.6</td>
			<td>&nbsp;</td>
			<td>&nbsp;26 July 2014</td>
			<td>experimental feature: incorporate results of TeraByte Challenge, improved upload code to enable upload speeds of at least 850mbit/s</td>
		</tr>
		<tr>
			<td>1.6-rc1</td>
			<td>&nbsp;</td>
			<td>&nbsp;4 April 2014</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>1.6-beta1</td>
			<td>&nbsp;December 2013</td>
			<td>&nbsp;31 December 2013</td>
			<td>&nbsp;</td>
		</tr>
	</tbody>
</table>

<h2 id="filesender_1.5">FileSender 1.5</h2>

<p>Check <a href="/spaces/file_sender/tickets">the 1.5 bug tickets</a> to get a good idea of where we are with 1.5 and what remains to be done.</p>

<table border="0">
	<tbody>
		<tr>
			<td><b>Release</b></td>
			<td><b>Planned date</b></td>
			<td><b>Release date</b></td>
			<td><b>Release will include/fix</b></td>
		</tr>
		<tr>
			<td>1.5</td>
			<td>&nbsp;<strike>November 2012</strike> January 2013</td>
			<td>&nbsp;3 March 2013</td>
			<td>Documentation, minor bug fixes, language file updates</td>
		</tr>
		<tr>
			<td>1.5-rc1</td>
			<td>&nbsp;<strike>15 May 2012 15 June 2012</strike> August/September 2012</td>
			<td>22 October 2012</td>
			<td>Minor bug fixes, language file updates <strike>and documentation</strike></td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;<b>codefreeze</b></td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;1.5-beta4</td>
			<td>july 2012</td>
			<td>&nbsp;25 July 2012</td>
			<td>security and other bug fixes, no new or changed features</td>
		</tr>
		<tr>
			<td>&nbsp;<b>security audit</b></td>
			<td>execute: 9-11 May 2012, report: around 21 May 2012</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>1.5-beta3</td>
			<td>15 May 2012</td>
			<td>15 May 2012</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>1.5-beta2</td>
			<td>&nbsp;<strike>23 March 2012</strike> 25 April 2012</td>
			<td>25 April 2012</td>
			<td>
			<ul>
				<li>Last fixes for robuster upload pause/resume (<a href="/spaces/file_sender/tickets/618">#618</a>)</li>
				<li>Improved multi-tab upload session handling (<a href="/spaces/file_sender/tickets/641">#641</a>, <a href="/spaces/file_sender/tickets/629">#629</a>, <a href="/spaces/file_sender/tickets/654">#654</a>)</li>
				<li>consolidation of all locale related content in 1 single language file</li>
				<li>improved upgradability by clearly separating distribution-provided and local override files ( in particular language and config)</li>
			</ul>
			</td>
		</tr>
		<tr>
			<td>1.5-beta1</td>
			<td>
			<p><span style="text-decoration: line-through;">31 October 2011</span></p>

			<p><span style="text-decoration: line-through;">9 December 2011</span></p>

			<p><span style="text-decoration: line-through;">January 2012</span></p>

			<p>17 February 2012</p>
			</td>
			<td>13 February 2012</td>
			<td>
			<p>HTML5 (no-gears) unlimited size file upload</p>

			<p>Graceful fallback to Flash for upload with older browsers</p>

			<p>HTML+JavaScript only UI when using HTML5 for upload</p>

			<p>Internationalisation: multi-language UI support</p>

			<p>Database abstraction with PDO, Postgresql and MySQL tested</p>
			</td>
		</tr>
	</tbody>
</table>

<h2 id="filesender_1.1.x">FileSender 1.1.x</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>Release</b></td>
			<td><b>Planned date</b></td>
			<td><b>Release date</b></td>
			<td><b>Release will include/fix</b></td>
		</tr>
		<tr>
			<td>1.1.1</td>
			<td>&nbsp;May 2012</td>
			<td>&nbsp;31 May 2012</td>
			<td>
			<ul>
				<li>Support for changed HTML5 semantics in Firefox 13+ (<a href="/spaces/file_sender/tickets/730">#730</a>).</li>
				<li>&nbsp;Fixed potential privilege elevation issue which under certain conditions could give a normal user access to the admin interface (<a href="/spaces/file_sender/tickets/750">#750</a>).</li>
				<li>Change in database column type for fileto/logto (<a href="/spaces/file_sender/tickets/739">#739</a>).</li>
				<li>Other minor bugfixes</li>
			</ul>
			</td>
			<td>&nbsp;</td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>1.1</td>
			<td>31 October 2011</td>
			<td>&nbsp;5 November 2011</td>
			<td>
			<p>Replaced Gears upload module with HTML5 FileAPI upload module</p>
			</td>
		</tr>
	</tbody>
</table>

<h2 id="filesender_1.0.x">FileSender 1.0.x</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>Release</b></td>
			<td><b>Planned date</b></td>
			<td><b>Release date</b></td>
			<td><b>Release will include/fix</b></td>
		</tr>
	</tbody>
	<tbody>
		<tr>
			<td>1.0.1</td>
			<td>May 2011</td>
			<td>&nbsp;18 May 2011</td>
			<td>
			<p>&nbsp;</p>

			<p>Bug <a href="/spaces/file_sender/tickets/271">#271</a>: Compatibility with SimpleSAMLphp 1.7+</p>

			<p>Bug <a href="/spaces/file_sender/tickets/379">#379</a>: IPv6 addresses are not stored in the files table</p>

			<p>Bugs <a href="/spaces/file_sender/tickets/380">#380</a>, <a href="/spaces/file_sender/tickets/389">#389</a>, <a href="/spaces/file_sender/tickets/390">#390</a>: max_gears_upload_size check not implemented and related filesize limit checks</p>

			<p>Bug <a href="/spaces/file_sender/tickets/381">#381</a>: Multiple emails - allow , and ;</p>

			<p>Bug <a href="/spaces/file_sender/tickets/383">#383</a>: Surrounding whitespace with email-adresses not trimmed</p>
			Ticket <a href="/spaces/file_sender/tickets/384">#384</a>: Experimental feature: possible solutions for <i><a href="/spaces/file_sender/tickets/63">#63</a> devise a solution for SPF records</i>, documented in <a href="/wiki/show/file_sender/Mail_Bounce_Handling">http://www.assembla.com/wiki/show/file_sender/Mail_Bounce_Handling</a>

			<p>&nbsp;</p>

			<p>Bug <a href="/spaces/file_sender/tickets/394">#394</a>: &quot;File too large, use Gears&quot; warnings fixups</p>

			<p>Bug <a href="/spaces/file_sender/tickets/396">#396</a> Confirmation when cancelling Flash upload</p>

			<p>Bug <a href="/spaces/file_sender/tickets/397">#397</a> Wrapping of Subject field in My Files table<br />
			&nbsp;</p>
			</td>
		</tr>
		<tr>
			<td>1.0</td>
			<td>31 January 2011</td>
			<td>31 January 2011</td>
			<td>See <a href="/wiki/show/file_sender/Release_Schedule_until_v1-0">Release Schedule until v1-0</a></td>
		</tr>
	</tbody>
</table>

