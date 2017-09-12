
      <h2>Release Version 1.6-rc1</h2><div>
<p> </p><p>Release date:  4 April 2014</p>
<table border="0">
<tbody>
<tr>
<td><b>Distribution file</b></td>
<td><b>MD5</b></td>
<td><b>SHA1</b></td>
</tr>
<tr>
<td><a href="https://filesender-dev.surfnet.nl/releases/filesender-1.6-rc1.tar.gz">filesender-1.6-rc1.tar.gz</a></td>
<td><span style="font-family: courier new,courier;">32b71d3d1f9d13ab215a71dc9dbba7c4<br></span></td>
<td>2cf9a3e8ac8c3c740e2dbef06aca072b409b2136<br></td>
</tr>
<tr>
<td><a href="https://filesender-dev.surfnet.nl/releases//filesender-1.6-rc1.zip">filesender-1.6-rc1.zip</a></td>
<td><span style="font-family: courier new,courier;">03a52805cea406b6502906c57982b116<br></span></td>
<td>ae03347995b9d4fc89946600e2c635550911bc5a<br></td>
</tr>
</tbody>
</table>
<p>Release 1.6-rc1 is also available in the 
[[Installation_-_Debian_Ubuntu|Debian]] and [[Installation_-_RPM|RPM]] 
package repositories and 
the <a href="http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-1.6-rc1/">Subversion repository</a>. Currently Release 1.6-rc1 is distributed from the <b>unstable</b> repositories.</p>
<h2>Installation</h2>
<p>Documentation (in progress) for this release is available at [[Documentation v1-6]]<br></p>
</div>
<div>
<h2>Upgrade Notes</h2>
<p>See [[Upgrade notes to 1-6]] for important upgrade and installation notes.  <br></p><p></p><h2>Changes since 1.6-beta1</h2><p>     - Download pause/resume now possible with browsers supporting<br>       partial download (most notably Firefox, IE11, curl and wget)<br>       (#1076)<br>     - 'terasender' default disabled in config-dist.php (#1077)<br>     - Added IE10+ and Safari 6+ to supported browsers in HELP text<br>       for en, no and nl languages (#1063)<br></p><h2>Fixes since 1.6-beta1</h2><p>     - Security: also escape single quotes for externally supplied<br>       output (#1079)<br>     - Security: encode MMredirectURL in Flash detection code (#1078)<br>     - Security: strict type comparison in XSFR check (#1080)<br>     - 'friendly name' extraction fixed (#1068)<br>     - Various fixes and improvements in the partial download code (#1076)<br>       - chunked reading and buffering to prevent server side memory<br>         exhaustion with large range requests<br>       - more robust range request detection to make actual pause/resume<br>         possible <br></p><h2>Major changes since 1.5</h2>     - Add TeraSender code (#885, #899, #1064)<br>       - Allows for faster HTML5 uploads<br>       - Upgrade note: new configuration options<br>       - Default not enabled, enable in config.php<br>     - New layout of My Files page (#597)<br>       - add number of downloads<br>       - expandable per file details view<br>       - removed 'me' substition<br>     - Add optional personal message and subject to guest vouchers (#637,#963)<br>       - Upgrade note: change in configuration mail template<br>     - Recipient address autocomplete based on previous recipients (#821)<br>       - Upgrade note: new configuration options<br>     - Add selector when multiple mail adresses are available (#184)<br>       Modified patch from Thijs Kinkhorst<br><h2>Changes since 1.5</h2>     - Upgrade of JQuery and JQueryUI to 1.10.2 (#819)<br>     - Default Voucher Subject configurable (#774)<br>       Patch contributed by Thijs Kinkhorst<br>     - Add a customisable footer through the language definitions (#871)<br>       Modified patch from Jean-Philippe Evrard, BELNET<br>     - logout.php and invalidvoucher.php removed and integrated in<br>       the core index.php (#904)<br>       - Upgrade note: needs change in config.php when upgrading,<br>         logout page breaks if config.php isn't adapted<br>     - New download.php (#858)<br>       - redo logic for mail sending and logging<br>       - added partial download (HTTP range) functionality (not used yet)<br>       - some cleanup<br>     - Add option to suppress carbon copy of download confirmation mail<br>       to downloader (#985)<br>     - Add sqlite init-script and 'how to' (#898)<br>       Patch contributed by Dick Visser<br>     - Minor layout changes (#965,#966)<br><h2>Fixes since 1.5</h2>     - Optimise PDO Query row count statements (#888)<br>       Patch from Dick Visser<br>     - Remove unused validVoucher() function<br>       Patch from Thijs Kinkhorst<br>     - Hash fileuid for pending/validateupload entry (#884)<br>       Bug noticed by Dick Visser<br>     - Replace $_REQUEST['PHPSESSID'] with session_id() (#897)<br>     - Fix declarations for fileexpirydate and logdate in mysql init script (#932)<br>     - Fixed use of single quote in filename with Flash uploads (#895)<br><h2>Known issues</h2> Important known issues can be found at [[Known issues 1-6]]. 
See also <a href="https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373">https://www.assembla.com/spaces/file_sender/tickets/cardwall?default_list_cardwall=filter:u671373</a> for a current list of issues.</div>
<div>
<h2>Support and Feedback</h2>
<p>See [[Support and Mailinglists]] and [[Feature requests]].</p>
</div>
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
