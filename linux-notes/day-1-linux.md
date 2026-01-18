🔹 Linux Day 1 – Commands & Explanation
📁 1️⃣ Filesystem & Navigation
🔹 pwd — Print Working Directory
Shows where you are in the filesystem.
pwd
📌 Example output:
/home/anmol/linux_day1/practice
🔹 ls — List Files & Folders
Displays contents of a directory.
ls
Common options:
ls -l    # detailed list
ls -a    # show hidden files
ls ../   # list parent directory
ls path  # list specific folde
🔹 cd — Change Directory
Moves between folders.
cd foldername
cd ..     # move one level up
cd ~      # go to home directory
cd /      # go to root
📂 2️⃣ Folder Creation
🔹 mkdir — Make Directory
Creates a new folder.
mkdir test
Create multiple folders:
mkdir day1 day2 day3
Safe creation:
mkdir -p test
📄 3️⃣ File Creation
🔹 touch — Create File
Creates an empty file.
touch file.txt
Multiple files:
touch a.txt b.txt
🔹 echo — Create file with content
Writes text into a file.
echo "Hello Linux" > hello.txt
Append text:
echo "New line" >> hello.txt
📋 4️⃣ Copy Files & Folders
🔹 cp — Copy
Copies files.
cp file1.txt file2.txt
Copy file to another folder:
cp file.txt ../backup/
🔹 cp -r — Copy Folder
Required to copy directories.
cp -r day1 day1_backup
📌 -r = recursive (copy everything inside)
🔀 5️⃣ Move & Rename
🔹 mv — Move or Rename
Same command for both actions.
Rename file:
mv old.txt new.txt
Move file:
mv file.txt ../day2/
Move folder:
mv folder1 folder2/
❌ 6️⃣ Delete Files & Folders
🔹 rm — Remove File
rm file.txt
🔹 rmdir — Remove Empty Folder
rmdir empty_folder
🔹 rm -r — Remove Folder with Files
rm -r foldername
⚠️ Be careful — deletion is permanent.
🔍 7️⃣ Find File Location
🔹 find — Search File
Finds file anywhere.
find ~ -name "filename.txt"
🧠 8️⃣ Path Shortcuts (VERY IMPORTANT)
Symbol	Meaning
/	      root
~	      home directory
..	    parent directory
.	      current directory


