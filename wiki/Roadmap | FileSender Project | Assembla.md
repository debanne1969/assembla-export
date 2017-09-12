<p>This page outlines the FileSender release roadmap.&nbsp;</p>

<ul>
	<li><span style="line-height: 20px;">New features are typically prototyped in a playground branche.&nbsp; We strive to have fully functional prototypes and development snapshots, the proof of the pudding is in the eating.&nbsp;&nbsp;</span></li>
	<li><span style="line-height: 20px;">Code security audits are conducted for each production release. &nbsp;Depending on the level of field testing desired code security audits may be done for alpha and beta releases as well.</span></li>
	<li><span style="line-height: 20px;">The development workflow once there is a baseline version is: playground -&gt; QA -&gt; integrate in trunk -&gt; QA/develop automatic tests -&gt; decide what to include in new release -&gt;release branche -&gt; QA -&gt; release</span></li>
</ul>

<h2 id="future_roadmap">Future roadmap</h2>

<div>All items listed here are in planning stage. &nbsp;If you wish to influence development planning to speed up certain features please consider making an earmarked contribution and contact jan.meijer@uninett.no or guido.aben@aarnet.edu.au</div>

<div>
<ul>
	<li>Standard usage statistics module. &nbsp;Prototype was built in 2012 and in use by RNP and UNINETT. &nbsp; No current activity</li>
	<li>Port encryption feature from 1.6 to version 2.0. &nbsp;</li>
	<li>Integration with external cryptographic timestamper</li>
	<li>Stronger download authentication</li>
	<li>UI review by user interaction design expert + implementation of recommendations: make the UI look _really good_</li>
	<li>Universal Access review + implementation recommendations: ensure FileSender can be used by anyone</li>
	<li>Better strategies for populating recipients (addressbook integration?)</li>
</ul>
</div>

<h2 id="current_roadmap">Current roadmap</h2>

<h3 id="filesender_version_2.0_(in_progress)">FileSender version 2.0 (in progress)</h3>

<div><b>Status per 16 February 2015:</b>&nbsp;based on the prototype built in the 2nd half 2013, production code work started summer 2014. &nbsp;A very usable 2.0-alpha code is now available for testing and actively being tested by both RENATER and UNINETT. &nbsp;Installation documentation is available. &nbsp;Configuration documentation is rudimentary. &nbsp;The 1st security audit has been performed, no structural issues found. &nbsp;Those issues found have been addressed. &nbsp;A 2nd security review is on its way. &nbsp;RENATER expects to make version 2.0 available to its customers around April 2015. &nbsp;The project still has a way to go before we can release a beta, documenting and testing will take its time.</div>

<div><b>Features:</b></div>

<div>
<ul>
	<li>full multi-file support: upload, download, MyFiles, email receipts and automatic transaction deletion</li>
	<li>drag &amp; drop support</li>
	<li>generalised user option mechanism, option availability is configurable server side</li>
	<li>user has fine-grained control over email receipts sent&nbsp;</li>
	<li>smaller privacy footprint</li>
	<li>new database design</li>
	<li>systematic audit trail logging</li>
	<li>audit trail available for user</li>
	<li>UI templating mechanism</li>
	<li>REST API</li>
	<li>and more</li>
</ul>
</div>

<h3 id="client-side_encryption_(in_progress)">Client-side encryption (in progress)</h3>

<div><b>Status per 7 January 2016: </b>this is released in release 1.7-beta1. &nbsp;There is one main known issue: because of the way decryption can be implemented using current browser technology, downloads of encrypted files larger than say 250 MB may lead to browser crashes.</div>

<div>&nbsp;</div>

<div><b>Features:</b></div>

<div>
<ul>
	<li>100% browser-based client-side encryption and decryption of files</li>
	<li>does _not_ handle key management (!)</li>
	<li>cryptosystem security audit executed</li>
	<li>code runs production @ SURFnet</li>
</ul>
</div>

<h2 id="completed_roadmap">Completed roadmap</h2>

<h3 id="3c623e3c753e66696c6573656e6465722076657273696f6e20312e362c2072656c6561736564203236206a756c7920323031343c2f753e3c2f623e"><b><u>FileSender version 1.6, released 26 July 2014</u></b></h3>

<div>
<ul>
	<li>High-speed upload module &#39;terasender&#39;</li>
	<li>auto-complete email addresses in To: field based on previous recipients for a particular user</li>
	<li>refactored MyFiles, file download dates&nbsp;provide audit trail when download Cc:s switched off</li>
	<li>support for configurable footer via language file</li>
	<li>support for optional Subject and Message in guest use voucher</li>
	<li>support for multiple From: addresses from authentication source</li>
	<li>ability to prevent file receipients receiving an email for each download (config option&nbsp;<i>download_confirmation_to_downloader</i>&#39;)</li>
	<li>Support for SQLite database</li>
</ul>
</div>

<h3 id="3c623e3c753e66696c6573656e6465722076657273696f6e20312e352c2072656c656173656420332e332e323031333c2f753ec2a03c2f623e"><b><u>FileSender version 1.5, released 3.3.2013</u>&nbsp;</b></h3>

<ul>
	<li>Improved backend</li>
	<li>Native HTML5 and JavaScript UI to replace Flash UI</li>
	<li>Fallback to flash upload component to ensure progress bar for non-HTML5 browsers</li>
	<li>Multi-language support</li>
	<li>Database abstraction layer with support for MySQL and PostgreSQL</li>
	<li>Robuster upload process</li>
	<li>Improved logging</li>
</ul>

<div>&nbsp;</div>

<h3 id="3c753e66696c6573656e64657220312e312c2072656c65617365642035206e6f76656d62657220323031313c2f753e"><u>FileSender 1.1, released 5 November 2011</u></h3>

<div>
<ul>
	<li>Replaced Google Gears with HTML5 FileAPI for uploads &gt; 2 GB</li>
	<li>Removed Google Gears dependency</li>
</ul>

<h3 id="3c753e66696c6573656e64657220312e302c2072656c6561736564203331206a616e756172792032303131c2a03c2f753e"><u>FileSender 1.0, released 31 January 2011&nbsp;</u></h3>
</div>

<div>
<ul>
	<li>initial production release</li>
	<li>Flash based UI</li>
	<li>Flash for uploads up to 2 GB</li>
	<li>Google Gears browser plugin for uploads &gt; 2 GB</li>
	<li>using SimpleSAMLphp to integrate with various authentication mechanisms (SAML2, RADIUS, LDAP, etc.)</li>
	<li>guest voucher mechanism to allow guest users to upload files</li>
	<li>cancel/resume uploads (for Gears uploads)</li>
	<li><span style="line-height: 20px;">download files multiple times, from link with built-in password in auto-generated email, or directly from interface by authenticated user&nbsp;</span></li>
	<li><span style="line-height: 20px;">automatic deletion of shared files and issued vouchers after X amount of time, or manual deletion by authenticated user any time prior to expiry</span></li>
	<li><span style="line-height: 20px;">email notification each time a file is uploaded, downloaded or manually deleted, or a voucher is issued or manually deleted</span></li>
	<li><span style="line-height: 20px;">MyFiles to show current shared files and unused guest vouchers</span></li>
	<li><span style="line-height: 20px;">user can resend download link emails to file recipients without re-uploading the file</span></li>
	<li><span style="line-height: 20px;">add additional recipients to already uploaded files</span></li>
	<li><span style="line-height: 20px;">UTF8 support, supports all international character sets</span></li>
</ul>

<div>&nbsp;</div>
</div>

<div>&nbsp;</div>

