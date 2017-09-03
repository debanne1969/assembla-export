This page describes the automated build system.

Location
======
The automated build system is located [here](http://filesender-dev.surfnet.nl/hudson/).

Description
========
The build system is a machine running [hudson](http://hudson-ci.org/) that will run a [build script](http://www.assembla.com/code/file_sender/subversion/nodes/filesender_builder) when triggered. Hudson can be triggered manually and automatically when somebody commits code to the filesender SVN tree. The filesender assembla installation is configured to trigged hudson.

The build script will:

* Do a checkout of the filesender trunk
* Compile the flash part with the flex command line compiler
* Make a tarball release
* From this tarball make a debian package
* Put these in the nightly build repository

The script is quite straightforward and can be run on most debian machines.

