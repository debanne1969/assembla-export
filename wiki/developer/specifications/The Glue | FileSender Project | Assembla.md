# Introduction

This page describes the interaction between the functional and technical design. For every action in the functional design is described what happens 'under the hood' and the called functions are listed.

Analyzing/reverse engineering the code is quite intensive, but many parts are quite straight forward. For this reason only the most important and complicated processes are described here; the uploading of a file with and without google gears, the downloading and the handling of vouchers. 

# List files
* user navigates to [[Functional design#My Files|myfiles]]
* _init()_ is loaded in  [[Technical design - flex#myfiles.mxml|myfiles.mxml]]
* flex requests file list from [[Technical design - PHP#fs_main.php|fs_main.php]], which will call _getUserFiles_ in [[Technical design - PHP#Functions.php|Functions.php]]
* _getUserFiles_ will extract uid from current session
* _getUserFiles_ will query database and return list of files belonging to uid

# New upload

## With gears

On the client:

* User navigates to  [[Functional design#New upload| New Upload]]
* Upload process is initialized by init() in [[Technical design - flex#upload_gears.mxml|upload_gears.mxml]]
* All callbacks are attached to function _returnStatus_ in [[Technical design - flex#upload_gears.mxml|upload_gears.mxml]]
* The upload button is pressed by the user
* _doGearsUpload()_ in [[Technical design - flex#upload_gears.mxml|upload_gears.mxml]] is called
* The email address is checked on validity
* Check number of emails recipients (defined in [[Technical design - PHP#config.php|config.php]]  )
* Check if AuP is selected, if not give alert
* Call  javasript function _upload(filevoucheruid)_ defined in [[Technical design - Javascript#fs_gears.js|fs_gears.js]]
* Split the file to upload in chunks, and call _sendChunk()_ with each chunk
* Start POST connection to [[Technical design - PHP#fs_gears_upload.php|fs_gears_upload.php]]  with arguments n = filename, b = start, vid = voucherid and total = total, put chunk in post
* callback function _returnStatus_ is called with progress information and screen is updated
* When complete callback is received the upload is complete, if an error
  occurs or the upload is canceled it is handled here also

On the server:

* receives POST connection to _fs_gears_upload.php_
* Receives file data and stores this in a temp file in location defined by _site_temp_filestore_ in [[Technical design - PHP#config.php|config.php]]
* TODO: can't find where the file is moved to the final location

## Without gears

On the client:

* User navigates to  [[Functional design#New upload| New Upload]]
* The upload button is pressed by the user
* _doupload()_ in [[Technical design - flex#upload_std.mxml|upload_std.mxml]] is called
* Check file size, if not 0 or too big (defined in [[Technical design - PHP#config.php|config.php]])
* Check number of emails recipients (defined in [[Technical design - PHP#config.php|config.php]])
* Get _SessionID_ of current user TODO: HOW
* Open the file
* Start POST connection to [[Technical design - PHP#fs_uploadit.php|fs_uploadit.php]] with argument _S_ set to the _SessionID_
* Stream the file to server
* The screen is displaying a progress bar which is updated by the _progressHandler_ callback function
* When the fileupload is completed the callback function _completeHandler_ is called by flash.
* [[Technical design - PHP#fs_main.php|fs_main.php]] is called with the _closeVoucher_ call, which indicates the file is completed. A list of JSON encoded properties is added to the request.
* This will display a confirmation or error, depending on if the upload was completed, canceled or an error occurred. 
* [[Technical design - PHP#fs_main.php|fs_main.php]] is called with the _insertFile_ call

on the server:

* In this case all interaction with the user is handled by [[Technical design - PHP#fs_main.php|fs_main.php]]
* clients initiates a POST connection to [[Technical design - PHP#fs_uploadit.php|fs_uploadit.php]]
* HTTPS connection is forced 
* authentication is checked
* The file is received, and moved to the designated file storage, by [[url:http://php.net/manual/en/function.move-uploaded-file.php|move_uploaded_file]]
* When the closeVoucher call at [[Technical design - PHP#fs_main.php|fs_main.php]] is received the database record for the file is updated and the filestatus is set to 'closed'
* When the insertFile call is received a database record for that file is inserted in the table 'files' and filled with the data supplied with a JSON encoded list of file properties
* The insertFile function will also sent an email to the recipients 


# File Download

* A user will press a download link in his [[Functional design#File Download|email program]]
* A browser opens and will open [[Technical design - PHP#fs_download.php|download.php]] and will extract voucher ID from arguments (vid)
* The file name is extracted from the vid
* The location of the file is verified, otherwise file not found error
* then _readfile_chunked()_ in _download.php_ is called, which will read the file in chunks
* The file content is returned to the client in chunks with [[url:http://php.net/manual/en/function.ob-start.php|ob_start()]] and [[url:http://php.net/manual/en/function.ob-flush.php|ob_flush()]]


# List vouchers
* user navigates to [[Functional design#Vouchers|Vouchers]]
* flex requests file list from [[Technical design - PHP#fs_main.php#fs_main.php]], which will call _getVouchers_ in [[Technical design - PHP#Functions.php#Functions.php]]
* _getVouchers_ will extract uid from current seesion
* _getVouchers_ will query database and return list of files belonging to uid with status set to 'voucher'


# Create voucher

* user navigates to [[Functional design#Vouchers|Vouchers]]
* user presses create voucher button
* _createVouchers()_ in [[Technical design - flex#vouchers.mxml|vouchers.mxml]] is called
* parameters are extracted and checked
* _saveVoucher()_ in  [[Technical design - flex#vouchers.mxml|vouchers.mxml]] is called with parameters
* [[Technical design - PHP#fs_main.php#fs_main.php]] with _insertFile_ call, which will create the voucher in the files table

# Use voucher

* A user will press a [[Functional design#Use Vouchers|voucher]] link in his email program
* A browser opens and will open filesender
* From there the sequence is identical to [[#New upload]]


