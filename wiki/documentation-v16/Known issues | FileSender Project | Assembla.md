
      
      
      
      
      
      
      <p><span style="font-size: 100%;">This page outlines the known issues for the FileSender </span><b style="font-size: 100%;">1.6 release</b></p><p><span style="background-color: rgb(255, 255, 255);"> </span>
      
      </p><p><span style="background-color: #ff0000;"></span><span style="background-color: #ff0000;"></span>FileSender

 1.6 contains a number of known issues that we were unable to fix 
before releasing.  Some of these issues are a consequence of certain 
architectural decisions or deficiencies in technology we depend on.  The
 issues are annoying but not show stopping.  The more visible ones 
you're bound to get questions about are: </p><p> </p><ol><li><span style="background-color: rgb(255, 255, 255);">UTF8:
 when downloading a 
filename with international characters other than ISO-8859-1 it will 
look 'funny' but fully usable when downloaded with Internet Explorer.  
This is a problem in IE and not in FileSender.  See bug ticket <a href="https://www.assembla.com/spaces/file_sender/tickets/374">#374</a></span></li><li><span style="background-color: rgb(255, 255, 255);">When a user starts 
downloading a file, and then cancels the download, a "user has 
downloaded the file" email is still generated.  See bug ticket <a href="https://www.assembla.com/spaces/file_sender/tickets/307">#307</a>  </span></li><li><span style="background-color: rgb(255, 255, 255);">When a user has downloaded a
 file, the download page is accessible until the user's local browser 
cache is cleared or the file is deleted on the FileSender server.  This 
is a consequence of the choice to rely on a unique URL for 
authenticating users to downloads.  See bug ticket <a href="https://www.assembla.com/spaces/file_sender/tickets/187">#187</a>.</span></li><li><span style="background-color: rgb(255, 255, 255);">Safari 5 (Snow Leopard) only: Duplicate mails when resending or deleting a file or voucher with Safari 5. See bug ticket #1062)</span><br></li><li><span style="background-color: rgb(255, 255, 255);">Safari 5 (Snow Leopard) only: When downloading a small file more than once Safari serves the file from its local cache.  No download counters are incremented ad no download emails are sent.  See bug ticket #597. </span></li><li><span style="background-color: rgb(255, 255, 255);">Session time-out with SAML2 authentication and long uploads: with uploads that take a long time, say 8 hours or more, a session can time out if a SAML2 Identity Provider is used.  See bug ticket #905.</span></li></ol><p><span style="background-color: rgb(255, 153, 0);"><br></span></p><p><span style="background-color: rgb(255, 255, 255);">In
 addition we found a number of smaller issues you're less likely to 
encounter.   Before submitting a bug report please make sure you run the
 latest FileSender version and check <a href="https://www.assembla.com/spaces/b516sOlY8r3PPQeJe5afGb/tickets/report/u1270273">the known issues tickets for version 1.6</a>.  If you get helpdesk calls because of a known issue, please let us know as it helps us prioritise!</span><br></p>
    
    
    
    
    
    
    
    
