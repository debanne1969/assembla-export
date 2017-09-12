
      
      
      
      <p> 
      </p><h2>Release Version 1.1.1</h2>
<p>Release date: 31 May 2011</p>
<table border="0">
<tbody>
<tr>
<td><b>Distribution file</b></td>
<td><b>MD5</b></td>
<td><b>SHA1</b></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.1.1.tar.gz">filesender-1.1.1.tar.gz</a></td>
<td><span style="font-family: courier new,courier;">85611acdcc33013be491ba9636ca650f<br></span></td>
<td> c2bc901300751768fa87cce9689c3dd8b7738314<span style="font-family: courier new,courier;"></span></td>
</tr>
<tr>
<td><a href="http://download.filesender.org/filesender-1.1.1.zip">filesender-1.1.1.zip</a></td>
<td><span style="font-family: courier new,courier;">93b4f12df8293a81a57f3967b27df9cd<br></span></td>
<td> 6a100971663937c4057fdf821351d0e14e66008e<span style="font-family: courier new,courier;"></span></td>
</tr>
</tbody>
</table>
<p>Release 1.1.1 is also available in the [[Installation - Debian Ubuntu|Debian]] and [[Installation - RPM|RPM]] package repositories and 
the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.1.1/">Subversion repository</a>. Currently Release 1.1.1 is distributed from the <b>oldstable</b> repositories </p>
<h2>Installation</h2>
<p>See [[Installation_-_Linux_Source_-_v1-1]]</p>
<h2>Upgrade Notes</h2>
<p>When upgrading from a previous beta version (including 1.0(.x) RELEASE) please read the [[Upgrade notes up to v1-1-1]] <b>before</b> upgrading.</p>
<h2>Changes since 1.1 RELEASE</h2>   * Important changes since 1.1<br>     - Support for changed HTML5 semantics in Firefox 13+ (#730).<br>     - Fixed potential privilege elevation issue which under certain<br>       conditions could give a normal user access to the admin<br>       interface (#750).<br>     - Change in database column type for fileto/logto (#739).<br>       When upgrading from previous versions you should manually alter<br>       the relevant column type in the database with:<br><br>       #sudo -u postgres psql filesender<br>         ALTER TABLE files ALTER fileto TYPE text;<br>         ALTER TABLE logs ALTER logto TYPE text;<br>         \q<br><br>   * Minor fixes and changes since 1.1<br>     - Additional email validation in Mail.php (#746).<br>     - Fix for multi-value SAML-attribute logging (#747).<br>     - Fix for upload with a backslash or double quote in the filename (#601).<br>     - Workaround for download of files with a double quote in the<br>       filename (#602).<br><h2>Known issues</h2>
<p>See [[Known issues in v1-1]].</p>
<h2>Support and Feedback</h2>
<p>See [[Support and Mailinglists]] and [[Feature requests]].</p>
    
    
    
    
    
