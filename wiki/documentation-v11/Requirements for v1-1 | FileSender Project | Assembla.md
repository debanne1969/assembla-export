<p>The following outlines client and server requirements for the 1.1 release</p>

<p><strong>Client requirements for uploads of any size</strong></p>

<ul>
	<li><strong>Web browser with HTML5 FileAPI support.&nbsp;</strong>

	<ul>
		<li>Chrome and FireFox4+ are known to work.&nbsp;</li>
		<li><a href="http://caniuse.com/#feat=fileapi">Check here to monitor implementation progress</a> of the HTML5 FileAPI for all major browsers. In particular support for <a href="http://caniuse.com/#feat=filereader">FileReader API</a> and <a href="http://caniuse.com/#feat=bloburls">Blob URLs</a> needs to be light green (=supported) for a browser to support uploads larger then 2GB</li>
	</ul>
	</li>
	<li><strong><a href="http://get.adobe.com/flashplayer/">Flash Player</a> 10.x browser plugin</strong> - required for user interface</li>
</ul>

<p><strong>Client requirements for uploads up to 2GB using Flash and for all downloads</strong></p>

<ul>
	<li><strong>Web browser</strong> - modern release</li>
	<li><strong><a href="http://get.adobe.com/flashplayer/">Flash Player</a> 10.x browser plugin</strong> - required for user interface (for both up- and downloads).&nbsp; Used for uploads up to 2 GB if the browser does not support the HTML5 FileAPI</li>
</ul>

<p><strong>Server requirements</strong></p>

<ul>
	<li><strong>64-bit Linux</strong></li>
	<li><strong>Webserver</strong> - any webserver will do, however our documentation assumes <a href="http://www.apache.org/httpd/">Apache</a> 2+; <strong>ensure that the webserver is only reachable over HTTPS and the files directory is non-exec</strong> (see the <a href="/wiki/show/file_sender/Administrator_reference_manual" title="Administrator_reference_manual">Administrator_reference_manual</a> for more information, and the <a href="/wiki/show/file_sender/FAQ" title="FAQ">FAQ</a> for a quite relevant entry on why self signed certificates won&#39;t easily work)</li>
	<li><strong><a href="http://www.php.net/">PHP</a> 5.2.10+</strong> - PHP has to be 64bits aware</li>
	<li><strong><a href="http://www.postgresql.org/">PostgreSQL</a> 8.3.9+ database</strong> - we test on 8.3.9+, but earlier versions might work</li>
	<li><strong><a href="http://rnd.feide.no/simplesamlphp/">SimpleSamlPHP</a> 1.7.0+ </strong>- earlier versions also work (testing has been done with 1.6.x and 1.8.x).</li>
	<li><strong>Mail Transport Agent (MTA)</strong> - Any decent MTA will do (Postfix, Exim, Sendmail). FileSender needs to be able to send out emails.</li>
</ul>

