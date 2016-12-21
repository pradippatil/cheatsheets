

#### Which shell?
`echo $SHELL`

##### Check if a directory exists?
-d flag of `test`

    if [ -d $mydir ] 
    then
    command(s)
    fi

---
##### Write command to list all the links from a directory?
`ls -lrt | grep "^l"`

---
##### How will you run a process in background? How will you bring that into foreground and how will you kill that process?
For running a process in background use "&" in command line. For bringing it back in foreground use command "fg
jobid" and for getting job id you use command "jobs", for killing that process find PID and use kill -9 PID
command. This is indeed a good Unix Command interview questions because many of programmer not familiar
with background process in UNIX

---
##### Check if a directory is empty?
No direct flag. Check count of files/dirs it contains.

    if [ $(ls -lA $mydir | wc -l) -eq 0 ] 
    then
        directory is empty
    fi

---
##### Find total number of fields from a line
`awk -F, '{print NF}`

---
##### Print last field a line
`awk -F, '{print $NF}`

---
##### Send STDOUT and STDERR to same file
`command > file 2>&1`

---
##### Debug flag?
`set -x`

---
##### What are links and symbolic links in UNIX file system?
A link is a second name (not a file) for a file. Links can be used to assign more than one name to a file, but cannot be used to assign a directory more than one name or link filenames on different computers.
    Link: `ln target linkname`

Symbolic link ‘is’ a file that only contains the name of another file.Operation on the symbolic link is directed to the file pointed by the it.Both the limitations of links are eliminated in symbolic links.
    Symbolic link: `ln -s target linkname`

---
#### Process IDs
Current process id: `$$` </br>
Parent process id: `$PPID` </br>
Parent process id of any PID: `ps -p $pid -o ppid=` </br>


---
##### How do you copy file from one host to other?
Many options but you can say by using "scp" command. You can also use rsync command to answer this UNIX
interview question or even sftp would be ok.

---
#####  How do you find which process is taking how much CPU?
By using "top" command in UNIX, there could be multiple follow-up UNIX command interview questions based
upon response of this because “TOP” command has various interactive options to sort result based upon various
parameter.

---
#####  How do you check how much space left in current drive ?
By using "df" command in UNIX. For example "df -h ." will list how full your current drive is. This is part of
anyone day to day activity so I think this Unix Interview question will be to check anyone who claims to working in
UNIX but not really working on it.

---
##### Your application home directory is full? How will you find which directory is taking how much space?
By using disk usage (DU) command in Unix for example du –sh . | grep G will list down all the directory which
has GIGS in Size.

---
#####  How do you find whether your system is 32 bit or 64 bit ?
Either by using "uname -a" command or by using "arch" command.

---
#####  There is a file Unix_Test.txt which contains words Unix, how will you replace all Unix to UNIX?
You can answer this Unix Command Interview question by using SED command in UNIX for example you can
execute sed s/Unix/UNIX/g fileName.

---
#####  You have a tab separated file which contains Name, Address and Phone Number, list down all Phone Number without there name and Addresses?
To answer this Unix Command Interview question you can either you AWK or CUT command here. CUT use tab as
default separator so you can use
cut -f3 filename. 

---
##### How do you find for how many days your Server is up?
By using uptime command in UNIX

---
##### You have an IP address in your network how will you find hostname and vice versa?
This is a standard UNIX command interview question asked by everybody and I guess everybody knows its answer as well. By using nslookup command in UNIX, you can read more about Convert IP Address to hostname in Unix here 

---
##### Read 2 files in parallel

---
##### How to send mails in Unix?

---
##### How to connnect to db?
We can use isql utility that comes with open client driver as follows:
isql –S serverName –U username –P password

---
##### How will you find the 99th line of a file using only tail and head command?
tail +99 file1|head -1

---
##### Find n^th line from huge file without using head/tail
head and pipe with tail will be slow for a huge file. I would suggest sed like this:
`sed 'NUMq;d' file`

---
##### What is the difference between $$ and $!?
$$ gives the process id of the currently executing process whereas $! shows the process id of the process that recently went into background.

---
##### What are zombie processes?
These are the processes which have died but whose exit status is still not picked by the parent process. These processes even if not functional still have its process id entry in the process

---
##### I have 2 files and I want to print the records which are common to both.
We can use “comm” command as follows:
comm -12 file1 file2 ... 12 will suppress the content which are unique to 1st and 2nd file respectively.

---
#####  How will I insert a line “ABCDEF” at every 100th line of a file?
sed ‘100i\ABCDEF’ file1

---
##### 

---
##### 

---
##### 