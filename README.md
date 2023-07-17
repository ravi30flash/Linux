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

++++++++++++++++++++++++++++++++++++++++++++++

Installation:
``20G

1) /    		[ Parent Partition ] 

2) /boot		[ Booting Configuration ] GRUB

3) SWAP		[ RAM x 2 ] = 8G
							Phy 
							Mem

A part of HDD/SSD act as RAM, is called Virtual Mem





File SYstem:
``` 
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

Storage
Device
a
-----------
CD/DVD:

/dev/sr0
/dev/sr1

