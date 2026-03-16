# Linux Filesystem Basics

Linux uses a hierarchical file system structure starting from the root directory (/).

Important directories:
- /home : Stores user files
- /bin : Contains essential system commands
- /etc : Configuration files
- /var : Log and variable files
- /tmp : Temporary files

## Basic Linux Commands

pwd  
Prints the current working directory.

ls  
Lists files and directories in the current folder.

cd  
Changes the current directory.

mkdir  
Creates a new directory.

touch  
Creates a new empty file.

cp  
Copies files from one location to another.

mv  
Moves or renames files.

rm  
Deletes files or directories.

rmdir  
Deletes an empty directory.

Command	      Purpose
cat file	    show full file
less file	    scroll through file
head file	    show first lines
tail file	    show last lines

## Conclusion

These commands help users navigate and manage files in Linux. They are fundamental for cybersecurity professionals since most security tools operate on Linux systems.
# Linux Users, Groups, Permissions & Basic Security Commands

## Users: Users are accounts that can access a Linux system.
Example:
root (administrator)
normal users like anmol or analyst
Users have:
username
home directory
password
permissions

## Commands used for user management:
useradd → creates a new user in the system
passwd → sets or changes a user's password
Example:
sudo useradd analyst
sudo passwd analyst
Verify the user:
id analyst
This shows the user ID and group ID of the user.

## Groups
Groups allow multiple users to share the same permissions.
Example:
developers group:
anmol
john
This helps manage access control more efficiently.

## File Permissions
Linux permissions include:
r = read
w = write
x = execute
Permissions apply to three categories:
user (owner)
group
others
Example permission:
-rwxr-xr--
Meaning:
User → read write execute
Group → read execute
Others → read only

## Numeric Permission System
Linux permissions are also represented using numbers.
Values:
r = 4
w = 2
x = 1
They are added together.
Examples:
rwx = 7
rw- = 6
r-x = 5
r-- = 4
--- = 0
Example command:
chmod 755 script.sh
Meaning:
User → rwx
Group → r-x
Others → r-x

## chmod Command
chmod → changes the permissions of files or directories.
Numeric method:
chmod 755 script.sh
chmod 600 secret.txt
chmod 700 secure_folder
Examples:
chmod 755 script.sh
User → read write execute
Group → read execute
Others → read execute

chmod 700 secure_folder
Owner → full access
Group → no access
Others → no access

## Symbolic Permission Method
Structure:
chmod [who][operation][permission] file
Who:
u → user
g → group
o → others
a → all
Operations:
→ add permission
→ remove permission
= → set exact permission

Examples:
chmod u+x script.sh
Adds execute permission to the user.
chmod g-w report.txt
Removes write permission from group.
chmod o+r report.txt
Adds read permission for others.
chmod a+x program.sh
Adds execute permission for everyone.

## chown Command
chown → changes the owner of a file or directory.
Example:
sudo chown analyst notes.txt
This changes the owner of the file to analyst.
Verify using:
ls -l
Example output:
-rw-r--r-- 1 analyst anmol notes.txt
Owner of the file is now analyst.
Change owner and group together:
sudo chown analyst:analyst notes.txt
Creating Files and Directories
touch → creates an empty file
Example:
touch report.txt
mkdir → creates a new directory
Example:
mkdir secure_folder
Listing Files and Permissions
ls → lists files in a directory
Example:
ls
ls -l → shows files with permissions, owner and size
Example:
ls -l
Example output:
-rwxr-xr-x script.sh
Breakdown:
rwx | r-x | r-x
user group others

## Hidden Files
Files starting with "." are hidden files.
Examples:
.bashrc
.profile
.secret

Commands:

ls -a → shows hidden files
ls -a
ls -la → shows hidden files with detailed information
ls -la

Security insight:
Attackers sometimes hide malicious scripts using hidden files.

System Users File

Linux stores all user accounts in:

/etc/passwd

View the file:

cat /etc/passwd

Example entry:

root:x:0:0:root:/root:/bin/bash

This contains information about all users in the system.

grep Command

grep → searches for specific text inside files.

Example:

Find root user:

grep root /etc/passwd

Find a specific user:

grep analyst /etc/passwd

Search recursively inside directories:

grep -r password .

This searches the word password in all files in the current directory.

Dangerous Permissions

Example:

chmod 777 file.sh

Permission:

rwxrwxrwx

Meaning:

Everyone can read, write and execute the file.

This is dangerous because any user or attacker can modify the file.

Mini Security Task Performed

Created a secure directory:

mkdir secure_folder
chmod 700 secure_folder

This ensures only the owner can access the directory.

## Day 3 Key Skills Learned

Creating users (useradd)
Setting passwords (passwd)
Understanding file permissions (r, w, x)
Numeric permission system
Symbolic permission system
Changing permissions (chmod)
Changing file ownership (chown)
Listing files and permissions (ls -l)
Detecting hidden files (ls -a)
Viewing system users (/etc/passwd)

Searching files using (grep)
