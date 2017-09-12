
      
      
      
      
      
      
      <p>This page outlines client and server requirements for FileSender<b> version 1.5</b></p>
<h4><b>Client requirements for uploads of any size<br></b></h4>
<ul><li><b>Web browser with HTML5 FileAPI support. </b></li><ul><li>Chrome, FireFox4+, IE 10 and Safari 6.0.1+ are known to work. </li><li><a href="http://caniuse.com/fileapi">Check here to monitor implementation progress</a> of the HTML5 FileAPI for all major browsers. In particular support for <a href="http://caniuse.com/filereader">FileReader API</a> and <a href="http://caniuse.com/bloburls">Blob URLs</a> needs to be light green (=supported) for a browser to support uploads larger then 2GB</li></ul></ul>
<h4><b>Client requirements for uploads up to 2GB using Flash<br></b></h4>
<ul><li><b>Web browser</b> - modern release</li><li><b><a href="http://get.adobe.com/flashplayer/">Flash Player</a> 10.x browser plugin</b> - required for the Flash upload component used with non-HTML5 browsers.  </li></ul><h4><b>Client requirements for downloads of all sizes</b></h4><ul><li> <b>Web browser</b> - modern release</li></ul><p> </p>
<h4><b> Server requirements<br></b></h4>
<ul><li><b>64-bit Linux</b></li><li><b>Webserver</b>: any webserver will do, however our documentation assumes <a href="http://www.apache.org/httpd/">Apache</a> 2+; <b>ensure that the webserver is only reachable over HTTPS and the files directory is non-exec</b> (see the <a href="https://www.assembla.com/wiki/show/file_sender/Administrator_reference_manual" title="Administrator_reference_manual">Administrator_reference_manual</a> for more information, and the <a href="https://www.assembla.com/wiki/show/file_sender/FAQ" title="FAQ">FAQ</a> for a still quite relevant entry on why self signed certificates will cause issues for uploads with the Flash component)</li><li><b><a href="http://www.php.net/">PHP</a> 5.2.10+: </b>PHP has to be 64bits aware.  On some platforms 5.3 might be required due to secondary dependencies. </li><li><b>Database: <a href="http://www.postgresql.org/">PostgreSQL 8.3.9+</a> or <a href="http://www.mysql.com/">MySQL 5.1</a>:  </b>FileSender 1.5 introduces a PDO based database abstraction layer enabling use of either 
PostgreSQL or MySQL<b>. </b> PDO is available on most standard PHP installations.  Earlier versions of Postgres or MySQL might work but haven't been tested by us.<br></li><li><b><a href="http://rnd.feide.no/simplesamlphp/">SimpleSamlPHP</a> 1.7.0+: </b>earlier versions might work <b><br></b></li><li><b>Mail Transport Agent (MTA)</b>: Any decent MTA will do (Postfix, Exim, Sendmail). FileSender needs to be able to send out emails.</li></ul>
    
    
    
    
    
    
    
