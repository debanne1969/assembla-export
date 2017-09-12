Here you can find how to make a new release for filesender. Details of past and planned filesender releases are listed in the [[Release_Schedule|release schedule]]

Source packages
=============

*   First make sure that you really want to make a release. No files should be changed from this point, except for files containing version numbers and changelog.
*   Make a branch in the svn.
        $ svn cp http://subversion.assembla.com/svn/file_sender/filesender/trunk/ http://subversion.assembla.com/svn/file_sender/filesender/branch/filesender-<version>
*   Edit the files containing version numbers and changelogs. Commit this to the branch.
*   Do a clean export of the branch
        $ svn export http://subversion.assembla.com/svn/file_sender/filesender/branch/filesender-<version>
*   Create new release tarball and zipfile
        $ tar -zcvf filesender-<version>.tar.gz filesender-<version>
        $ zip -rv filesender-<version> filesender-<version>
*   Calculate SHA-1 hash
        $ sha1sum filesender-<version>.zip filesender-<version>.tar.gz
*   Create a wiki page describing the release.  Name of the wiki page is "release-<version number>".  The wiki page contains a release version number, a general description of the release, a description of the changes implemented (split in bug fixes and feature changes) and  the download links with the SHA-1 hashes.
*   Edit the [download overview page](/wiki/edit/file_sender/Download): depreciate the current release to the top entry under 'previous releases' and add the new release as current.
*   Edit the *Development Status* section on the [home page](/wiki/edit/file_sender/b516sOlY8r3PPQeJe5afGb) to reflect the current release number and release date.
*   Send the release announcement email as **plain text (NO HTML!)** using the following email template:

<PRE>

    To: filesender-announce@filesender.org
    Cc: filesender-dev@filesender.org
    Subject: FileSender <version number> released 

    Hi,

    FileSender <version number> is now available for download.

    Download page:
        http://www.assembla.com/wiki/show/file_sender/Beta-1-2


    CHANGES
     ========
     Features implemented:
     -


    Bugs fixed:
       -

    Cheers,

    <sign here>
</PRE>


Debian package
============
Requirements: a debian system

*   Make sure you have all debian packaging tools installed
        $ sudo apt-get install devscripts
*   To sign the packages you need your the filesender-dev key in your gnupg configuration.
*   Do a clean export of the tag
        $ svn export http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-<version>
*   inside the exported folder run
        $ dpkg-buildpackage
* Debian packages will be in the parent
* You can add the debian package to the stable repository by running
        $ reprepro -b /var/www/debian/ includedeb stable filesender_<version>_all.deb
* You can also add the source to the source stable repo:
        $ reprepro -b /var/www/debian/ includedsc stable *.dsc


RPM package
===========
* Make sure you have RPM installed:
        $ sudo apt-get install rpm
* Create the required directory structure:
        mkdir -p rpmbuild/{BUILD,RPMS,SOURCES,SPECS,SRPMS,TMP}
* To sign the packages you need to put this in ~/.rpmmacros
        %_signature gpg
        %_gpg_name  Filesender Development <filesender-dev@filesender.org>
Also make sure the filesender-dev private key is in your gnupg configuration
* Put the specs file from http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-<version> in rpmbuild/SPECS
* Put the source tarball, patches and extra files in rpmbuild/SOURCES. The required files are listed in the spec file and can be found in http://subversion.assembla.com/svn/file_sender/filesender/tags/filesender-<version>
* run rpmbuild -ba --sign rpmbuild/SPECS/*.spec
* If everything went well the RPM's will be in rpmbuild/RPMS
* to publish the RPM copy it to /var/www/rpm/stable
* Update the yum repository database:
    $ cd /var/www/rpm/stable
    $ createrepo -o . .


