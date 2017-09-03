# Directory classes
__Description:__ Directory containing PHP classes

## _includes.php
__Description:__  Includes all other includes and sets _$filesenderbase_ to the location of the current file.

## AuthSaml.php
__Description:__ Contains the AuthSaml class

### Class AuthSaml
__Description:__ Handles the  SAML authentication

methods:

* public:
    * __getInstance()__ returns the singleton instance
    * __authIsAdmin()__ checks if a user is SAML authenticated and is administrator. returns true/false used by flex to display admin features
    * __sAuth()__ returns SAML authenticated user information as json array
    * __logonURL()__ returns logon URL from SAML and returns string for flex
    * __logoffURL()__ returns logon OFF URL from SAML and returns string  for flex
    * __isAuth()__  checks SAML for authenticated user: returns true/false

## AuthVoucher.php
__Description:__: Contains the AuthVoucher class

### Class AuthVoucher

__Description:__ voucher related functions

methods:

* public:
    * __getInstance()__ returns the singleton instance
    * __aVoucher()__ - check if a voucher exists and returns true/false
    * __validVoucher()__ - check if a voucher exists and is available and returns found/notfound/invalid/none (for flex application)
    * __getVoucher()__ - returns voucher as json array

## DB.php

__Description:__ functions for database connection. Uses config.php settings for database access. 

### Class DbException
__extends:__ extends Exception

__Description:__ Exception raised in case of database problem

### Class DbConnectException
__extends:__ DbException

__Description:__ Exception raised in case of connect problem

### Class DB
__Description:__ Represents database connection

methods:

* public
    * __getInstance()__  returns the singleton instance
    * __connect()__ connect to the database. returns reference to postgresql connection. Raises DBConnectException in case of connect problem
    * __fquery()__ executes query and arguments (???)
    * __query(_$query_)__ check connection and call __DoQuery__ with _$query_
    * __buildQuery()__ Combine supplied arguments in one query
    * __doQuery($handle, $query)__ executes the SQL query in _$query_

properties:

* _$connection_ reference to postgresql connection

## DB_Input_Checks.php
__Description:__ Contains class DB_Input_checks and some functions

* __ip2long6(_$ipv6_)__ converts IPv6 address to a long number
* __long2ip6(_$ipv6long_)__ converts long number to IPv6 address
* __checkdateformat(_$date_, _$dateformat_)__ returns date, TODO: FUNCTION NOT FINISHED

### Class DB_Input_Checks
__Description:__ Takes care of the input checks required in sql queries. Each check return the value or the report the error in errorReporting. All the Vars will go through a mysqlEscape function, in this function different ways of general string filtering can be used.

methods:

* public:
    * __getInstance()__   returns the singleton instance
    * __checkEmail(_$email_)__ check if an email address if valid
    * __checkURL(_$url_)__ check if a URL is valid
    * __checkIp(_$ip_)__ returns sanitized IPv4 address 
    * __checkIp6(_$ip_)__ returns sanitized IPv6 address
    * __errorReport(_$errorMessage_)__ empty functions used for error reporting, TODO: FUNCTION NOT FINISHED

## EN_AU.php
__Description:__ Contains class EN_AU

### Class EN_AU
__Description:__  EN_AU language file for flex application. Contains a mapping from strings used internally in the code to Australian English.

methods:

* public:
    * __language()__ returns the _$lang_ array

properties:

* _$lang_ dictionary with mapping from string code used in source and real language


## Functions.php
__Description:__ contains the class _Functions_ and some functions

* __formatBytes(_$bytes_, _$precision=2_)__ Format bytes into readbable text format
* __getGUID()__  Create Unique ID for vouchers
* __sanitizeFilename(_$filename_)__ Replace illegal chars with _ character in supplied filenames
* __ensureSaneFileUid(_$fileuid_)__ Error if fileUid doesn't look sane

### Class Functions
__Description:__

methods:

* public:
    *  __construct()__ Constructor
    *  __getInstance()__ returns the singleton instance
    *  __getStats()__  Return Basic Database Statistics e.g. Up xx Gb (files xx) | Down xx Gb (files xx)
    *  __getSplash()__ Get Splash Screen text for all users
    *  __getConfig()__ Retrun Specific config fields required by flex as JSON array
    *  __getVouchers()__  Get Voucher for a specified user based on eduPersonTargetedID
    *  __getUserFiles()__ Get Files for a specified user based on eduPersonTargetedID
    *  __adminLogs()__ Return logs if users is admin
    *  __adminFiles()__  Return Files if users is admin
    *  __getFile(_$dataitem_)__ Return file information based on filervoucheruid
    *  __getVoucher(_$vid)__ Return voucher information based on filervoucheruid
    *  __downloadedFile()__ Email and log when a file is downloaded
    *  __insertFile()__  Insert new file or voucher
    *  __updateFile()__  Update file or voucher
    *  __deleteVoucher(_$fileid_)__ Delete a voucher specified by _$fileid_
    *  __closeVoucher(_$fileid_)__ Close a voucher specified by _$fileid_
    *  __deleteFile(_$fileid_)__ Delete a voucher specified by _$fileid_
    *  __getFileSize(_$filename_)__ return file size of file specified by _$filename_
    *  __driveSpace()__ Returns the total number of bytes as a float or FALSE on failure 
    *  __moveFile()__ move file from tmp directory to live directory and rename with Unique ID

properties:

* private:
    * _$saveLog_ reference the [[#Class Log|Log instance]]
    * _$db_ reference the [[#Class DB|DB instance]]
    * _$CFG_ reference the [[#Class Config|Config instance]]
    * _$sendmail_ reference to the [[#Class Mail|Mail instance]]
    * _$authsaml_ reference to the [[#Class AuthSaml|AuthSaml instance]]
    * _$authvoucher_ reference to the [[#Class AuthVoucher|AuthVoucher instance]]
	* _$returnFields_  These fields are returned without fileUID to stop unauthorized users accessing the fileUID

## Log.php
__Description:__ Contains the Class Log

### Class Log
__Description:__ Logging functions, used for logging to a log storage

methods:

* public:
    * __getInstance()__ Returns the singleton instance
    * __saveLog(_$dataitem_, _$logType_, _$message_)__ Save Log Data
    * __logProcess(_$client_, _$message_)__ logfile for individual client specific logging. calls to this function are form glex/flash if client specific logging is on

## Mail.php
__Description:__  Contains the Class Mail

### Class Mail
__Description:__ Mail functions, used for sending mail

methods:

* public:

    * __getInstance()__ Returns the singleton instance
    * __sendemail(_$mailobject_, _$template_)__  Send mail
    * __sendemailAdmin(_$message_)__  Send admin mail messages

# Directory includes

## EnsureHTTPS.php
__Description:__ Destroy session when used HTTP (not HTTPS) and ForceSSL is set in config

## ErrorHandler.php
__Description:__  Error handling functions

functions:

* __customException(_$exception_)__ Custom exception
* __customError(_$errno_, _$errstr_, _$errfile_, _$errline_)__ Custom error
* __logEntry(_$message_)__ general log function for flex logging

## UTF8.php
__Description:__ UTF-8/International Character handling related functions

functions:

* __detectLatin1(_$string_)__ Simple check for ISO-8859-1
* __detectUTF8(_$string_)__ Simple check for UTF-8
* __detect_char_encoding(_$string_)__ detect the required charset MIME encoding for $string, only distinguishes between US-ASCII, ISO-8859-1 and UTF-8
* __mime_qp_encode_header_value(_$string_,_$charsetin_,_$charsetout_,_$crlf_)__ QP header encoding using iconv_mime_encode
* __utf8tohtml(_$utf8_, _$encodeTags_)__ converts a UTF8-string into HTML entities

# Directory config

## config.php
__Description:__ Contains the Class Config and let_to_num function

functions:

* let_to_num(_$v_) - transforms the php.ini notation for numbers (like '2M') to an integer (2*1024*1024 in this case)

### Class Config
__Description:__ Empty class containing the loadConfig method

methods:

* public:
    * __getInstance()__ Returns the singleton instance
    * __loadConfig()__ return dictionary with all configuration variables


# Directory cron

## cron.php
__Description:__  This script should be called by the cron daemon on a regular interval to remove files that have expired and close the expired files in the database 

functions:

 * __cleanUp()__ Clean up missing file, removes out of date files and vouchers. return true if successful, false in case of error
 * __logProcess(_$client_, _$message_)__ ??

# Directory www
## about.php

__Description:__ Displays a custom About page

## createxls.php
__Description:__  return payload of htmltable POST variable into a excel document

## fs_gears_upload.php
__Description:__ Upload using gears. Data is sent in chunks from google gears and appended to the file in the temporary folder

## fs_main.php
__Description:__ Flex calls this for all requests except the actual file uploading.

_$_POST['call']_ defines the functions trigger from this call flex uses HTTPService calls to talk to php and returns results as text or json text
e.g. <mx:HTTPService id="init_main" url="../fs_main.php{URLvid}" useProxy="false" method="POST" resultFormat="text" result="resultInit(event)" fault="resultError(event)"/>

TODO: expand


## fs_uploadit.php
__Description:__ Upload file from flex application and move into site_filestore folder. returns string: moveOk, moveError,invalidAuth back to flex

## help.php
__Description:__ Displays custom help page

## index.php
__Description:__ Entry page, checking for flash, loads images and flex app.

## invalidvoucher.php
__Description:__ Displays invalid voucher page

## displayimage.php
__Description:__ Will call function __displayimage()__ (inside)

Functions:

*  __displayimage(_$customimage_, _$defaultimage_)__  will read and print the contents of _$customimage_ if it exists, otherwise _$defaultimage_

## download.php
__Description:__  download using PHP from a non web accessible folder. File is specified by a voucher ID (VID). 

## logout.php
__Description:__ Displays a logout html page. Doesn't do the logout itself.

## vouchererror.php
__Description:__ Displays a invalid voucher page

