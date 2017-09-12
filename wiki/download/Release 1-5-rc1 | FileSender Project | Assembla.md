
      
      <h2>Release Version 1.5-rc1</h2><div>
<p> </p><p>Release date:  22 October 2012</p>
<table border="0">
<tbody>
<tr>
<td><b>Distribution file</b></td>
<td><b>MD5</b></td>
<td><b>SHA1</b></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.5-rc1.tar.gz">filesender-1.5-rc1.tar.gz</a></td>
<td><span style="font-family: courier new,courier;">a0fe32333c3a821aa7eebb5857685b1f<br></span></td>
<td>5efe47308c6b8109139969080e798e8bbf1154ff<br></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.5-rc1.zip">filesender-1.5-rc1.zip</a></td>
<td><span style="font-family: courier new,courier;">ebb9228e4ff4a31e49eb07ab8bab1c06<br></span></td>
<td>3d79c18cd9c04e8895c8372727030e0ce8dec099<br></td>
</tr>
</tbody>
</table>
<p>Release 1.5-rc1 is also available in the [[Installation - Debian 
Ubuntu|Debian]] and [[Installation - RPM|RPM]] package repositories and 
the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.5-rc1/">Subversion repository</a>. Currently Release 1.5-rc1 is distributed from the <b>unstable</b> repositories.</p>
<h2>Installation</h2>
<p>Documentation for this release candidate is not finished yet but is 
largely the same as for the previous releases. Exceptions are documented
 in [[Installation notes for 1-5 development code]]. This release candidate has been thoroughly tested and will be field tested on three production installs before the final release.<br></p>
</div>
<div>
<h2>Upgrade Notes</h2>
<p>See [[Installation notes for 1-5 development code]] for important upgrade and installation notes. </p><h2>Changes since release 1.5-beta4</h2><p> </p><p>  * Changes since 1.5-beta4<br>     - Update of default Help text (English, Dutch, Norwegian) (#650, #651)<br>     - Updated language definitions<br>     - Fixed links to caniuse.com (all languages)<br>     - Disable Send button after first press (#805, #811, #812)<br>     - Do not mark Guest Voucher as used when upload fails (#807)<br>     - Prevent erroneous showing of DatePicker in recent Chrome versions (#823)<br>     - Debug setting set to false in config-dist.php (#804)<br>     - Only log user information when debug is true (#808)<br>     - Fixes in error logging (#806)<br>     - Remove dependency on php-gmp (#813)<br>     - Fixed include files in emailbouncehandler.php<br>     - Various small changes and bug fixes (#709, #794, #809, #810, #828) </p><h2>Changes since release 1.5-beta3</h2><br><p>   * Changes since 1.5-beta3<br>     - Security: make admin check more strict (#751)<br>     - Security: Fixed reset of session cookie when switching to HTTPS (#757)<br>     - Security: Fixed 2 potential XSS vulnerabilities (#754)<br>     - Security: always prevent caching of sensitive pages (#762)<br>     - Security: add XSRF checks for POSTs and additional auth-checks for GETs (#753)<br>     - Security: add additional recommended PHP settings (#758)<br>     - Fixes and improvements in language selection (#662, #745)<br>     - Updated language definitions<br>     - Disabled HTML5 capability for Opera (#527)<br>     - Improvements on handling and reporting of missing required SAML attributes (#628)<br>     - Bugfixes in mail error-handling (#713)<br>     - Improved  Help text (en_AU only) (#650, #651)<br>     - Removed HTML5URL configuration setting (merged into Help text) (#744)<br>     - Various small bug fixes (#691, #731, #742, #794)<br><br></p><h2>Changes since release 1.5-beta2</h2><p><br>   * Changes since 1.5-beta2<br>     - HTML5 upload support for the upcoming FireFox 13.<br>     - Improvements in the User Interface.<br>     - Improved user feedback and error reporting<br>     - Improved server side logging.<br>     - Various small bug fixes and enhancements.<br><br>   * Changed features:<br>     - Option to securely wipe (shred) expired files in the daily cron job.<br>     - Separate text definitions for 'logon' button and title of the landing page.<br>     - The configured 'Site Name' is now used on the landing page <br></p>
</div>
<div>
<h2>Changes since release 1.5-beta1</h2><p> </p><p>   * Major changes since 1.5-beta1<br>     - The ./config directory as distributed now only contains a sample<br>       config-dist.php file. All other templates/sample files have been<br>       moved to ./config-templates or their contents have been merged<br>       into the ./language/* files.</p><p>     - The supplied config-dist.php has been cleaned up and contains some <br>        important changes. It is recommended to create a fresh config.php<br>        from the supplied config-dist.php file and adapt that one with your<br>        local settings.<br>     - Two database column type changes (needs manual adjustment when <br>       upgrading).<br>     - Changed and consolidated language file naming scheme.<br>     - Added Czech, Slovenian, Italian, Spanish, Croatian and Hungarian<br>       language files.<br>     - Updated Dutch and Norwegian language files.<br><br>   * Major (less visible) changes since 1.5-beta1<br>     - Further improvements in workflow, validation/error handling and<br>       input/output pathways.<br>     - Minor bug fixes and enhancements. <br></p><h2>Changes since 1.1 RELEASE</h2>
<p> </p>
<p>   * Major changes since 1.1/1.0.1</p>
<p>     - Replaced Flash User Interface with a HTML-only interface<br>     - Dropped Gears dependency, upload of large (>2G) files now requires<br>       a modern HTML5 capable browser, other browsers are limited to 2G<br>       uploads (using a small Flash-application).<br>     - Added automatic language selection (English, Norwegian, Dutch)<br>     - Added Database Abstraction Layer (PDO) to facilitate the use<br>       of MySQL and possibly other databases as backend.<br><br>   * Major (visible) changes since earlier 1.5.0 development builds<br>     - Added French and German languages (contributed by RESTENA)<br>     - Replaced MDB2 with PDO DB Abstraction Layer<br><br>   * Major (less visible) changes since earlier development builds<br>     - Input/output pathways have been simplified<br>     - Input/output sanitisation and validation is done<br>     - Much code and program flow has been cleaned up and simplified<br>     - We now use mostly prepared statements for database interaction<br>     - All pages are now W3C compliant<br><br></p>
<h2>Known issues</h2>
This is the first release candidate for 1.5. During this rc1 phase we'll run the code on a few production installs to verify production readiness and will update the documentation accordingly. No code 
changes are planned. See <a href="http://www.assembla.com/spaces/file_sender/tickets">http://www.assembla.com/spaces/file_sender/tickets</a> for a current list of issues.</div>
<div>
<h2>Support and Feedback</h2>
<p>See [[Support and Mailinglists]] and [[Feature requests]].</p>
</div>
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
