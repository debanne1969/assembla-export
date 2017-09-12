#Release Version 2.0-alpha1

<span style="background-color:orange">This document is a work in progress.  While this announcement
remains on top we have not yet formally issued an alpha release.</style>

__Release date:  x 2016__ 

#Distribution
Release 2.0-alpha1 is available via SVN as per our Alpha release policy. (link!!)

The 2.0-alpha1 branche is:
https://www.assembla.com/spaces/file_sender/subversion/source/HEAD/filesender/branches/filesender-2.0

Code in this branche is considered to be 2.0-alpha1 as of revision X


#Installation
Documentation is available at Documentation v2-0. 


#Upgrade Notes
Version 2.0 breaks compatibility with version 1.x.  We recommend to There are currently no detailed upgrade
notes for version 2.0 available.

#Security audits
The 2.0-alpha1 code has been put through two separate external code security audits 
between January and April 2015:
* One initiated by the project and executed by Pine Security
* One initiated by French NREN RENATER which included a review of their operational environment.

Few issues surfaced and they have where relevant been addressed.  

#Major changes since release 1.6

Version 2.0 is a new baseline release.  Much of the code base was rewritten, 
a new database design adopted, many configuration directives have been added and existing
directives changed. Please note version 2.0 does not contain the crypto functionality
found in version 1.7-beta1.  We expect to put this on the roadmap after the 2.0 production
release.

Many new features have been added. Check the Features page for details of the draft
feature list for version 2.0. 

A summary:

* Added Multi-file transfer support with drag & drop file selection
* Added Fine-grained email receipt control 
* Added Per transfer audit report
* Removed Flash dependency for uploads with legcy browsers without HTML5 FileAPI support.
 The per-file limit with legacy browsers is 2GB.
* Improved TeraSender upload module
* Added a RESTfull webservice API
* Reduced the privacy footprint
* Added Shibboleth authentication library support
* New database design
* Database initialisation scripts for MySQL and PostgreSQL

#Known issues
* Release 2.0-alpha1 has not undergone any structured client-side workflow
testing!
* While nearly all configuration directives have been documented and put through basic
testing, the administration
manual detailing how to for example implement email bounce handling or tweaking the layout
is largely absent.
* The TeraSender upload module works and has been put through some basic tests including
a number of uploads of 200 GB.  We are not entirely satisfied yet with its stability and
you may encounter issues.
* We are not aware of any major issues.  Visit the open ticket list for an overview
of currently open issues.

#Translations

# Testing


#Support and Feedback
See Support and Mailinglists and Feature requests.
