+++
title= "s3mon"
date= 2019-10-03T21:23:28+02:00
+++


If you are you making backups and storing them in an s3 bucket it could happen
that you are blindly trusting your backup mechanism but your s3 buckets may be
empty or with corrupted backups. 😲

The "backup" topic is huge, but these days, in many cases, it all ends in an s3
bucket.

**s3mon** aims to be a command-line tool that could help verify that data has
been stored in an s3 bucket no longer than a defined period of time in order
to ensure that backups have been stored properly and if not, notify by defined
alerts and channels in order to fix or improve the backup procedure. 🤔
