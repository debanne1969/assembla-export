# Actors
There are 4 types of entities that can influence the working of Filesender:

* An Authenticated user. He or she can upload, remove and share files. Also he can create and remove vouchers.
* A download user. He or she can download a file after receiving an email issued by an authenticated user.
* A voucher user. He or she can create one single download and share it. A voucher user can do this after receiving an invitation issued by an authenticated user. 
* A cleanup daemon that removes expired downloads and vouchers. This daemon is time triggered.


# Action sequences

## Authentication
### Login
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/login.png "")

A user can be come an authenticated user after login at the login screen.

Action:

 * Press login - the user will be redirected to [[#Identity selection]]


### Identity selection
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/identity.png "")

Here a user can specify the authenticated method. The options depends on the server configuration.

Action:

 * choose an authentication backend


## Authenticated menu

The menu is available to an authenticated user at all time. 

Actions:

 * [[#New upload]] - will initial the new upload process
 * [[#Vouchers]] - will list the active vouchers
 * [[#My files]] - will list the active files
 * Help - will redirect the user to a custom help page
 * About - will redirect the user to a custom about page
 * [[#Logout]] - ends the authenticated user session

## Logout
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/logout.png "")

When an authenticated user presses the logout button, the session is ended and the user is prompted with a confirmation.

Actions:

 * None

## New upload
### step 1 
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/upload_fill.png "")

Here a user can upload a file to the server and specify the email addresses of people who are allowed to download this file. Optionally an email subject and body can be specified. The file can be downloaded until the specified expire date. 

Fields:

* Recipient email address(es)
* Email subject (optional)
* Email body (optional)
* Expire date
* File upload

Action:

* Send - will upload the file to the server. The user is redirected to [[#step 2 uploading]].


### step 2 uploading
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/uploading.png "")

When the Send button in step 1 is pressed the user is presented a 'uploading' screen', until the upload process is complete. After the user is redirected to [[#step 3 upload finished]].

Actions:

* None

### step 3 upload finished
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/upload_complete.png "")

When the upload is complete the user is presented with a 'upload completed' dialog. This is the final step in the new upload process. The server will send a email with a download URL to the specified addresses. 

Actions:

* None

## File Download
### step 1 - email
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/file_email.png "")

When a file is shared with a guest he will receive an email. This email contains the body and subject specified by the file uploader. Also it contains a URL which can be sued to download the file.

Actions:

* Press download URL, this will open [[#step 2 - Download screen]]

### step 2 - Download screen
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/file_download.png "")

The user is prompted with the file properties.

The properties are:

* Sender email
* Receiver email
* Email subject (if any)
* Email body (if any)
* File Name
* File Size
* Expire Date

Actions:

* Press 'start download'. The user is prompted with the browser download dialog, and continue to [[#Step 3 - file download]].

### Step 3 - file download
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/file_downloading.png "")

The user is downloading the file. The user can end the session, no actions are left.

Actions:

* None

## Vouchers
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/vouchers_list.png "")

Here an authenticated user can create and remove vouchers. Vouchers can be send to an email address.

parameters:

* 'send voucher to:' required to create a voucher

Actions:

* Press 'send voucher' which will give the [[#Create voucher]] dialog.
* Press the delete voucher linked to a voucher (if any), which will give the [[#delete voucher]] dialog.

## Create voucher
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/voucher_sent.png "")

When an email address is specified and 'send voucher' is pressed the user is prompted with a notification.

Actions:

* OK button, will return user to [[#Vouchers]].

## Use voucher
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/voucher_email.png "")

When a voucher is created by an authenticated user an email is sent to the specified user. 

Actions:
 
* Open URL in email. This will bring the user to a filesender installation and he can upload a file. This is the same action sequence as [[#New upload]]'.

## delete voucher
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/voucher_delete.png "")

When a user presses the delete button linked to a voucher he is prompted with a confirmation dialog.

Action:

* confirm deletion. After the user is returned to [[#vouchers]].



## My files
![List of files](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/myfiles.png "List of files")

Here an authenticated user can see his or her uploaded files. Also he can remove one or more of them.

action:

* Delete a uploaded file, the user is prompted with a [[#delete file]] dialog.

## delete file
![](http://subversion.assembla.com/svn/file_sender/documentation/screenshots/file_delete_confirm.png "")

When an authenticated user presses the delete button linked to a uploade file, the user is prompted with a confirmation dialog.

action:

* Confirm, will delete the file and the user is returned to [[#My files]].
* cancel, don't delete the file and return to [[#My files]].

