
      
      <div>
<h2>Release Version 1.5-beta1</h2>
<p>Release date: 13 February 2012</p>
<table border="0">
<tbody>
<tr>
<td><b>Distribution file</b></td>
<td><b>MD5</b></td>
<td><b>SHA1</b></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.5-beta1.tar.gz">filesender-1.5-beta1.tar.gz</a></td>
<td><span style="font-family: courier new,courier;">ac189f33c446664d1eeb6c0a13444155<br></span></td>
<td> <span style="font-family: courier new,courier;">5e88f7ed631ea173512a8bfaee44e1a37a0bece9</span></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.5-beta1.zip">filesender-1.5-beta1.zip</a></td>
<td><span style="font-family: courier new,courier;">6a837362bd31a4c792212b3cf6e0dafd<br></span></td>
<td> <span style="font-family: courier new,courier;">c7b762eaeb6043d9f08f2c4df2d82fffc30aa117</span></td>
</tr>
</tbody>
</table>
<p>Release 1.5-beta1 is also available in the [[Installation - Debian Ubuntu|Debian]] and [[Installation - RPM|RPM]] package repositories and the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.5-beta1/">Subversion repository</a>. Currently Release 1.5-beta1 is distributed from the <b>unstable</b> repositories.</p>
<h2>Installation</h2>
<p>Documentation for this beta release is not finished yet but is largely the same as fro the previous releases. Exceptions are documented in [[Installation notes for 1-5 development code]].Note that although we have thoroughly tested this beta1 release it is not yet intended for production use.<br></p>
</div>
<div>
<h2>Upgrade Notes</h2>
<p>See [[Installation notes for 1-5 development code]].</p>
</div>
<div>
<h2>Changes since 1.1 RELEASE</h2>
<p> </p>
<p>   * Major changes since 1.1/1.0.1</p>
<p>     - Replaced Flash User Interface with a HTML-only interface<br>     - Dropped Gears dependency, upload of large (>2G) files now requires<br>       a modern HTML5 capable browser, other browsers are limited to 2G<br>       uploads (using a small Flash-application).<br>     - Added automatic language selection (English, Norwegian, Dutch)<br>     - Added Database Abstraction Layer (PDO) to facilitate the use<br>       of MySQL and possibly other databases as backend.<br><br>   * Major (visible) changes since earlier 1.5.0 development builds<br>     - Added French and German languages (contributed by RESTENA)<br>     - Replaced MDB2 with PDO DB Abstraction Layer<br><br>   * Major (less visible) changes since earlier development builds<br>     - Input/output pathways have been simplified<br>     - Input/output sanitisation and validation is done<br>     - Much code and program flow has been cleaned up and simplified<br>     - We now use mostly prepared statements for database interaction<br>     - All pages are now W3C compliant<br><br></p>
<h2>Known issues</h2>
This is the first beta for 1.5 and there are still some rough edges to be fixed in the next beta2 cycle. See <a href="/spaces/file_sender/tickets">http://www.assembla.com/spaces/file_sender/tickets</a> for a current list of issues.</div>
<div>
<h2>Support and Feedback</h2>
<p>See [[Support and Mailinglists]] and [[Feature requests]].</p>
</div>
    
    
