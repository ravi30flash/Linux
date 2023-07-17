# Linux
notes about linux 

## DAY : 1
Types of OS:
```
Single User Single Tasking [DOS]
Single User Multitasking [Win]
Multiuser Multitasking [Linux/unix]
Real Time
Embedded

Open Source
```
- Free to study
- Free to modify
- Free to dist.

### History of SHELL:
```
sh 		[ SHELL ]
ksh		[ Korn Shell ] : UNIX Script
To exe multi objs using a single obj.

csh 		[ C lang Shell ]
tcsh 	[ Turbo C shell ]
BASH  	[ ksh + tcsh ] 
```

1. POST
1. BIOS   
&nbsp;&nbsp;&nbsp;&nbsp;    \\_ CD/DVD  
&nbsp;&nbsp;&nbsp;&nbsp;    \\_ HDD/SSD *  
&nbsp;&nbsp;&nbsp;&nbsp;    \\_ USB  
&nbsp;&nbsp;&nbsp;&nbsp;    \\_ N/W
1. MBR [ Master Boot Record ]
1. Boot Loader [ GRUB ] 
			

* CLI  
&nbsp;&nbsp;&nbsp;&nbsp;    \\_ TUI [Text-mode user interface]   
* GUI

---

Installation:
```
20G

1. /    		[ Parent Partition ] 
1. /boot		[ Booting Configuration ] GRUB
1. SWAP		[ RAM x 2 ] = 8G Phy Mem

Swap Memory : A part of HDD/SSD act as RAM, is called Virtual Mem

File System: 
FAT32 - 512 kb/block
NTFS  - 4 MB/block

ext2
ext3
ext4
xfs
vfat [fat, fat16, fat32]

/dev/sda : HDD
/dev/sda1 : Partition
/dev/sda2

Storage Devices
-----------
CD/DVD:
    \
     -> /dev/sr0
     -> /dev/sr1
```
## DAY : 2
```
kiosk@kiosk-virtual-machine:~$
kiosk: username
kiosk-virtual-machine: hostname
~ [tilde] : home dir of logged in user
/home/user1
/home/natasha

Types of user:
/root
$ : Normal User 
# : Root user
______
linux Folder structure:
/bin    : [binary]
/sbin 	: [Super Binary]
/usr	: [All system commands] /usr/bin, /usr/sbin/
/boot	: [Booting Configuration] GRUB
/dev	: [Devices]
/lib	: [Library]
/lib64	: [Library]
/mnt,/misc,/opt,/media : EMPTY
/home	[Home Dir of normal users] /home/natasha ; /home/harry
/root	[Home Dir of Super User]
/proc	[Process & hardware related information]
/selinux[RHEL/CentOS: Security Enhanced Linux] File Based Security [rwx]
/etc		[Important: system services & system related config]
/srv		[Service: Third party services]
/sys		[System: system driver database]
/tmp		[Temp]
/var		[variable data: spool dir(mail inbox), logs]
files	[static/dynamic]
```
## Basic Commands:
PATH:
```
Absolute Path [/home/natasha/Desktop]
Relative Path [cd Dir]
```
1. pwd			:	Present Working Dir  
1. whoami 	:	Check the loggedin user  
1. date		:	Show the date & time  
1. ls			: 	Show the list of dir contents
1. mkdir dir_name		:	Make dir
1. touch filename		:	To crete a blank file
1. cat > filename		:	Create a new file with text.

[ctrl+d : exit]

    >	stdout	[ Standard output to the program ]  
    <	stdin	[ Standard input to the program ]

\# cat > secret
redhat  
redhat

1. cat filename: To show the text of file
1. passwd username: To reset the password for user.
1. cat >> filename : To append the data in existing file.
text
[ctrl+d]: To save
1. remove:
* A file:  
    \# rm filename
* A dir:  
\# rm -rfv dir_name
```
-r [ Recursive ] 
-f [ Forcefully ]
-v [ verbose ] : to view the process in detail.
```
* MOVE:  
    \# mv sourceFile/Dir DestinationDir

* COPY:
    * File to File:  
        \# cp srcFile dstFile

    * File/Dir to Dir:  
        \# cp -rfv srcFile/Dir dstDir
---

`echo "MSG"` : Print the msg on screen  
`ls -a`	:	Show all/Hidden files/Dirs

`mkdir .dirname`	: Hidden dir  
`touch .filename`	: Hidden file

`history`	: To show the history  
* ![history_index_number]  
* `!2000`	: Exe history index number

`history -c` : Clear/Clean the history

`tty`: Print/show th console identity

\# `echo "Hello" > /dev/tty1`

ENV variable[SYSTEM Variable]  Check:  
### Environment variables 

Print:

`echo $SHELL`  
`history`

`echo $HISTSIZE`  
Output : 1000

change the value of env variables but for current working env:

---
export HISTSIZE=0

\# `cd /root/`  
\# `ls -a`  
`.bash_history`  
____

\# `echo $HISTTIMEFORMAT`

    %d : Day
    %m : month
    %y : year
    %T : Timestamp

\# `export HISTTIMEFORMAT="%d-%m-%y %T"`


# Day 3: User Management
```
user related info:
# cat /etc/passwd
    hunt:x:1000:1000:,,,:/home/hunt:/bin/bash

Password info:
# cat /etc/shadow
    hunt:Encrypted pass:Acc Age

SHA512 + Salt Algo
UID [0-60000]     | GID [0-60000]
0-999 Super user  | 0-999 Super group
1000+ Regular user| 1000+ regular group

Group info:
# cat /etc/group
    grp:x:GID

Group pass:
# cat /etc/gshadow

1) Add user:
    # adduser username
check:
    # id username

2) Password:
    # passwd username
    # passwd -d username 
    -d : delete

3) Login:
    # su - username
        # exit
        OR
        # logout

4) Delete user:
    a) without home dir
        # userdel username

    b) with home dir
        # userdel -r username

Groups: 
1) Add group:
    # groupadd groupname

2) Password:
    # gpasswd groupname

3) Delete:
    # groupdel groupname


Memberships:
a) Primary

    add user as primary member of a group:
    # groupadd grp
    # useradd -g grp u1
        -g: Primary membership

b) Secondary

    i) add user as secondary member of a group:
    # groupadd lol
    # useradd -G lol pipi
    -G: secondary member

    ii) Add an existing user in a group as secondary member:

    # usermod -G grp natasha

Permissions:
1) Symbolic Method

    read    : r  
    write	: w  
    execute	: x  

    user owner	: u  
    group owner	: g  
    others  : o  
    All : a  

    Assign		: +  
    Remove		: -  
    Overwrite	: =  

Permission Area:
# ls -l
    drwxr-xr-x  2 root  root   6 Mar 22 17:47 kids
    rwx     |   r-x     |	r-x
    u		|	g		|  	o

Default perm for file:
read & write : u
read		 : g
read		 : o

Default perm for dir:
read, write & execute : u
read & execute		  : g
read & execute		  : o


File Type:

    Regular file  	[-]
    Dir				[d]
    block			[b]
    char			[c]
    pipe OR Socket	[p OR s]
    link			[l]

Assign perm using Symbolic method:
    # chmod u+xwr file/dir

    # chmod u+w,u-x file/dir

    # chmod u+rw,g=w,o-rwx file/dir

    # chmod a=w  file/dir
    OR
    # chmod ugo+rw file/dir
    OR
    # chmod +w file/dir

2) Numeric Method
    read	: 4
    write	: 2
    execute	: 1
    Full	: 7
    No		: 0
    
    ---		000		0
    r--		100		4
    -w-		010		2
    --x		001		1
    rwx		111		7
    

# chmod 517 file/dir
	    u:g:o
```

