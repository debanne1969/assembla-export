Installation instructions
=========================

FileSender installation instructions are available in the [[url:/wiki/show/file_sender/Documentation_v1-1|Documentation]] section.

Be sure to read the parts about configuring PostgreSQL, PHP, Apache,
SimpleSAMLphp and cron to get up and running.

Upgrading to 1.1.1 RELEASE
==========================

Version 1.1.1 is a maintenance and bugfix release (see CHANGELOG.txt for
details about the fixes). 

To prevent problems with files sent to mutiple recipients exceeding (when combined) 250
characters you should manually alter the relevant column type in the database with:

       #sudo -u postgres psql filesender
         ALTER TABLE files ALTER fileto TYPE text;
         ALTER TABLE logs ALTER logto TYPE text;
         \q

As usual it is recommended to make a backup of your current installation
before upgrading, especially if you have made local modifications to the
installed version.

Upgrading to 1.1 RELEASE
==========================

As usual it is recommended to make a backup of your current installation
before upgrading, especially if you have made local modifications to the
installed version.

Although 1.1 offers a major change in client side user functionality
(replacing Gears with HTML5) on the server side it contains only a few
minor bugfixes (see CHANGELOG.txt for details about the fixes). When
upgrading from a previous version please adjust the 'gearsURL' 
configuration setting:

  $config['gearsURL'] = 'http://html5test.com/';

When upgrading from a previous version it is also recommended to adjust
the column sizes for 'fileauthuseruid' and (if not already done)
'fileip6address' in the 'files' database table:

	#sudo -u postgres psql filesender
	ALTER TABLE files ALTER fileauthuseruid TYPE character varying(500);
	ALTER TABLE files ALTER fileip6address TYPE character varying(45);
	\q

Upgrading to 1.0.1 RELEASE
==========================

Version 1.0.1 is mainly a bugfix release (see CHANGELOG.txt for
details about the fixes). When using IPv6 it is recommended to
adjust the 'files' database table:

	#sudo -u postgres psql filesender
	ALTER TABLE files ALTER fileip6address TYPE character varying(45);
	\q

As usual it is recommended to make a backup of your current installation
before upgrading, especially if you have made local modifications to the
installed version.

Upgrading from previous (beta) versions
=======================================

Please read the following notes before upgrading from a previous beta
version to 1.0.x.

IMPORTANT: Upgrading from versions older then Beta-0.1.17
=========================================================

* A new naming scheme to store files on the server was introduced in
Beta-0.1.17. Please run 

    php <filesenderbase>/scripts/convert-filenames.php

    *after* upgrading to Beta 0.1.17 or newer. If you need to downgrade
to a previous version run

    php <filesenderbase>/scripts/convert-filenames.php revert

    *before* downgrading.

    YOU ONLY NEED TO DO THIS ONCE. If you upgrade from for example Beta-0.1.18 to
RELEASE-1.0 you do not need to repeat this step. So only run the script when
upgrading from Beta-0.1.16 or older.

* As of version Beta-0.1.17 the expiration of files and vouchers is handled
by a script to be called by cron. Please see the installation instructions at
https://www.assembla.com/wiki/show/file_sender/Documentation on how to
install such a cron job.


IMPORTANT: Upgrading from previous betas in general
===================================================

It is strongly recommended that you do a fresh install after making a
backup copy of your previous install and carefully re-apply any local
changes you have made in previous versions.

The following notes describe the files most likely to contain local changes:

Configuration
=============

  - config/config.php

In the various beta cycles several new and required settings have
been added to the config.php that might not be present in your current
configuration. Also the default permissions of the config.php have been made more restrictive. 

IMPORTANT: make the config/config.php group readable by your web daemon user. See the [[Installation - Linux Source#install the filesender package|Install the filesender package]] section of the Installation guide.

IMPORTANT: When upgrading please start with a fresh configuration file
and take the time to go through all configuration directives to make
sure all is as it should be. Merging new entries into your old config.php is
discouraged.

Customisation
=============

Site specific information will be in:

  - www/about.php
  - www/help.php

Note that the default www/help.php now contains a list of settings about for
example maximum sizes and expiry time which is automatically generated from
the settings in the configuration file. You may want to integrate that
information with your custom help info.

You may have put a custom logo/banner in:

  - www/banner.png

As of version Beta-0.1.17 you can put a site specific banner in

  - config/banner.png

If this file is available FileSender will use that one instead of the
default banner in www/banner.png.

Please refer to the section on Customisation in the [[Administrator_reference_manual]]
for instructions on how to customise your installation.

Performance
===========

  - www/js/fs_gears.js

You may have changed the chunksize used in the gears upload. This value is
found in www/js/fs_gears.js in the variable CHUNK_BYTES that has a default
value of 2000000 (2M).

Support and Feedback
==================

See [[Support and Mailinglists]] and [[Feature requests]].﻿
