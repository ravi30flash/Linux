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

```


