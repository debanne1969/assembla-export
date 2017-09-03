<p>This document describes the FileSender software life cycle.&nbsp; What labels do we use to describe the various states a release can be in, from birth (beta) to end-of-life (EOL).&nbsp; FileSender follows the well-known Debian lingo for describing the status of its releases.&nbsp;</p>

<h2 id="distribution_channels_and_current_release_status">Distribution channels and current release status</h2>

<p>For all distribution channels (Tarball, Debian and RPM packages) the following channels (repositories) are used:</p>

<table>
	<tbody>
		<tr>
			<td><b>Status label</b></td>
			<td><b>Description</b></td>
			<td>&nbsp;</td>
		</tr>
		<tr>
			<td>&nbsp;oldstable</td>
			<td>&nbsp;previous supported release (security fixes only)</td>
			<td>&nbsp;1.5</td>
		</tr>
		<tr>
			<td>&nbsp;stable</td>
			<td>&nbsp;recommended and supported release</td>
			<td>&nbsp;1.6.1</td>
		</tr>
		<tr>
			<td>&nbsp;testing</td>
			<td>&nbsp;next stable version</td>
			<td>&nbsp;1.6.1</td>
		</tr>
		<tr>
			<td>&nbsp;unstable</td>
			<td>beta version</td>
			<td>&nbsp;1.7-beta1</td>
		</tr>
		<tr>
			<td>&nbsp;experimental</td>
			<td>&nbsp;snapshot builds/experimental</td>
			<td>1.7-beta1</td>
		</tr>
	</tbody>
</table>

<h2 id="c2a0">&nbsp;</h2>

<h2 id="release_history">Release history</h2>

<table border="0">
	<tbody>
		<tr>
			<td><b>Version</b></td>
			<td><b>Status</b></td>
			<td>Phase change planned around</td>
		</tr>
		<tr>
			<td>1.5</td>
			<td>oldstable</td>
			<td>1.5 as of 6-01-2016</td>
		</tr>
		<tr>
			<td>1.6.1</td>
			<td>stable</td>
			<td>1.6.1 as of 6-01-2016</td>
		</tr>
		<tr>
			<td>1.6.1</td>
			<td>testing</td>
			<td>&nbsp;1.6.1 as of 30-12-2015</td>
		</tr>
		<tr>
			<td>1.7 (beta + rc)</td>
			<td>unstable</td>
			<td>&nbsp;1.7-beta1 as of 6-1-2016</td>
		</tr>
	</tbody>
</table>

<p>&nbsp;</p>

<h2 id="release_life_cycle">Release life cycle</h2>

<p>All FileSender releases go through the following phases during their life:</p>

<p style="padding-left: 30px;"><b>Unstable:</b> under development: nightly builds and beta builds</p>

<p style="padding-left: 30px;"><b>Testing:</b> candidate to become stable.&nbsp; Production quality and well tested, but needs to prove itself in the field.&nbsp; Support, bug and security fixes are provided.&nbsp;</p>

<p style="padding-left: 30px;"><b>Stable:</b> field tested boring-no-problems production release.&nbsp; Support, bug and security fixes are provided.<br />
<b>Oldstable:</b> the previous stable release.&nbsp; Security fixes only.</p>

<p>Each channel can be occupied by one release.&nbsp; When we release a FileSender version for use in production environments, it moves from <i><b>Unstable</b></i> to <b>Testing</b>.&nbsp; This bumps the release living in Testing to Stable and the one living in Stable to Oldstable.&nbsp; The current Oldstable release dies.&nbsp;</p>

<p>When a release in Testing has run problem-free for at least an 8 week period on at least 2 production sites that see daily real traffic, it <i><b>can</b></i> (but does not need to) be moved to <b>stable</b>.&nbsp; A release in &quot;stable&quot; must be what it says on the tin: stable.&nbsp; It should run unattended and feel fine about it.&nbsp; We maken an effort to have a solid release in both Testing and Stable at any given point in time.</p>

<p>&nbsp;</p>

<h2 id="7768656e20646f657320737570706f727420656e643f">When does support end?</h2>

<p>When a release moves out of &quot;Oldstable&quot; support is no longer provided and the release is labeled <b>EOL, End of Life</b>.&nbsp; New <i>revisions</i> of a &#39;major.minor&#39;&nbsp; will obsolete the previous &#39;major.minor&#39;, so for example &#39;1.0.1&#39; will obsolete &#39;1.0.0&#39;. The unstable/testing/stable/oldstable cycle is used for the major.minor releases. Minor revisions will be put in the distribution channel where the major.minor is.</p>

<h2 id="version_numbering">Version numbering</h2>

<p>FileSender version numbering follows the <b>major.minor.revision</b> method.&nbsp;</p>

<p style="padding-left: 30px;"><b>major:</b> incremented when major back-end changes occur that require a lot of attention when upgrading.&nbsp; Examples are significant changes in the API, database schema etc.;</p>

<p style="padding-left: 30px;"><b>minor: </b>when introducing changes too big to be labeled<b> revision</b> and too smalto use</p>

<p style="padding-left: 30px;"><b>revision</b>: small changes.&nbsp; This will typically be bug fixes,&nbsp; security fixes and UI polish.</p>

<h1 id="3c623ec2a03c2f623e"><b>&nbsp;</b></h1>

<h2 id="3c623e7072652d72656c6561736573203c62723e3c2f623e"><b>Pre-releases </b></h2>

<p><b>Beta releases:</b> for major releases we will typically release one or more beta versions.&nbsp; These are tested by the testing team and are assumed to work reasonably well.&nbsp; Beta releases need to be field tested for robustness, bugs and assumption verification.</p>

<p><b>Release candidates:</b> for both <b>major releases and minor releases</b> we will at least <b>1 Release Candidate</b> version.&nbsp;</p>

<p><b>Release: </b>when a Release Candidate has been running on least two FileSender sites without error for a period of at least 1 week under meaningful use, this release candidate is re-branded as a release.&nbsp; There are no code changes, no database changes and no config file changes between a release candidate and a release.</p>

<p>Pre-releases will be labeled with a<i> -[beta|rc][n]</i> suffix, for example <i>1.1-rc2</i> or <i>1.5-beta1</i></p>

<h2 id="3c623e736e617073686f742072656c65617365733c2f623e"><b>Snapshot releases</b></h2>

<p>Between releases there can and will be intermediate snapshot builds. Snapshot builds are regarded as pre-release builds of a to be released target version. The snapshot version will be added to the target version number with a hyphen. <i style="background-color: #ffff88;">If there is no target version yet we could add the snapshot version with a + sign to indicate a post-release snapshot?</i><br style="background-color: #ffff88;" />
<br />
Snapshot suffix: <i>-[builddate|svnrevision]</i> where <i>builddate = YYYYMMDDhhmm</i><br />
&nbsp;</p>

<p>Examples: <i>1.5-201202041550&nbsp; 1.5.1-<a href="https://www.assembla.com/code/file_sender/subversion/changesets/1488">r1488</a></i></p>

<h2 id="package_naming_and_versioning">Package naming and versioning</h2>

<h4 id="packaging_principles">Packaging principles</h4>

<p>Main version of a package should be the &quot;target&quot; version to be officially released. Both alpha/beta/rc&#39;s and snapshots are to be considered a pre-release of that target version. When publishing packages the pre-release/snapshot version should be regarded as &#39;lower&#39; than the final target release but &quot;higher&quot; than the previous target release.<br />
<br />
For RPM this is done using the Fedora recommendations by defining/using a Release tag.<br />
<br />
For Debian this is (for many reasons) a bit more complicated when using both pre-releases and snapshots for the same target version. The use of a <i>~label</i> in the <i>upstream_version</i> part appears to be the recommended way.</p>

<h4 id="tarballs_and_zipfiles">Tarballs and zipfiles</h4>

<p>tarballs and zipfiles will be named following the above mentioned versioning scheme with the name <i>filesender</i></p>

<h4 id="rpm_packages">RPM packages</h4>

<p><a href="http://fedoraproject.org/wiki/Packaging:NamingGuidelines#Pre-Release_packages%20"><span style="background-color: #ffff88;">http://fedoraproject.org/wiki/Packaging:NamingGuidelines#Pre-Release_packages</span><span style="background-color: #ffff88;">&nbsp;</span></a></p>

<p><a href="http://directory.fedoraproject.org/wiki/Release_Procedure"><span style="background-color: #ffff88;">http://directory.fedoraproject.org/wiki/Release_Procedure</span></a><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">In specfile Version=FS-version, Release=package-revision</span><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">[package-revison] = [n][.m][.fs-sub-version]</span><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">n=0 for pre-releases and dev builds</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">n=1 for releases</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">m=for pre-releases only: increasing number which will be incremented when switching from dev-build to pre-release or vice versa</span><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-0.1.<a href="https://www.assembla.com/code/file_sender/subversion/changesets/1488">r1488</a>&nbsp;&nbsp;&nbsp;&nbsp; nightly in 1.5 dev cycle</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-0.1.<a href="https://www.assembla.com/code/file_sender/subversion/changesets/1492">r1492</a>&nbsp;&nbsp;&nbsp;&nbsp; nightly</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-0.2.beta1&nbsp;&nbsp;&nbsp;&nbsp; beta1</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-0.3.<a href="https://www.assembla.com/code/file_sender/subversion/changesets/1495">r1495</a>&nbsp;&nbsp;&nbsp;&nbsp; nightly</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-0.3.<a href="https://www.assembla.com/code/file_sender/subversion/changesets/1497">r1497</a>&nbsp;&nbsp;&nbsp;&nbsp; nightly</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-0.4.rc1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; rc1</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5-1&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; final release</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5.1-0.1.<a href="https://www.assembla.com/code/file_sender/subversion/changesets/1500">r1500</a>&nbsp;&nbsp; new nightly in 1.5.1 dev cycle</span></p>

<h4 id="debian_packages">Debian packages</h4>

<p><a href="http://www.debian.org/doc/debian-policy/ch-controlfields.html#s-f-Version"><span style="background-color: #ffff88;">http://www.debian.org/doc/debian-policy/ch-controlfields.html#s-f-Version</span></a><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">[epoch:]upstream_version[-debian_revision] </span><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<a href="https://help.launchpad.net/Packaging/PPA/BuildingASourcePackage"><span style="background-color: #ffff88;">https://help.launchpad.net/Packaging/PPA/BuildingASourcePackage</span></a><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">pre-release tags can (must according to policy) be in upstream_version like 1.5~rc1 *but* that would conflict with snapshot/dev builds.</span><br style="background-color: #ffff88;" />
<br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5~beta1</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1-5~rc1</span><br style="background-color: #ffff88;" />
<span style="background-color: #ffff88;">1.5~201202042315</span></p>

