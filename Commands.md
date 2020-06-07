# Linux Commands
 - **netstat -tupln**:
    | **Flag**  |  **Function** |
    | :--------- | :-------------- |
    | t | tcp ip|
    | u | udp |
    | p | program |
    | l | listening or not |
    | n | numeric IP addresses |
    
    **Sample Output:**
    ```console
    mahesh@mahesh-VirtualBox:~$ sudo netstat -tupln
	Active Internet connections (only servers)
	Proto Recv-Q Send-Q Local Address           Foreign Address			State       PID/Program name    
	tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      548/systemd-resolve 
	tcp        0      0 127.0.0.1:631           0.0.0.0:*               LISTEN      582/cupsd           
	tcp6       0      0 ::1:631                 :::*                    LISTEN      582/cupsd 
    ```      
    This command requires `root`to display the programs bound to each port.
    **Note: Command to install**
    ```console
    sudo apt install nettools
    ````
  - **top**
    Prints details of all processes running in the system, by default sorted based on CPU usage
    
    **Sample Output:**
    ```shell
    mahesh@mahesh-VirtualBox:~$top
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
## Important Files
### /etc/passwd
Stores all the users and the details in this order:
1. Human Readable Username
2. Hashed password of the user
3. User ID
4. Group ID
5. User Details
6. Home Directory
7. Login Shell

### /etc/shadow
Stores the __hashed__ passwords of the users listed in `/etc/passwd`

### /etc/group
Stores the groups on the system, by default each user created has a group with the same name

 
