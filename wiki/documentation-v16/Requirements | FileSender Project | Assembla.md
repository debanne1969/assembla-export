
      
      
      
      <p><span style="font-size: 100%;">This page outlines client and server minimum requirements for FileSender</span><b style="font-size: 100%;"> version 1.6</b></p>
<h4><b>Client requirements for uploads of any size<br></b></h4>
<ul><li><b>Web browser with HTML5 FileAPI support. </b></li><ul><li>Chrome, FireFox 17+, IE 10.0+, Safari 6.0.1+ and Opera 20+ </li><li><a href="http://caniuse.com/fileapi">Check here to monitor implementation progress</a> of the HTML5 FileAPI for all major browsers. In particular support for <a href="http://caniuse.com/filereader">FileReader API</a> and <a href="http://caniuse.com/bloburls">Blob URLs</a> needs to be light green (=supported) for a browser to support uploads larger then 2GB</li></ul></ul>
<h4><b>Client requirements for uploads up to 2GB using Flash<br></b></h4>
<ul><li><b>Web browser</b> - modern release</li><li><span style="background-color: rgb(255, 255, 255);"><b><a href="http://get.adobe.com/flashplayer/">Flash Player</a> 10.x browser plugin</b> </span>- required for the Flash upload component used with non-HTML5 browsers.  </li></ul><h4><b>Client requirements for downloads of all sizes</b></h4><ul><li> <b>Web browser</b> - modern release</li></ul>
<h4><b> Server requirements<br></b></h4>
<ul><li><b>64-bit Linux</b></li><li><b>Webserver</b>: any webserver will do, however our documentation assumes <a href="http://www.apache.org/httpd/">Apache</a> 2+; <b>ensure that the webserver will only use HTTPS for FileSender traffic!  Ensure that the files directory is non-exec.</b></li><li><b>SSL Server Certificate</b> recognised by popular browsers.  see the <a href="https://www.assembla.com/wiki/show/file_sender/Administrator_reference_manual" title="Administrator_reference_manual">Administrator_reference_manual</a> for more information, and the <a href="https://www.assembla.com/wiki/show/file_sender/FAQ" title="FAQ">FAQ</a> for a still quite relevant entry on why self signed certificates will cause issues for uploads with the Flash component.</li><li><span style="background-color: rgb(255, 255, 255);"><b><a href="http://www.php.net/">PHP</a> 5.3+: </b>PHP has to be 64bits aware.</span></li><li><span style="background-color: rgb(255, 255, 255);"><b>Database: <a href="http://www.postgresql.org/">PostgreSQL 8.3.9+</a> or <a href="http://www.mysql.com/">MySQL 5.1</a>+, SQLite 8.4.20:  </b>As of version 1.5, FileSender uses a PDO based database abstraction layer enabling use of multiple databases<b>. </b> PDO is available on most standard PHP 
installations.  Earlier versions of Postgres, MySQL or SQLite might work but 
haven't been tested by us.</span><br></li><li><span style="background-color: rgb(255, 255, 255);"><b><a href="http://rnd.feide.no/simplesamlphp/">SimpleSamlPHP</a> 1.9.2+: </b>earlier versions might work </span><b><br></b></li><li><b>Mail Transport Agent (MTA)</b>: Any decent MTA will do (Postfix, Exim, Sendmail). FileSender needs to be able to send out emails.</li></ul>
    
    
    
    
    
    
    <br>
    
    
    
    
