The following outlines client and server requirements for the 1.0 release:

__Client__

* __Web browser__ - modern, current release (browser limitations apply to Google Gears plugin)
* __[Flash Player](http://get.adobe.com/flashplayer/) 10.x browser plugin__ - required for user interface; used for uploads up to 2.0 GB, if Google Gears is not installed / enabled
* __[Google Gears](http://gears.google.com/download.html) browser plugin__ - required for uploading files > 2 GB __(currently not possible on Mac OSX and Linux)__ (for a list of browser versions supported by Google Gears see [http://gears.google.com/](http://gears.google.com/)); if a user attempts a large upload without Gears, they will be prompted to install Gears or that this is not possible, depending on their OS; used for all file uploads if installed and enabled. To install the plugin:
   * __for supported browsers / versions:__ [http://gears.google.com/download.html](http://gears.google.com/download.html)
   * __If using Firefox on Linux try:__ [http://gears64.org/](http://gears64.org/)
   * For Firefox on windows there is a Gears Add On that can be used if the normal installation isn't possible:  [https://addons.mozilla.org/en-US/firefox/addon/13492](https://addons.mozilla.org/en-US/firefox/addon/13492)

__ Server__

* __64-bit Linux__
* __Webserver__ - any webserver will do, however our documentation assumes [Apache](http://www.apache.org/httpd/) 2+; __ensure that the webserver is only reachable over HTTPS and the files directory is non-exec__ (see the [[Administrator_reference_manual]] for more information, and the [[FAQ]] for a quite relevant entry on why self signed certificates won't easily work)
* __[PHP](http://www.php.net/) 5.2.10+__ - PHP has to be 64bits aware
* __[PostgreSQL](http://www.postgresql.org) 8.3.9+ database__ - we test on 8.3.9+, but earlier versions might work
* __[SimpleSamlPHP](http://rnd.feide.no/simplesamlphp/) 1.5.1-1.6.3__ - Version 1.7.0 and and higher are supported as of FileSender 1.0.1 
* __Mail Transport Agent (MTA)__ - Any decent MTA will do (Postfix, Exim, Sendmail).  FileSender needs to be able to send out emails.

