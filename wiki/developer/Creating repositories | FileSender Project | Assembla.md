Debian repository
=============
Here you can find how to set up and maintain a debian repository. For more info checkout [the manual](http://alioth.debian.org/scm/viewvc.php/*checkout*/mirrorer/docs/manual.html?revision=HEAD&root=mirrorer).

* first of all, make sure reprepro is installed:
        $ sudo apt-get install reprepro

* Choose a location, for example /var/www/debian
        $ export DEBREPO="/var/www/debian"

* Make sure you have the filesender-dev private key in your gnupg keychain

* Create a file ${DEBREPO}/conf/distributions with this content:

        Codename: filesender
        SignWith: F0226697
        Suite: stable
        Components: main
        Architectures: amd64 i386 source
        Origin: http://www.filesender.org
        Description: The official stable filesender Debian repository
       
        Codename: filesender-dev
        SignWith: F0226697
        Suite: unstable
        Components: main
        Architectures: amd64 i386 source
        Origin: http://www.filesender.org
        Description: The official unstable filesender Debian repository

* Create the repository:
        $ reprepro -b $DEBREPO createsymlinks

* Now you can add packages:
        $ reprepro -b $DEBREPO includedeb stable mypackage.deb

* You can also add source packages, issue the reprepro man page for more info

Yum RPM repository
================
This can be done with fedora/redhat/centos, but also with debian/ubuntu. 

* For debian, make sure the createrepo package is installed:
        $ sudo apt-get install createrepo
* Choose a place for the yum repository, for example /var/www/rpm
        $ export RPMREPO="/var/www/rpm"
* Copy the RPM's that you want to distribute to this directory
* Build the required metafiles:
        $ cd ${RPMREPO}
        $ createrepo -o . .
* Now people can access the repo, but they need to know how. Create a repo file and put this somewhere public so people can put it in /etc/yum.repo.d/
        [filesender-noarch]
        name=filesender-noarch
        baseurl=http://filesender-dev.surfnet.nl/rpm
        gpgkey=http://filesender-dev.surfnet.nl/filesender.armor
        enabled=1
        gpgcheck=1
* Don't forget to make the filesender-dev private key also online, so people can verify the package. It needs to be in ascii armor format:
        $ gnupg --export --armor filesender-dev@filesender.org



