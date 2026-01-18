🟢 Linux Basics – DAY 2
Users, Groups & Permissions
📌 Why Linux Needs Users & Groups

Linux is a multi-user operating system, which means:

Many people can use the same system

Everyone should not access everything

Security is controlled using users, groups, and permissions

Example:

anmol → full access to her files

student → limited access

System files → only root can modify

👤 Users (What is a User?)

A user is an account that can:

Log in to Linux

Create files

Run programs

Types of users:

root → superuser (administrator)

anmol → normal user

student → another normal user

Each user has:

Username

UID (User ID)

Home directory (/home/username)

Password

👥 Groups (Why Groups Exist)

A group is a collection of users.

Why groups are needed?

👉 To manage permissions easily and securely.

Example:

Group: developers

Users: anmol, student

Folder: /project

Giving permission to the group allows all members to access it.

➡ Without groups → permission management becomes messy and insecure.

📁 Important System Files (Conceptual)
File	Purpose
/etc/passwd	Stores user information
/etc/group	Stores group information
/etc/shadow	Stores encrypted passwords

⚠️ Only root can modify these files.

🧾 Linux Commands Explained
🔹 useradd – Create a User
sudo useradd student


What happens:

Adds entry in /etc/passwd

Assigns a UID

User cannot log in until a password is set

Set password:

sudo passwd student

🔹 groupadd – Create a Group
sudo groupadd interns


Add user to group:

sudo usermod -aG interns student


Check groups of a user:

groups student

👑 File Ownership

Every file in Linux has:

Owner → user who owns the file

Group → group associated with the file

Others → everyone else

Check ownership:

ls -l file.txt


Example output:

-rw-r--r-- anmol interns file.txt

🔐 Permissions (Core Concept)
Permission types:
Symbol	Meaning
r	read
w	write
x	execute
Permission levels:
Level	Applies to
Owner	File owner
Group	Group members
Others	Everyone else
Permission string example:
-rwxr-xr--


Breakdown:

- → regular file

rwx → owner (7)

r-x → group (5)

r-- → others (4)

🔢 Numeric Permission Logic
Permission	Value
r	4
w	2
x	1

Examples:

rwx → 4+2+1 = 7

r-x → 4+0+1 = 5

r-- → 4+0+0 = 4

🔧 chmod – Change Permissions
Numeric method (most common)
chmod 755 script.sh


Meaning:

Owner → read, write, execute

Group → read, execute

Others → read, execute

Other examples:

chmod 644 notes.txt
chmod 700 secret.txt

Symbolic method
chmod u+x file.sh   # Add execute permission to owner
chmod g-w file.txt  # Remove write permission from group

🔁 chown – Change Ownership

Change owner:

sudo chown student file.txt


Change owner and group:

sudo chown student:interns file.txt

🧪 Practical Example
Scenario:

User: student

Group: interns

File: report.txt

Goal:

student → read & write

interns → read

others → no access

Commands:
sudo chown student:interns report.txt
chmod 640 report.txt

🔒 Security Notes

Wrong permissions can cause security risks

777 permissions are dangerous

Root user can override all permissions

Permissions protect important system files

🧠 Memory Rule
useradd → creates user
groupadd → creates group
chmod    → controls access
chown    → controls ownership
