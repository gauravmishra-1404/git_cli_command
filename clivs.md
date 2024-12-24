*******Command Line Interface************
shell provide an interface we can write or enter command using keyboard.
this is called CLI.
user write a human readable command which shell interprete that command to machine understanding language then this output goes to kernel which helps to software interact hardware.

there are several shells: BASH, CSH, KSH.

various ways to access the shell:
using linux terminal, connect via secure shell (ssh), console.

How to I find out my current shell name?
cat /etc/shells

For current Shell Type:
echo $SHELL --> command used to give the current shell name
ps $$  --> this gives the info about p0id, port of out current shell
ps -p $$

****Command (cd)
cd or cd / :  reprresents the root directory means show the all root directory.
cd . : represents the current directory
       this used to make path relative in current directory.
       eg.: cd ./one/two
cd .. : represents the one back of current directory
cd /bin : Essential User binaries which used when system is mounted in single user mode.
cd /etc : configuration file which is editable.
/home : home folders contains the all folder for each user.
        eg if u r a bob then ur home folder will be /home/bob
        
/opt: optional packages contains sub directories for optionl software packages.

pwd : will give the path of the currently where you are present.
ls : will give the list of all files and directories which present in the current directory.
ls -l : will give the list of all files and drectories but in log formate.
ls -lh : -l-->long formate   -h ---> human readable language 

mkdir : used to create a new directory.
mkdir hello : used to create directory named hello
touch : command is used to the create the any type of file
    eg. touch a.txt
tree any_directory_name: used to see subdirectories and files of the current directory.

nano directory/file_name : is provide the interface to edit the file.
rm /file.txt : used to remove the file.
rm -R hello : used to remove the directory whiich is not empty.
rm hello: it only remove the empty directory
mv : command is used to move or rename the files and directories
   eg.  mv hello/one/a.txt hello/one/two --> it will move the a.txt file from one folder to two folder.
   
**********Permission*********
Type of ownership:
1. User 2. group  3. others
eg. -rwe-w-r--  --> where first - represents the file while d represents the directory.

commands for permission:
**chmod : is used to give or edit permission for different users.

there are two ways to give permission:
1. numeric   2. symbolic

1. numeric 
   eg. chmod 746 hello ---> every digit of the 746 number signifies the type of permission give to that file or directories
   
   r -> read, w-> write  x -> execute
   r w x
   0 0 0 0
   0 0 1 1
   0 1 0 2
   0 1 1 3
   1 0 0 4
   1 0 1 5
   1 1 0 6
   1 1 1 7
   
2. symbolic: u --> user, g --> group, o --> other
      + --> add the permission 
      eg: chmod u+r hello
      
      - --> remove the permission
      eg: chmod u-r hello
      
      = --> overwrite the command or replace the current command
      eg: chmod u=w hello
      
**chown: this command is used to change the name of the owner that is user or group of the file.

chown [OPTIONS] [OWNER][:GROUP] FILE

     eg. chown alice hello
     eg. chown :developer hello
     eg. chown alice:developer hello
************************************************************
**Pipe (|) : it the operator which cascade the different command lines.
eg.  ls -l | head -n 3

**Choosing Between wget and curl
Use wget when:
You need simple file downloads.
Recursive downloads or mirroring websites are required.
Automatic resumption of downloads is essential.

syntax: 
wget -O harry.txt URL
eg. wget -P /home/user/Downloads/ https://example.com/file.txt  --> used to download the file using url at specific location.

-P used for specify the path on with we want to download a file.

Use curl when:
You require more advanced HTTP features (headers, cookies, authentication).
You need to work with APIs (POST, PUT, DELETE requests).
You need support for additional protocols like SCP, SFTP, etc.

syntax:
curl -O harry.txt url 

**head -n number_line file_name --> command is used to print top n lines

**tail -n number_line file_name  --> command is used to print last n lines

**grep --> command is used for filtering the text from the file.txt

eg. grep -c -i "Harry" --> -c for count the word
                           -i for remove k sensitive means Harry and harry will count.
          s                 

**cat text1.txt text2.txt --> cat command is used for concating the two text file or more  
**tac text1.txt  ---> tac command is used print in reverse order
***rev text1txt  --> reverse the text as well as word.

***********process********************
ps : process status displays the processes running in the current shell.
ps -e ---> gives the info pid no., TTY, TIme, CMD about process
ps -ef :  provides the detail info
ps -ef --forest -> commands gives the tree of the process
ps aux --> gives the complete info about the process in terms of %CPU, %MEM, VSZ,RSS,TTY,Start, STAT TIME,COMMAND

ps -e -o pid,ppid,comm ---> -o helps to customize our column pid,ppid,comm

kill the process:
ps aux | grep <process_name> | awk '{print $2}' | xargs kill -9

aux: gives all process list running on the machine
grep: used to find the process 
awk: helps to print the 2nd column that is pid of process.
xargs: will take the pid id from awk and passed forcefully to kill statement.

**What is your user in Linux?
commands: whoami
          echo $USER
          id -un
          
**What is your group in Linux?
 command: groups
 
 **What is your computer architecture? (hint: uname command, learn the flags)
 command:  uname -m --> machine information
 	   uname -a --> gives the all information about the system.
 	   
**What is your audio driver? (hint: lspci, learn pipes and grep)
command: lspci --> gives the list of all the details about pci hardware which connected to the motherboard like audio chip, graphic card, etc.

PCI--> stands for peripheral component interconnect.
lspci | grip -i "audio"

 ***Display all active connections and the corresponding TCP / UDP ports.
        //lsof -i -P -n --> it will give list of all processes and port name contains both tcp and udp
                        : for tcp-> lsof -i tcp
                        : for udp -> lsof -i udp
                        
**Managing Software**
  ***Use apt (Ubuntu) or homebrew (Mac) to:
        * Install htop, vim and nginx
                sudo apt -i -y htop vim nginx --> sudo is used for administrative work where when we required to install, managing
                                                 software packages, -i means install, -y means without permission 
        * Uninstall nginx
           // sudo apt remove nginx --> command uninstall the application but not the configuration of appl.
         dg  //sudo apt purge nginx  --> command uninstall the application and also remove all configuration of appl.
           //sudo apt autoremove ngnix --> command used to uninstall, remove configuration file and dependency file.
          
More CLI commands:-
cp: with recursive flag:The cp command in Linux is used to copy files and directories. The recursive flag (-r or -R) is used to copy directories along with their contents, including subdirectories and files.

cp -r [source] [destination]

eg. cp -r /path/to/source-directory /path/to/destination-directory

cp -r dir1 dir2 /path/to/destination --> multiple directory

cp -rp /path/to/source /path/to/destination --> for preserve file attributes like timestamps and permission


**less : command opens the text file into another
eg. less harry.txt

**more harry.txt ---> it open the interface which show how many percentage of text you scrolled.

**rsync: 
The rsync command in Linux is a versatile and fast utility for copying and synchronizing files and directories locally or remotely. It is widely used for backups and mirroring due to its ability to transfer only the changed portions of files, saving time and bandwidth.


rsync [options] [source] [destination]

OS/Process Related Commands:
ps  -> The ps command in Linux/Unix is used to display information about active processes running on the system. It provides details such as process IDs (PIDs), user ownership, CPU and memory usage, and the commands that started each process.

top : command is used to give the top of n number of lines of the processes. eg. //top -o %CPU -n 1 | head -n 3 
or //ps aux --sort=-%cpu | head -n 3

df --> command will gives the info about the disk interms of there storage, name, etc.

uname --> uname will gives the info about the system.
usecases: uname -a  ---> provides all info about the system like architecture, type of operating system, day of installed in ur system, etc.

uname -m  --> gives architecture info.

free ---> command is used for the getting info about the RAM usage.
       info like total RAM size, used, cached, shared, avaiable ram.
       
lspci ---> command will list the all the peripheral component interconnected which are external component like graphic card, audio driver,etc to the mother board.

usecase: lspci | grep -i "audio"
kill (with flags)

Network:
**ssh: 
Benefits of Using SSH
Encryption: Ensures secure communication.
Authentication: Supports password, key-based, or multi-factor authentication.
Versatility: Supports tunneling, port forwarding, and file transfers.
Cross-Platform: Available on Linux, macOS, and Windows.
