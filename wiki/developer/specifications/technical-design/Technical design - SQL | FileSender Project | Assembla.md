# SQL

## scripts/filesender_db.sql

__Description:__ This file is used to populate a database.

The script creates 2 tables, _files_ and _logs_. _files_ is used to store information about uploaded files. The _logs_ table is used for storing all events.

There are also 2 sequences, _log_id_seq_ and _download_id_seq_. _download_id_seq_ is unused, _log_id_seq_ is used for the auto incrementation of a new _logid_. This can be replaced by the 'serial' field in future versions.

![database design](http://subversion.assembla.com/svn/file_sender/documentation/database.png)
