
      
      
      
      
      <p><br></p><h2>Release Version 1.6-beta1</h2><div>
<p> </p><p>Release date:  31 December 2013</p>
<table border="0">
<tbody>
<tr>
<td><b>Distribution file</b></td>
<td><b>MD5</b></td>
<td><b>SHA1</b></td>
</tr>
<tr>
<td><a href="https://filesender-dev.surfnet.nl/releases/filesender-1.6-beta1.tar.gz">filesender-1.6-beta1.tar.gz</a></td>
<td><span style="font-family: courier new,courier;">3be6670615dbe72cda78bdf7df8febbf<br></span></td>
<td>ff85301019f7fd001e10513b925f39f4d7b19599<br></td>
</tr>
<tr>
<td><a href="https://filesender-dev.surfnet.nl/releases//filesender-1.6-beta1.zip">filesender-1.6-beta1.zip</a></td>
<td><span style="font-family: courier new,courier;">e6b6d850e6b962f0d87c46a291d75212<br></span></td>
<td>9698070143aff337f4947ab13cdebcc1f3d18070<br></td>
</tr>
</tbody>
</table>
<p>Release 1.6-beta1 is also available in the 
[[Installation_-_Debian_Ubuntu|Debian]] and [[Installation_-_RPM|RPM]] 
package repositories and 
the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.6-beta1/">Subversion repository</a>. Currently Release 1.6-beta1 is distributed from the <b>unstable</b> repositories.</p>
<h2>Installation</h2>
<p>Documentation (in progress) for this release is available at [[Documentation v1-6]]<br></p>
</div>
<div>
<h2>Upgrade Notes</h2>
<p>See [[Upgrade notes to 1-6]] for important upgrade and installation notes. </p><h2>Major changes since 1.5</h2>     - Add TeraSender code (#885, #899, #1064)<br>       - Allows for faster HTML5 uploads<br>       - Upgrade note: new configuration options<br>       - Default not enabled, enable in config.php<br>     - New layout of My Files page (#597)<br>       - add number of downloads<br>       - expandable per file details view<br>       - removed 'me' substition<br>     - Add optional personal message and subject to guest vouchers (#637,#963)<br>       - Upgrade note: change in configuration mail template<br>     - Recipient address autocomplete based on previous recipients (#821)<br>       - Upgrade note: new configuration options<br>     - Add selector when multiple mail adresses are available (#184)<br>       Modified patch from Thijs Kinkhorst<br><h2>Changes since 1.5</h2>     - Upgrade of JQuery and JQueryUI to 1.10.2 (#819)<br>     - Default Voucher Subject configurable (#774)<br>       Patch contributed by Thijs Kinkhorst<br>     - Add a customisable footer through the language definitions (#871)<br>       Modified patch from Jean-Philippe Evrard, BELNET<br>     - logout.php and invalidvoucher.php removed and integrated in<br>       the core index.php (#904)<br>       - Upgrade note: needs change in config.php when upgrading,<br>         logout page breaks if config.php isn't adapted<br>     - New download.php (#858)<br>       - redo logic for mail sending and logging<br>       - added partial download (HTTP range) functionality (not used yet)<br>       - some cleanup<br>     - Add option to suppress carbon copy of download confirmation mail<br>       to downloader (#985)<br>     - Add sqlite init-script and 'how to' (#898)<br>       Patch contributed by Dick Visser<br>     - Minor layout changes (#965,#966)<br><h2>Fixes since 1.5</h2>     - Optimise PDO Query row count statements (#888)<br>       Patch from Dick Visser<br>     - Remove unused validVoucher() function<br>       Patch from Thijs Kinkhorst<br>     - Hash fileuid for pending/validateupload entry (#884)<br>       Bug noticed by Dick Visser<br>     - Replace $_REQUEST['PHPSESSID'] with session_id() (#897)<br>     - Fix declarations for fileexpirydate and logdate in mysql init script (#932)<br>     - Fixed use of single quote in filename with Flash uploads (#895)<br><h2>Known issues</h2> Important known issues can be found at [[Known issues 1-6]]. 
See also <a href="https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373">https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373</a> for a current list of issues.</div>
<div>
<h2>Support and Feedback</h2>
<p>See [[Support and Mailinglists]] and [[Feature requests]].</p>
</div>
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
