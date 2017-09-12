# Supported Debian and Ubuntu versions

* Debian Squeeze (oldstable/lts) and higher
* Ubuntu Lucid (10.04 LTS) and higher


# Should I pick stable, testing or unstable?

FileSender uses the Debian terminology for its distribution channels.  Use the [[Release_status_and_life_cycle| release status overview]] to select the FileSender release you want to install.


Installation instructions
==================

These instructions should be executed as 'root'.
To ensure that the installation packages are fetched from a trusted source the packages are PGP-signed. 
The correct PGP-key should be fetched over a trusted path (using SSL). To ensure a correct verification 
of the SSL-certificate the instructions below assume that the `ca-certificates` package is installed. If you get 
the `no valid OpenPGP data found.` message please do the following:

    apt-get install ca-certificates

Add the Filesender signing key to the APT PGP-keyring:

    wget -q https://filesender-dev.surfnet.nl/filesender.key -O- | apt-key add -

If you want to use version 1.6(.x) (labeled the **latest stable** release) of filesender run:

    echo "deb http://repository.filesender.org/debian stable main" > /etc/apt/sources.list.d/filesender.list


If you want to use the **upcoming stable** release of filesender run:

    echo "deb http://repository.filesender.org/debian testing main" > /etc/apt/sources.list.d/filesender.list

If you want to use the (nightly when appropriate) latest **beta/rc builds** of filesender run:

    echo "deb http://repository.filesender.org/debian unstable main" > /etc/apt/sources.list.d/filesender.list

If you want to use the previous (old) stable release of filesender run:

    echo "deb http://repository.filesender.org/debian oldstable main" > /etc/apt/sources.list.d/filesender.list

Now continue the installation process

    apt-get update
    apt-get install filesender


This will also install the simplesamlphp package and other dependencies like apache, php5 and postgresql. 

# Configuring Apache

A simple default configuration of apache is included in the filesender package and is located at `/etc/filesender/apache.conf`. You can copy this to `/etc/apache2/conf.d/filesender.conf` and adjust it to your needs.

    cp /etc/filesender/apache.conf /etc/apache2/conf.d/filesender.conf
    service apache2 reload

# Configuring Apache with SSL
The default FileSender configuration only works over SSL.  Make your Apache SSL-enabled with the following commands:

    a2ensite default-ssl
    a2enmod ssl
    service apache2 reload

This will give you a SSL-enabled Apache server with a self-signed SSL-certificate, allowing you to verify your FileSender installation works with HTML5 compatible browsers.  On your production service you will need to replace the self signed certificate with one issued by a CA recognised by popular browsers to ensure the Flash fall-back uploads method works for older browsers.  

*See also the [[FAQ#Q2| FAQ entry on SSL certificates]].
*To make your FileSender work over HTTP-only, change `$config['forceSSL']` in config.php to false.  This will constitute a security risk.
*See also [[Installation - Linux Source#Step 2 - Configure Apache2 with SSL|Configure Apache2 with SSL]] in the _Linux source installation guide_.

# Configuring PHP5
The most crucial settings are configured as part of the package installation.  There are some other settings you might want to consider.  See the [[Installation - Linux Source#Step 8 - Configure PHP5|PHP5 configuration part for a Linux Source Installation]].  Don't forget to reload your Apache server to activate your new PHP settings:

    service apache2 reload

# Configuring SimpleSAMLphp

For a quick start using the Feide OpenIdP Identity Provider copy the relevant sample configuration files to the right places.

For simplesamlphp version 1.6.x (default on Debian Squeeze):

    cp -p /usr/share/doc/simplesamlphp/examples/config-templates/authsources.php.gz /etc/simplesamlphp/
    cp -p /usr/share/doc/simplesamlphp/examples/metadata-templates/saml20-idp-remote.php.gz /etc/simplesamlphp/metadata/
    gunzip /etc/simplesamlphp/authsources.php.gz /etc/simplesamlphp/metadata/saml20-idp-remote.php.gz

For simplesamlphp version 1.9.x and later (default in the FileSender repository):

    cp -p /usr/share/doc/simplesamlphp/examples/metadata-templates/saml20-idp-remote.php /etc/simplesamlphp/metadata/

Edit `/etc/simplesamlphp/metadata/saml20-idp-remote.php` as per the instructions in that file.

To tailor your [SimpleSAMLphp](http://rnd.feide.no/simplesamlphp) installation to your local site please check its [installation and configuration documentation](http://rnd.feide.no/view/simplesamlphpdocs).

The default config.php in the current stable debian package (1.6.3) might need an additional setting:

           'attributenamemapdir'   => '/etc/simplesamlphp/attributemap/',

# Test your installation

* Go to https://<server>/simplesamlphp/ and check if everything is okay
* Go to https://<server>/filesender/ and check if everything is okay

# Support and Feedback

See [[Support and Mailinglists]] and [[Feature requests]].﻿
