# Flex source files

## flex/src/filesender.mxml
__Description:__ default package for the filesender application

Public:

* __main_init()__initialize UI
* __resultInit(event:ResultEvent)__HTTPservice result from main_init
* __getVoucher()__all to javascript to get the current voucher id (vid) from the url if it exists
* __getFile()__HTTP service call for voucher data
* __resultLogon(event:ResultEvent)__Redirect for logon to SimpleSAML
* __aboutLink()__redirect to aboutLink
* __helpLink()__redirect to help link
* __resultFile(event:ResultEvent)__HTTPService result from voucher call
* __resultError(event:FaultEvent)__HTTPService has an error - this is a server error and PHP would log an error
* __checkVoucher(vid:String,gStatus:Boolean)__check if vid from javascript is returned
* __gearsActive(gears:Boolean)__setup gears UI
* __installGears()__redirect for gears install link
* __handleStateChange(event:StateChangeEvent)__whenever a state changes initialise the states UI  
* __uploadStopped()__when upload complete - update UI
* __uploadStarted()__when upload started - update UI
* __returnFiles(event:ResultEvent)__Not used - depricated
* __faultHandler(event:FaultEvent)__FAULT Handler for logging HTTP requests
* __logon()__HTTPRequest by logon button
* __noAuth(msg:String)__not authenticated - update UI and display relevant message
* __logoff(msg:String)__called by logoff button
* __newUpload()__recheck that user is still authenticated before allowing new upload
* __resultAuthAdmin(event:ResultEvent)__HTTPService - returns admin then update UI
* __resultAuth(event:ResultEvent)__HTTPService - returns authenticated then update UI
* __adminClick()__check auth before allowing admin
* __fatalError(error:String)__fatal error display function
* __correctLinux(e:Event)__corrects keyboard characters entered when using linux
* __logProcess(message:String)__log client process
* __resultlog(event:ResultEvent)__HTTPRequest result from log

## flex/src/org/ricoshae/core/ff_fix.as

__Description:__ call to javascript DoneLoading() to clear the continuous loading status bar. FireFox issue only

## flex/src/org/ricoshae/core/FS_Validation.as
__Description:__ Class FS_Validation with a isValid Email method for validating email adresses. 

## Directory flex/src/org/ricoshae

### File admin.mxml

Public:

* __init()__init UI
* __return_error(event:FaultEvent)__HTTPService return error
* __returnFiles(event:ResultEvent)__HTTPService return files table
* __returnLogs(event:ResultEvent)__HTTPService return logs table
* __returnDriveSpace(event:ResultEvent)__HTTPService drive space
* __check_functions_result(event:ResultEvent)__depricated
* __convertBytes(bytes:Number)__display filesize in datagrid
* __convertDGToHTMLTable(dg:DataGrid)__excel export function
* __readablizeBytes(bytes:Number)__convert filesize display
* __loadDGInExcel(dg:DataGrid)__display datagrid in php

private:

* __filesizeFunc(item:Object, column:DataGridColumn)__display logfile size in custom cell object
* __filesizeFuncFiles(item:Object, column:DataGridColumn)__display file filesize in custom cell object
* __filterUpload(item:Object)__filters for each datagrid in admin
* __filterDownload(item:Object)__filters for each datagrid in admin
* __filterError(item:Object)__filters for each datagrid in admin
* __filterVoucher(item:Object)__filters for each datagrid in admin
* __filterActive(item:Object)__filters for each datagrid in admin
* __dateFunc( item:Object, column:DataGridColumn)__format date in datagrid

### download_std.mxml
Flex - download file using browsers download
This code still includes deprecated flash download code left in in-case there is a need to return to flash download 
Public:

* __init()__init UI
* __cancelDownload()__cancel download - flash *deprecated*
* __fileDownloadComplete(event:Event)__download complete - flash *deprecated*
* __returnMail(event:ResultEvent)__HTTPService return complete - flash *deprecated*
* __return_error(event:FaultEvent)__error event - flash *deprecated*
* __readablizeBytes(bytes:Number)__format file size display
* __testBrowserDownload()__file browser download - CURRENT
* __returnBrowser(event:ResultEvent)__HTTPService return from sendBrowser - flash *deprecated*

private:

* __doEvent(evt:Event)__progress event - flash *deprecated*
* __doProgress(event:ProgressEvent)__download progress - flash *deprecated*
* __downloadFile()__download file - flash *deprecated*

### helppop.mxml

Public:

* __init()__initialize UI

private:

* __canceldata()__close pop up

### myfiles.mxml

Public:

* __init()__initialise UI	
* __completeVoucher(event:ResultEvent)__deprecated - remove after confirm not used elsewhere
* __returnVouchers(event:ResultEvent)__return users files
* __returnInsertedVoucher(event:ResultEvent)__HTTPService - return inserted voucher
* __returnMail(event:ResultEvent)__HTTPService - return email sent
* __return_error(event:FaultEvent)__HTTPService - error accessing service
* __functionNameBtn()__confirm delete a file
* __OK_DeleteVoucher(event:CloseEvent)__file ok to delete
* __functionResendBtn()__re-send confirmation
* __OK_ResendVoucher(event:CloseEvent)__HTTPService - re-send 
* __returnResendVoucher(event:ResultEvent)__HTTPService - return from re-send
* __functionAddEmail()__call to pop-up add new recipient
* __deletedVoucher(event:ResultEvent)__HTTPService - return from delete voucher
* __saveVoucher(mailTo:String,VoucherUID:String)__HTTPService - save new file
*__convertBytes(bytes:Number)__convert bytes for filesize display
*__fromLabel_Func(item:Object, column:DataGridColumn)__change 'from' label in datagrid if current user to display 'Me'

Private:
*__filesizeFunc(item:Object, column:DataGridColumn)__Display file size - datagrid
*__dateFunc( item:Object, column:DataGridColumn)__display correct date in datagrid



### newEmail.mxml

Public:

* __init()__init UI
* __readablizeBytes(bytes:Number)__format filesize display
* __addNew()__add new recipient
* __fileSaved(event:ResultEvent)__HTTPService returned save
* __fileError(event:FaultEvent)__HTTPService Error

private:

* __canceldata()__ close pop up

### upload_gears.mxml

Public:

* __init()__initialise all arrays and set button defaults 
* __startuploadgears()__call externalInterface to allow gears to select file
* __doGearsUpload()__start the gears upload process
* __returnStatus(sInfo:String,sType:String)__whenever external interface is called - all return results come back through this function
* __filemoved(event:ResultEvent)__HTTPService return file moved
* __fileSizeReturn(event:ResultEvent)__HTTPService file size returned from checking temp folder
* __cancelUpload()__upload cancelled confirmation
* __OK_CancelUpload(event:CloseEvent)__continue cancelling upload
* __fileComplete()__file upload complete
* __fileSaved(event:ResultEvent)__HTTPService returns saved file
* __fileError(event:FaultEvent)__HTTPService error
* __readablizeBytes(bytes:Number)__Format file size

private:

* __fnCheckString(str:String)__show upload status 
* __fnCheckExtension(str:String)__check file extension
* __updateSpeed( e:TimerEvent )__update speed display

### upload_std.mxml

Public:

* __init()__init UI
* __keepaliveHandler(event:TimerEvent)__sends request to keep alive to log - if logging is off then there is no message recorded 
* __vaildateToEmail()__validate email address
* __doupload()__start the upload process
* __openHandler(event:Event)__handler for file open
* __progressHandler(event:ProgressEvent)__dispatched during file upload
* __completeHandler(event:Event)__Following dispatched when the file has been given to the server script
* __uploadCompleteHandler(event:DataEvent)__Following dispatched when a file upload has completed
* __uploadit()__setup file reference handler
* __fileCompleted()__completed file uploaded
* __fileSaved(event:ResultEvent)__HTTPService return from saving file data
* __fileError(event:FaultEvent)__FileReference error
* __httpErrorHandler(event:HTTPStatusEvent)__FileReference HTTP error
* __httpIOErrorHandler(event:IOErrorEvent)__FileReference IO error
* __httpSecurityErrorHandler(event:SecurityErrorEvent)__FileReference security error
* __selectHandler(event:Event)__FileReference select handler
* __cancelUpload()__Cancel Flash Upload
* __readablizeBytes(bytes:Number)__display bytes correctly

private:

* __updateSpeed( e:TimerEvent )__update upload speed
* __fnCheckString(str:String)__check invalid characters
* __fnCheckExtension(str:String)__check invalid extensions

### vouchers.mxml

Public:

* __init()__initialise vouchers UI
* __completeVoucher(event:ResultEvent)__HTTPService return from creating a voucher
* __returnVouchers(event:ResultEvent)__HTTPService return with all current users vouchers
* __returnInsertedVoucher(event:ResultEvent)__HTTPService return completed voucher
* __returnMail(event:ResultEvent)__HTTPService return email sent ok
* __return_error(event:FaultEvent)__HTTPService return error if unable to contact server
* __createVouchers()__create voucher	
* __functionNameBtn()__Delete voucher confirmation
* __OK_DeleteVoucher(event:CloseEvent)__delete voucher return confirmation
* __deletedVoucher(event:ResultEvent)__HTTPServer return voucher deleted
* __saveVoucher(mailTo:String,VoucherUID:String)__save voucher

private:

* __dateFunc( item:Object, column:DataGridColumn)__format date in datagrid

# 3th party libraries

## as3corelib

__Description__: An ActionScript 3 Library that contains a number of classes and utilities for working with ActionScript? 3. These include classes for MD5 and SHA 1 hashing, Image encoders, and JSON serialization as well as general String, Number and Date APIs.

__URL__: [[url:https://github.com/mikechambers/as3corelib/]]

__License__: BSD

Used modules:
* __flex/libs/as3corelib.swc__ The as3corelib component library used for inclusion to the flex project during compilation.

* __flex/src/com/adobe/crypto/__ Library for performing MD5 hashing

* __flex/src/com/adobe/serialization/json/__ Library for performing JSON serialization

* __flex/src/com/adobe/utils/IntUtil.as__ Library contains reusable methods for operations pertaining to int values.

# Binary flash files

## www/lib/swf/playerProductInstall.swf
__Description__: Flash file used for wrapping a swf. It abstracts implementation details about Plugin detection, embedding, and other features so that you only need to call a single method to embed your SWF file.

__More info__: [[url:http://help.adobe.com/en_US/flex/using/WS2db454920e96a9e51e63e3d11c0bf69084-7b86.html]]

## www/lib/swf/filesender.swf

__Description__: The binary file, which is the result of the compilation of the flex code. This file is transferred to the client and run client-side.

## flex/html-template/filesender.swf

__Description__: Deprecated - removed from SVN

