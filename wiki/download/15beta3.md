
      
      
      <h2>Release Version 1.5-beta3</h2><div>
<p> </p><p>Release date:  15 May 2012</p>
<table border="0">
<tbody>
<tr>
<td><b>Distribution file</b></td>
<td><b>MD5</b></td>
<td><b>SHA1</b></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.5-beta3.tar.gz">filesender-1.5-beta3.tar.gz</a></td>
<td><span style="font-family: courier new,courier;">ea0e28e7de1bb606225ff245c2e43e6b<br></span></td>
<td>684608aaa8dd48e487942ff5c4d56eda1397ec3d<br></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.5-beta3.zip">filesender-1.5-beta3.zip</a></td>
<td><span style="font-family: courier new,courier;">e4b591ced49d7c5794b112b8ce8a225f<br></span></td>
<td>a2a8c0a95c8aaaa224835bacbfcfec50f2133b91<br></td>
</tr>
</tbody>
</table>
<p>Release 1.5-beta3 is also available in the [[Installation - Debian 
Ubuntu|Debian]] and [[Installation - RPM|RPM]] package repositories and 
the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.5-beta3/">Subversion repository</a>. Currently Release 1.5-beta3 is distributed from the <b>unstable</b> repositories.</p>
<h2>Installation</h2>
<p>Documentation for this beta release is not finished yet but is 
largely the same as for the previous releases. Exceptions are documented
 in [[Installation notes for 1-5 development code]]. Note that although 
we have thoroughly tested this beta3 release it is not yet intended for 
production use.<br></p>
</div>
<div>
<h2>Upgrade Notes</h2>
<p>See [[Installation notes for 1-5 development code]] for important upgrade and installation notes. <br></p><h2>Changes since release 1.5-beta2</h2><p><br>   * Changes since 1.5-beta2<br>     - HTML5 upload support for the upcoming FireFox 13.<br>     - Improvements in the User Interface.<br>     - Improved user feedback and error reporting<br>     - Improved server side logging.<br>     - Various small bug fixes and enhancements.<br><br>   * Changed features:<br>     - Option to securely wipe (shred) expired files in the daily cron job.<br>     - Separate text definitions for 'logon' button and title of the landing page.<br>     - The configured 'Site Name' is now used on the landing page <br></p>
</div>
<div>
<h2>Changes since release 1.5-beta1</h2><p> </p><p>   * Major changes since 1.5-beta1<br>     - The ./config directory as distributed now only contains a sample<br>       config-dist.php file. All other templates/sample files have been<br>       moved to ./config-templates or their contents have been merged<br>       into the ./language/* files.</p><p>     - The supplied config-dist.php has been cleaned up and contains some <br>        important changes. It is recommended to create a fresh config.php<br>        from the supplied config-dist.php file and adapt that one with your<br>        local settings.<br>     - Two database column type changes (needs manual adjustment when <br>       upgrading).<br>     - Changed and consolidated language file naming scheme.<br>     - Added Czech, Slovenian, Italian, Spanish, Croatian and Hungarian<br>       language files.<br>     - Updated Dutch and Norwegian language files.<br><br>   * Major (less visible) changes since 1.5-beta1<br>     - Further improvements in workflow, validation/error handling and<br>       input/output pathways.<br>     - Minor bug fixes and enhancements. <br></p><h2>Changes since 1.1 RELEASE</h2>
<p> </p>
<p>   * Major changes since 1.1/1.0.1</p>
<p>     - Replaced Flash User Interface with a HTML-only interface<br>     - Dropped Gears dependency, upload of large (>2G) files now requires<br>       a modern HTML5 capable browser, other browsers are limited to 2G<br>       uploads (using a small Flash-application).<br>     - Added automatic language selection (English, Norwegian, Dutch)<br>     - Added Database Abstraction Layer (PDO) to facilitate the use<br>       of MySQL and possibly other databases as backend.<br><br>   * Major (visible) changes since earlier 1.5.0 development builds<br>     - Added French and German languages (contributed by RESTENA)<br>     - Replaced MDB2 with PDO DB Abstraction Layer<br><br>   * Major (less visible) changes since earlier development builds<br>     - Input/output pathways have been simplified<br>     - Input/output sanitisation and validation is done<br>     - Much code and program flow has been cleaned up and simplified<br>     - We now use mostly prepared statements for database interaction<br>     - All pages are now W3C compliant<br><br></p>
<h2>Known issues</h2>
This is the third beta for 1.5 and there are still some issues to be tackled in the next beta4 cycle. See <a href="http://www.assembla.com/spaces/file_sender/wiki/tickets">http://www.assembla.com/spaces/file_sender/tickets</a> for a current list of issues.</div>
<div>
<h2>Support and Feedback</h2>
<p>See [[Support and Mailinglists]] and [[Feature requests]].</p>
</div>
    
    
    
    
    
    
    
    
    
    
    
    
    
    
