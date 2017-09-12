
      <p>This page provides an overview of the current layout of the FileSender database, with descriptions of the purpose of each field.<br><br></p>
<h1>Table: files<br><br></h1>
<table style="width: 100%;" align="left" border="1">
<tbody>
<tr>
<td style="width: 100px;"><b>COLUMN NAME</b></td>
<td style="width: 175px;"><b>DATA TYPE</b></td>
<td><b>DESCRIPTION</b></td>
</tr>
<tr>
<td>fileto</td>
<td>text</td>
<td>Receiver's email address.</td>
</tr>
<tr>
<td>filesubject</td>
<td>character varying(250)</td>
<td>Title, used as part of subject in emails.</td>
</tr>
<tr>
<td>filevoucheruid</td>
<td>character varying(60)</td>
<td>Unique file id based on the combination of "file" and "to". This is used for download links.</td>
</tr>
<tr>
<td>filemessage</td>
<td>text</td>
<td>Message from the sender to the receiver, used as part of body in emails.</td>
</tr>
<tr>
<td>filefrom</td>
<td>character varying(250)</td>
<td>Sender's email address.</td>
</tr>
<tr>
<td>filesize</td>
<td>bigint</td>
<td>The size of the file, in bytes.</td>
</tr>
<tr>
<td>fileoriginalname</td>
<td>character varying(500)</td>
<td>The name of the file.</td>
</tr>
<tr>
<td>filestatus</td>
<td>character varying(60)</td>
<td>The status of the file, can be any one of: "", "Voucher", "Voucher Cancelled", "Closed", "Deleted".</td>
</tr>
<tr>
<td>fileip4address</td>
<td>character varying(24)</td>
<td>Sender's IPv4 address.</td>
</tr>
<tr>
<td>fileip6address</td>
<td>character varying(45)</td>
<td>Sender's IPv6 address. Not currently used?</td>
</tr>
<tr>
<td>filesendersname</td>
<td>character varying(250)</td>
<td>Never used?</td>
</tr>
<tr>
<td>filereceiversname</td>
<td>character varying(250)</td>
<td>Never used?</td>
</tr>
<tr>
<td>filevouchertype</td>
<td>character varying(60)</td>
<td>Never used?</td>
</tr>
<tr>
<td>fileuid</td>
<td>character varying(60)</td>
<td>Unique file id.</td>
</tr>
<tr>
<td><b>fileid</b></td>
<td><b>integer</b></td>
<td><b>Primary key. Auto incrementing number.</b></td>
</tr>
<tr>
<td>fileexpirydate</td>
<td>timestamp without time zone</td>
<td>The date and time at which the file will expire.</td>
</tr>
<tr>
<td>fileactivitydate</td>
<td>timestamp without time zone</td>
<td>The date and time at which the file entry was last updated.</td>
</tr>
<tr>
<td>fileauthuseruid</td>
<td>character varying(500)</td>
<td>Uniquely identifies users based on their authentication.</td>
</tr>
<tr>
<td>filecreateddate</td>
<td>timestamp without time zone</td>
<td>The date and time at which the file was uploaded.</td>
</tr>
<tr>
<td>fileauthurl</td>
<td>character varying(500)</td>
<td>Never used?</td>
</tr>
<tr>
<td>fileauthuseremail</td>
<td>character varying(255)</td>
<td>User's email address, based on their authentication data.</td>
</tr>
</tbody>
</table>
<p> </p>
<h1>Table: logs<br><br></h1>
<table style="width: 100%; height: 316px;" align="left" border="1">
<tbody>
<tr>
<td style="width: 100px;"><b>COLUMN NAME</b></td>
<td><b>DATA TYPE</b></td>
<td><b>DESCRIPTION</b></td>
</tr>
<tr>
<td><b>logid</b></td>
<td style="width: 175px;"><b>integer</b></td>
<td><b>Primary key. Auto incrementing number.</b></td>
</tr>
<tr>
<td>logfileuid</td>
<td>character varying(60)</td>
<td>Unique file id.</td>
</tr>
<tr>
<td>logtype</td>
<td>character varying(60)</td>
<td>The type of logged event. Can be any one of the following: Voucher Cancelled, Uploaded, File Removed (Expired), Error, File Moved, Updated, Upload Attempt, Download, Voucher Sent, File Cancelled, Voucher Closed.</td>
</tr>
<tr>
<td>logfrom</td>
<td>character varying(250)</td>
<td>Sender's email address.</td>
</tr>
<tr>
<td>logto</td>
<td>text</td>
<td>Receiver's email address.</td>
</tr>
<tr>
<td>logdate</td>
<td>timestamp without time zone</td>
<td>The date and time at which this event was logged.</td>
</tr>
<tr>
<td>logtime</td>
<td>time with time zone</td>
<td>Deprecated field, no longer used.</td>
</tr>
<tr>
<td>logfilesize</td>
<td>bigint</td>
<td>The size of the file connected to this log entry, in bytes.</td>
</tr>
<tr>
<td>logfilename</td>
<td>character varying(250)</td>
<td>The name of the file connected to this log entry.</td>
</tr>
<tr>
<td>logsessionid</td>
<td>character varying(60)</td>
<td>Never used?</td>
</tr>
<tr>
<td>logmessage</td>
<td>text</td>
<td>A message describing the reason for the log entry.</td>
</tr>
<tr>
<td>logvoucheruid</td>
<td>character varying(60)</td>
<td>Unique file id based on the combination of "file" and "to". This is used for download links.</td>
</tr>
<tr>
<td>logauthuseruid</td>
<td>character varying(500)</td>
<td>Uniquely identifies users based on their authentication.</td>
</tr>
</tbody>
</table>
<p> </p>
    
