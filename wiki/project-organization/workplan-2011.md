<h1 id="3c7370616e207374796c653d226261636b67726f756e642d636f6c6f723a20236666666666663b223e686f7720746f2072656164207468697320776f726b706c616e3c2f7370616e3e"><span style="background-color: #ffffff;">How to read this workplan</span></h1>

<p>FileSender is an agile project.&nbsp; This means our workplan is by no means written in stone but is adapted as circumstances warrant and opportunities allow.&nbsp; There is a very good idea on where we want to get but the road there is not always clear and without bumps.&nbsp; This affects release planning and that is reflected in work plan changes.</p>

<p>&nbsp;</p>

<h1 id="introduction">Introduction</h1>

<p>Removing the Google Gears dependency for file uploads larger then 2GB has highest priority after finalising the FileSender 1.0 release.&nbsp; In addition we want to put FileSender on the path to full removal of the Flash dependency.&nbsp; The way to go is the HTML5 FileAPI for supporting large file uploads and move towards a native HTML UI without Flash.&nbsp; This might need a phased approach.</p>

<p>In addition the &quot;why not use a web application framework&quot; question came up several times in 2010.&nbsp; This year we want to investigate whether it is worthwhile to move from &quot;raw&quot; PHP to a web application framework like for example Lift or Django.&nbsp; Having completed FileSender 1.0 offers us a good opportunity to consider such a move.</p>

<p>The work plan is divided in 4 rough chunks:</p>

<ul>
	<li>finish Filesender 1.0 release</li>
	<li>make decision on technology platform for next 2 years</li>
	<li>develop and release FileSender version without Gears but with &gt;2GB file upload support, feature-parity with FileSender 1.0</li>
	<li>develop other features according to priority</li>
</ul>

<p>&nbsp;</p>

<h1 id="3c7374726f6e673e726f7567682072656c6561736520706c616e6e696e673c2f7374726f6e673e"><strong>Rough release planning</strong></h1>

<p>With each release a certain amount of quality assessment, testing, documenting is required.&nbsp; We also know that when releasing a beta version for field testing, it starts a cycle of beta_release-deploy-test-feedback-code-new_beta_release that takes at least 6 weeks to complete.&nbsp; Taking these two boundary conditions into account it means we aim for 2 proper releases in 2011, and are happy if we can have smaller incrementals of good quality.</p>

<ul>
	<li>before EU summer holiday 2011: FileSender 1.5 release with HTML5 frontend</li>
	<li>November: Next FileSender release</li>
	<li>interim releases as appropriate</li>
</ul>

<p>&nbsp;</p>

<h1 id="project_team">Project team</h1>

<p>The core development team consists of:</p>

<ul>
	<li>Chris Richter: support for 1.0 release, lead developer front end, 1.5 back end, developer</li>
	<li>Maarten Koopmans: lead architect post-1.5 development, developer</li>
	<li>Xander Jansen: chief release management, testing</li>
	<li>Wendy Mason: chief documentation, testing</li>
	<li>Guido Aben: vice-project lead</li>
	<li>Jan Meijer: project lead</li>
</ul>

<p>&nbsp;</p>

<h2 id="consortium_representatives">Consortium representatives</h2>

<p>FileSender development is funded by a consortium of NRENs.&nbsp; Funding primarily pays to hire our two developers: Chris Richter and Maarten Koopmans.&nbsp; Consortium funding members and their representatives for 2012 are:</p>

<ul>
	<li>AARNet, Guido Aben</li>
	<li>Belnet, Mario Vandaele</li>
	<li>HEANet, Brian Boyle</li>
	<li>SURFnet, Rogier Spoor</li>
	<li>UNINETT, Jan Meijer</li>
</ul>

<p>&nbsp;</p>

<h1 id="work_break_down">Work break down</h1>

<h2 id="3c7374726f6e673e312e2066696e616c69736520312e302072656c6561736520283c656d3e31206a616e75617279202d203331206a616e756172793c2f656d3e293a3c2f7374726f6e673e"><strong>1. Finalise 1.0 release (<em>1 January - 31 January</em>):</strong></h2>

<ul>
	<li>complete documentation, clean up existing documentation</li>
	<li>re-order config.php</li>
	<li>polish packages</li>
	<li>QA packages</li>
</ul>

<p>&nbsp;</p>

<h2 id="3c656d3e322e20737570706f727420312e302072656c6561736520756e74696c20312e30206265636f6d657320756e737570706f7274656420283331206a616e75617279202d206d61782e20333120646563656d6265722032303131293c2f656d3e"><em>2. Support 1.0 release until 1.0 becomes unsupported (31 January - max. 31 December 2011)</em></h2>

<ul>
	<li>provide security fixes as needed</li>
	<li>provide small bug fixes as needed</li>
</ul>

<p>&nbsp;</p>

<h2 id="3c7374726f6e673e332e207072657061726174696f6e20706861736520666f72206e6578742072656c6561736520646576656c6f706d656e742028203c656d3e31206a616e75617279202d203331206d617263683c2f656d3e293c2f7374726f6e673e"><strong>3. Preparation phase for next release development ( <em>1 January - 31 March</em>)</strong></h2>

<ul>
	<li>Assess desirability of using an integrated web application framework</li>
	<li>Prototype uploads with HTML5 FileAPI in web application framework</li>
	<li>Prototype uploads with HTML5 FileAPI against current backend</li>
	<li>Decide path to follow: evolution of current backend, or replace current backend with integrated web application framework (e.g. Lift)</li>
</ul>

<p>&nbsp;</p>

<p>Note: at the time of updating this work plan, the decision was made to proceed in an evolutionary way and build on the 1.0 code base, using existing test, packaging and deployment procedures.&nbsp; Development will use existing PHP libraries where possible.</p>

<p>&nbsp;</p>

<p>Guiding principles:</p>

<ul>
	<li>rough consensus, working code</li>
	<li>user experience is fire-and-forget</li>
	<li>less is more: design the UI for people with better things to do with their time.&nbsp; Less clicks is better, less clutter is better</li>
	<li>aim for a UI that is as clean as possible</li>
	<li>aim for a user experience that closely follows the email paradigm</li>
</ul>

<p>&nbsp;</p>

<h2 id="342e2066696c6573656e64657220312e353a206e65772066726f6e742d656e64207569206f6e206578697374696e6720312e30206261636b656e6420636f64652062617365">4. FileSender 1.5: New front-end UI on existing 1.0 backend code base</h2>

<ul>
	<li>Remove Gears dependency, remove as much of Flash as possible</li>
	<li>Aim for HTML+JavaScript only front end</li>
	<li>Feature-parity with FileSender 1.0: no new features, 100% focus on removing Gears and as much of Flash as possible</li>
	<li>Use HTML5 FileAPI for file upload of any size, currently supported by at least FF4 and Chrome, expected to become future standard for all browsers</li>
	<li>Ensure reliable progress bar for uploads &lt;= 2GB in non-HTML5 FileAPI browsers (FF3.x, IE7,8,9)</li>
	<li>HTML-only admin interface</li>
	<li>Backend changes where needed</li>
	<li>Opportunistic backend code cleaning (clean it when you see it) to remove redundant pieces</li>
	<li>Code security audit</li>
	<li>to be released as FileSender 1.5</li>
	<li>make sure FileSender 1.5 works with SimpleSAMLphp 1.7.0+ (ticket <a href="/spaces/file_sender/tickets/271">#271</a>)</li>
</ul>

<p>&nbsp;</p>

<h2 id="352e2066696c6573656e64657220312e363a206261636b656e6420696d70726f76656d656e7473">5. FileSender 1.6: backend improvements</h2>

<ul>
	<li>The Quick Win release</li>
	<li><strong>Database abastraction.</strong>&nbsp; Implement and test for Postgresql and MySQL.&nbsp; Implement database schemas, indexes/optimalisations and test thoroughly.<span style="background-color: #ffff00;"> [ READY for 1.5]</span></li>
	<li><strong>New database schema</strong> to provide foundation for other features, with indexes and optimisations.&nbsp; Needs to allow for pause/resume/selective resend which require database to know which chunks already have arrived, sending multiple files in one go, file integrity checksums, multi-file-upload, quota support, multi-tenant, REST-API.</li>
	<li><strong>Revisit email bounce handling and dealing with SPF</strong> (ticket <a href="/spaces/file_sender/tickets/384">#384</a>)&nbsp;<span style="background-color: #ffff00;"> [ READY for 1.0.1]</span></li>
</ul>

<ul>
	<li><strong>Localisation 1</strong>: enable use of multiple language files.&nbsp; UI must support the user selecting different languages (with flag or text) <span style="background-color: #ffff00;">[READY for 1.5]</span></li>
	<li><strong>Localisation 2:</strong> use browsers built-in language preference to auto-select preferred language (wrap up what doesn&#39;t work in 1.5)</li>
</ul>

<p>&nbsp;</p>

<h2 id="66696c6573656e64657220322e303a20656e61626c696e67206261636b656e6420666f72206e6577206665617475726573">FileSender 2.0: enabling backend for new features</h2>

<p>Systematic code modularisation</p>

<p>&nbsp;</p>

<p>REST-API</p>

<ul>
	<li>1. adapt database schema to support improved file upload handling (multiple files in one go, resuming): database schema in such a way that production services can easy migrate: users get something new, don&#39;t need to migrate?</li>
	<li>then API</li>
	<li>upload client on ipad/iphone? (low prio)</li>
	<li>question: which features conflict with Flash component</li>
</ul>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2 id="6._new_features">6. New features</h2>

<p><em>New features will be prioritised and then implemented in order of priority.</em>&nbsp; Features with UI consequences need to be grouped together as much as possible to ensure UI consistency and no-clutter.</p>

<ul>
	<li>Enable pausing downloads for those browsers supporting it</li>
	<li>Enable direct-URL download for tools such as wget</li>
	<li>Authentication on the download URL</li>
</ul>

<p>&nbsp;</p>

<p>&nbsp;</p>

<ul>
	<li>Improved file upload handling 1: select and upload multiple files in one upload transaction (to one or more users, but same files go to all users!)</li>
	<li>Improved file upload handling 2: drag &amp; drop</li>
	<li>Improved file upload handling 3: select and upload a folder in one upload transaction (a sort of auto-zip feature)</li>
</ul>

<p>&nbsp;</p>

<ul>
	<li>UI1: input validation checks on-input, for example email address</li>
	<li>UI2: display &quot;characters left&quot; counter for subject and message fields</li>
	<li>UI3: ensure users with visual impairment can use FileSender: ticket <a href="/spaces/file_sender/tickets/349">#349</a></li>
	<li>UI4: allow for different &quot;first use&quot; and &quot;recurring use&quot; views to allow &quot;first use&quot; to include for example an introduction video that you won&#39;t be bothered with lateron</li>
	<li>UI5: include &quot;advanced features&quot; functionality, hiding stuff that is not needed for simple operation of service</li>
	<li>UI6: allow for &quot;two-click&quot; use: a user ought to be able to send a file to himself with selecting a file followed by pressing send.</li>
</ul>

<p>&nbsp;</p>

<ul>
	<li>Include addressbook functionality, possibly including groups, to make it easier to use FileSender for transporting files in longer-term collaboration relations</li>
</ul>

<ul>
	<li>Allow authorising of individual authorised users much in the same way we now authorise admins, preferably using through the admin web interface. Use case: allow only certain guest users coming from OpenIdP guest logons (user-whitelisting from open identity providers)</li>
	<li>Quota support, ticket <a href="/spaces/file_sender/tickets/385">#385</a></li>
</ul>

<p>&nbsp;</p>

<ul>
	<li>Reliability: resumable uploads for uploading only missing chunks in case of large file upload error and to allow for pause/resume functionality (has GUI implications)</li>
	<li>Speed-up: parallelised upload-threads</li>
	<li>Support use from mobile platforms (iOS (iPhone, iPad), Android, Windows Phone, NOT Symbian) (belnet: low prio)</li>
	<li>Well defined and documented REST API, including AuthN/Auth needed to include FileSender in automated scientific workflow</li>
	<li>Integration with virus scanning (also needs database)</li>
	<li>Integration with time stamping service</li>
	<li>Config: automatic configuration file sanity checker</li>
</ul>

<p>&nbsp;</p>

<ul>
	<li>Make FileSender entirely multi-tenant, both back-end and front-end, allowing for &quot;cloudification&quot; of a filesender install and service delivery to multiple organisations as well as per-institution branding if so desired.</li>
</ul>

<p>&nbsp;</p>

<h2 id="7._backend_code_improvements">7. Backend code improvements</h2>

<ul>
	<li>Code clean up</li>
</ul>

<p>&nbsp;</p>

<h2 id="8._make_upgrading_easy">8. Make upgrading easy</h2>

<ul>
	<li>Ensure localised content (CSS templates, language files, config files) does not get overwritten on upgrade</li>
	<li>Devise good upgrade process requiring least manual steps possible</li>
</ul>

<p>&nbsp;</p>

<h2 id="9._set_up_automated_testing_and_integrate_it_in_the_automated_build_process">9. Set up automated testing and integrate it in the automated build process</h2>

<ul>
	<li>automated testing from a user&#39;s point of view against the automated builds</li>
	<li>simulate different popular browsers</li>
	<li>Linux (standardise on Ubuntu desktop + Scientific Linux?), Mac (version?), Windows7 (older versions?)</li>
	<li>automated testing of API functionality after API is implemented</li>
</ul>

<h2 id="10._revise_logging_and_statistics">10. Revise logging and statistics</h2>

<ul>
	<li>systematic analysis of what we can log and what we wish to log where</li>
	<li>improve statistics-oriented logging, making it easier to do per-institution logging</li>
</ul>

<h2 id="11._project_organisation">11. Project organisation</h2>

<ul>
	<li>devise version support lifecycle</li>
	<li>secure funding for 2012 development</li>
	<li>devise workplan 2012 (december 2011)</li>
</ul>

