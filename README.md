#<a name="top">PFRESTORE - A Puppet File Restore Utility</a>
---

A simple perl script (yes, there are a few of us graybeards that still find perl very useful) that provides a menu of files that Puppet has replaced on a given system.

Requires:

1) POSIX 'strftime';

2) File::Copy qw(copy);

3) Switch;



**<a name="pfrestore">pfrestore</a>**

The script must be run as root to be able to access the back up files.  

Puppet will back up files to a "clientbucket" location on the local filesystem (unless its been configured to use a central bucket, in which case, this script wont help you.  Sorry) in a nine level directory hierachy based on the MD5 sum of the file.  This makes it somewhat cumbersome to find a particular backup file that you may be looking for.   

**<a name="pfrestore">pfrestore</a>** solves this by scouring all of the backup directories and providing a simple menu for recovering those files.  The recovered files will get written to the /tmp directory so you dont need to worry about Puppet overwriting them again as soon as youve recovered them.  


<img src="images/pfrestore.png" alt="Example showing a listing of files that have been replaced by Puppet">

* Initial listing of changed files that are available for restore


<img src="images/pfrestore-diff.png" alt="Example showing the diff process and prompt for restore">
* Diffing the backed up file with the active file and prompting for the restore to the /tmp directory


[-top-](#top)

---


Last Updated: Tue May 31 12:30:03 CDT 2016
