# Linux Commands
#### netstat -tupln:
| **Flag**  |  **Function** |
| :--------- | :-------------- |
| t | tcp ip|
| u | udp |
| p | program |
| l | listening or not |
| n | numeric IP addresses |
   
**Sample Output:**
```bash
$sudo netstat -tupln
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address			State       PID/Program name    
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      548/systemd-resolve 
tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      582/cupsd           
tcp6       0      0 ::1:631                 :::*                    LISTEN      582/cupsd 
```      
This command requires _**root**_ to display the programs bound to each port.
   
**Note: Command to install**
```bash
$sudo apt install nettools
```
#### top

Prints details of all processes running in the system, by default sorted based on CPU usage
   
**Sample Output:**
```bash
$top
PID  USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND                                                                                                                              
2730 mahesh    20   0 4251464 350304 132672 S  20.5   8.7   0:47.10 gnome-shell                                                                                                                         
2409 mahesh    20   0  717704 107180  56904 S  13.2   2.7   0:13.14 Xorg                                                                                                                                 
3160 mahesh    20   0  969592  51852  37888 S   6.3   1.3   0:10.96 gnome-terminal-                                                                                                                      
   1 root      20   0  168920  12904   8448 S   0.7   0.3   0:06.70 systemd                                                                                                                              
3505 mahesh    20   0   20604   3848   3292 R   0.7   0.1   0:00.18 top                                                                                                                                 
  11 root      20   0       0      0      0 I   0.3   0.0   0:00.64 rcu_sched                                                                                                                            
2546 mahesh    20   0  100008   2076   1700 S   0.3   0.1   0:01.04 VBoxClient                                                                                                                          
2587 mahesh    20   0  826664  61976  41036 S   0.3   1.5   0:04.42 ibus-extension-                                                                                                                     
   2 root      20   0       0      0      0 S   0.0   0.0   0:00.04 kthreadd       
```
    
## User Account Management
 _All following commands required **root** priveleges to work_

#### useradd
This command is used to add users into unix systems. `adduser` is a script based which works only on debian based distros

```bash
$useradd -m -d /home/username -s /bin/bash username
```
| **Flags** | **Meaning** |
| :-------: | :---------- |
| -m | make home directory |
| -d | destination/path of home directory |
| -s | login shell for the user:<br>**null** &rarr; Default shell<br>**/bin/false** &rarr; No Login shell |
| -u | user id to assign | 
| -g | group id to assign |

**Note:**
User created using useradd have no password assigned and cannot be used refer: [passwd](#passwd)

#### userdel
This command is used to delete user account from system.

```bash
$userdel [username|userid]
```

**Note:**
The home directory of the user exists even if the user is deleted and the owner and the group refer to non-existant user id's

#### usermod
Command used to modify user accounts

| **Flags** | **Meaning** |
| :-------: | :---------- |
| -d | New Home directory for user |
| -m | :warning: requires -d<br> Move existing contents |
| -L | Lock user account |
| -U | Unlock user accounts |
| -aG | add user to groups | 

```bash
$usermod -L username
#Locks the user account and prevents access to user account

$usermod -U username
#Unlocks the user account
```

#### passwd
  This command assigns password to user
  
  ```bash
  $passwd newuser
  New password: 
  Retype new password:  
  passwd: password updated successfully
  ``` 
   
## Important Files
#### /etc/passwd
Stores all the users and the details in this order:
1. Human Readable Username
2. Hashed password of the user
3. User ID
4. Group ID
5. User Details
6. Home Directory
7. Login Shell

#### /etc/shadow
Stores the _hashed_ passwords of the users listed in [/etc/passwd](#/etc/passwd)
| **Text** | **Meaning** |
| :------: | :---------- |
| gibberish | Hashed User pswd |
| ! | User Locked  |
| * | Can not enter a password |

#### /etc/group
Stores the groups on the system, by default each user created has a group with the same name

#### /etc/skel
Contains files which are by default created in new user's home directory.


 
