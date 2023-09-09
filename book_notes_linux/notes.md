### Basic commands
```bash

# to know date of system
date 

# to know date of system
date -u

# to see calender on cli mode
cal

# to know logged in userid
whoami

# command to get information about uid & gid of the system
id

# which command is used to know current working directory
pwd

# dot notation
./ : this denotes current working directory
../ : this denotes parent directory

# which command is used to list the items in a directory
ll

# which command is used to create directory 
mkdir

# which command is used to remove rm files & directory
rm

```

### commands with their description 

#### cat
```bash
options :
    1. -A : show all 
    2. -n : show number
    3. --version : output version information & exit
```

#### shred
```bash
options : 
    1. -f : change permission to allow writing if necessary
    2. -n : define no of times file to be overwritted. deafult (3)
    3. -s : size (shred this many bytes)
    4. -u : truncate and remove file after overwriting
    5. -v : verbose (show progress)
    6. -z : add a final overwrite with zeros to hide overwriting
    7. --version : to know version of the given shred command
```

#### ssh
```bash

Description: is a program for logging into a remote machine and for executing commands on a remote machine. It is intended to replace rlogin and rsh, and provide secure encrypted communications between two untrusted hosts over an insecure network

options: 
    1. -q : quite mode, warning & diagnostic messages are suppressed
    2. -v : verbose
    3. -p : port to connect on remote host
    4. -o : option
    5. -n : redirect stdin from /dev/null 
    6. -l : login name

```

#### uname 
```bash
Description: this command is used to print system information

options: 
    1. -a : all
    2. -s : prints kernel name
    3. -n : nodename
    4. -r : kernel release
    5. -v : kernel version
    6. -m : machine hardware name
    7. -p : processor type
    8. -i : prints the hardware platform
    9. -o : operating system information
    10. -h : help 
    11. --version : version of command

```

### how to add password for single user mode
```bash
step 1: login into the system
step 2: edit the file 
    -> vi /etc/sysconfig/init
step 3: find the line which starts with 
    -> SINGLE=/sbin/sushell 
step 4: edit this line to
    -> SINGLE=/sbin/sulogin
    -> save & exit
    -> reboot 
```

### what is PAM in linux
```bash
PAM : plugable authentication modules

these modules are used to autheticate the login users

files:
    /etc/pam.d
    /etc/pam.d/login
    /etc/pam.d/sshd
    
```

#### what is numa ? How does it work? how does it function?
