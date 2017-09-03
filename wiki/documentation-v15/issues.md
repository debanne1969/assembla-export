
      
      
      
      
      
      <p><span style="background-color: rgb(255, 255, 255);">This page outlines the known issues for the FileSender <b>1.5 release</b><br> </span>
      
      </p><p><span style="background-color: #ff0000;"></span><span style="background-color: #ff0000;"></span>FileSender
 1.5 contains a number of known issues that we were unable to fix 
before releasing.  Some of these issues are a consequence of certain 
architectural decisions or deficiencies in technology we depend on.  The issues are annoying but not show stopping.  The more visible ones you're bound to get questions about are: </p><p> </p><ol><li><span style="background-color: #ffffff;">UTF8: when downloading a 
filename with international characters other than ISO-8859-1 it will 
look 'funny' but fully usable when downloaded with Internet Explorer.  This is a problem in IE and not in FileSender.  See bug ticket <a href="https://www.assembla.com/spaces/file_sender/tickets/374"><span style="background-color: #ffffff;">#374</span></a></span></li><li><span style="background-color: #ffffff;"><span style="background-color: #ffffff;"><span style="background-color: #ffffff;">When a user starts 
downloading a file, and then cancels the download, a "user has 
downloaded the file" email is still generated.  See bug ticket <a href="https://www.assembla.com/spaces/file_sender/tickets/307"><span style="background-color: #ffffff;">#307</span></a></span> </span></span> </li><li><span style="background-color: #ffffff;">When a user has downloaded a
 file, the download page is accessible until the user's local browser 
cache is cleared or the file is deleted on the FileSender server.  This 
is a consequence of the choice to rely on a unique URL for 
authenticating users to downloads.  See bug ticket <a href="https://www.assembla.com/spaces/file_sender/tickets/187"><span style="background-color: #ffffff;">#187</span></a>.</span></li><li><span style="background-color: #ffffff;">Problematic downloads using Chrome on Windows7-without-SP1.  See bug ticket #588. <br></span></li></ol><p><span style="background-color: #ffffff;"><br></span></p><p><span style="background-color: #ffffff;">In addition we found a number of smaller issues you're less likely to encounter.   Before submitting a bug report please make sure you run the latest FileSender version and check <span style="background-color: rgb(255, 255, 255);"><a href="https://www.assembla.com/spaces/b516sOlY8r3PPQeJe5afGb/tickets?tickets_report_id=u39562">the open bug tickets for version 1.5</a></span><span style="background-color: rgb(255, 255, 255);"><span style=""></span></span>.  If you do get helpdesk calls because of an open bug, please do let us know as it helps us prioritise!<br></span></p>
    
