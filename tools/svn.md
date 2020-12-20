# Subversion

## NEW MACRO COMMANDS:
ADD – Replaced standard add command. Display option to select either ADDL (w/ needs-lock property) or ADDM (w/out needs-lock property)

	$ no equivalent svn sequence

ADDL – Add with Needs-Lock Property -- Schedule to be added & set ‘needs-lock’ property

	$ svn add FOO; svn propset svn:needs-lock yes FOO

ADDM – Add without Needs-Lock Property (Multi-access) – Same as regular svn add command

	$ svn add FOO

EDIT – Request Lock Token and open file in preferred text editor

	$ svn lock FOO; $EDITOR FOO

SUBMIT/SUB – Commit changes to repo & remove lock (note that initial submit will result in a warning because of attempt to unlock files that haven’t previously been locked, but it works anyway)

	$ svn commit FOO; svn unlock FOO

SETNEEDSLOCKPROP/SNLP – Shortcut to set the ‘needs-lock’ property

	$ svn propset svn:needs-lock yes FOO 

## SCRIPT:
Script location: /home/username/bin/svn-edit-lock
It’s recommended that you alias svn to /home/username/bin/svn-edit-lock. All standard svn commands will execute as normal (except ‘svn add’), plus you get the new macros (addl, edit, & submit). There is no need to actually use these macros or alias the svn-edit-lock script because each command could be executed by entering the equivalent svn commands, but I think they simplify the process and force proper usage.

## USAGE:
### ADDING A FILE/DIRECTORY:
‘svn addl’ – Use just as you would use standard ‘svn add’ command. The only difference is that the addl command sets the svn ‘needs-lock’ property on the file.

### MODIFYING A FILE (lock-modify-unlock):
When you wish to modify the file ‘FOO’, you request the lock token by either ‘svn lock FOO’ or ‘svn edit FOO’. The only difference in the 2 commands that ‘svn edit’ 1st locks file, then opens in your preferred text editor (\$EDITOR). Successful locking automatically changes the write permissions on the file from read-only to writable.

If someone already has the file locked or you attempt to lock a file that is out-of-date (i.e. needs updating), you will notified as such and the file will remain read-only.

Once you are done modifying the file and are ready to commit (check-in) the file to repository use ‘svn submit [FOO/*/./etc]’. This command will release the lock token on the file/directory/etc and then commit it to the repository. The write permissions will return to read-only and others will be allowed to lock/modify the file.

Note: You can always override the local file permissions with chmod if you need to make temporary changes to a file someone else has locked, but it’s not recommended.

### SETTING/VIEWING NEEDS-LOCK PROPERTY ON FILES ALREADY IN REPOSITORY:
If you’re starting from an existing svn design in which files are already in the repository, you may only want to set the ‘needs-lock’ property. For this operation the snlp shortcut executes the desired svn command.
To set the property on multiple files at once, list each file after the ‘svn snlp’ cmd:

    $ svn snlp FOO1 FOO2 FOO3 …

Using * wildcard to set property on all files (e.g. svn snlp *) will only work if all files are already in repository. Otherwise the process will error-out on 1st non repo file.
To view the properties on files use ‘svn proplist’

	$ svn proplist *

### COMMON STANDARD SVN COMMANDS:
CHECKOUT (co)-- Initial Populate – Creates a working copy of the project

    $ svn co svn://cdcs.engineering.linear.com/ltcXXXX/trunk design/

**UPDATE** (up) – Incorporate any changes committed by others since last update or initial checkout

    $ svn update <., DIR, FILENAME>

**ADD** – Schedule file/dir/link to be added to the repository during next commit

	$ svn add FOO

**STATUS** (st) – Detect & Report all file & tree changes you’ve made

    $ svn status [PATH...]
```
-u (--show-updates) – Display “out-of-dateness” information
-v (--verbose) – Show ALL entries under version control
		? item – item not under version control
		A item – item has been scheduled for Add
		C item – item is in a state of Conflict
		D item – item has been scheduled for Deletion
		M item – item has been Modified
```

**COMMIT** (ci) – Send changes from your working copy to the repository

	$ svn commit  [PATH...]

### OTHER STANDARD SVN COMMANDS:
**HELP** – Help command

	$ svn help checkout

**DELETE** – Schedule file/dir/link to be deleted from the repository during next commit

	$ svn delete FOO

**COPY** – Creates new item and schedules for addition to repository

    $ svn copy FOO BAR

**MOVE** – Exactly the same as running: svn copy FOO BAR; svn delete FOO

	$ svn move FOO BAR

**MKDIR** – Exactly the same as running: mkdir FOO; svn add FOO
	
    $ svn mkdir FOO

**DIFF** – 

	$ svn diff FOO

**REVERT** – Restores file/dir to its unmodified state

	$ svn revert FOO

**RESOLVE** – Resolves issues between local version and repository

	$ svn resolve .

**LOCK** – Requests lock token so user may edit file. Sets file properties to Writeable

	$ svn lock FOO

**UNLOCK** – Releases lock token so others may request lock/edit privileges. Sets file properties to Read-Only 

	$ svn unlock FOO

**PROPSET** – Set property (e.g. need-lock or executable)

	$ svn propset svn:needs-lock yes FOO
	$ svn propset svn:executable on RUNFOO

**PROPLIST** – List properties

	$ svn proplist *

