# Important HDFS and Linux Commands for Data Engineers

This README provides essential Linux and HDFS commands, ideal for beginners entering the Data Engineering domain.

Linux Commands

## 1. Present Working Directory (pwd)

> pwd: Displays the current directory.

## 2. User Information (whoami)

whoami: Displays the username of the current user.

Linux Directory Structure

Linux follows a tree-like structure.

/: Topmost directory, parent of all directories.

Terminology:

Directory (Linux) = Folder (Windows)

## 3. Change Directory (cd)

cd ~ : Navigate to the home directory.

cd .. : Move to the parent directory.

cd - : Return to the previous directory.

cd ../.. : Move up two levels in the directory tree.

cd . : Stay in the current directory.

Path Types

Absolute Path: Starts from the root /.

Example: cd /data

Relative Path: Relative to the current location.

Example: cd ../departments/

## 4. List Files and Directories (ls)

ls: Lists files and directories in the current location.

Color Coding:

Blue: Directories

Green: Executables

Black: Normal files

Common Options:

ls -l: Detailed list.

ls -lt: Newest files first.

ls -ltr: Oldest files first.

ls -a: Includes hidden files (start with .).

ls -R: Recursively lists all files and directories.

ls -latR /data: Combination of options.

## 5. Create Empty File (touch)

touch filename: Creates an empty file or updates its timestamp.

File Permissions:

Read: 4

Write: 2

Execute: 1

Example: 6 6 4 means:

Owner: Read & Write

Group: Read & Write

Others: Read

Example:

chmod 777 testfile: Grants rwx to all entities (owner, group, others).

## 6. Create and Remove Directories/Files

mkdir dir: Create a directory.

rmdir dir: Remove an empty directory.

rm filename: Remove a file.

rm -R dir: Remove a directory and its contents recursively.

## 7. Copy Files and Directories (cp)

cp file1 file2: Copy file1 to file2.

cp file1 dir: Copy file1 to a directory.

cp -R dir1 dir2: Recursively copy dir1 to dir2.

## 8. Move and Rename Files (mv)

mv file1 file2: Rename file1 to file2.

mv file dir: Move file to a directory.

## 9. Edit Files (vi)

Steps to Edit a File:

vi filename: Open file in editor.

Press i: Enter insert mode.

Write content.

Press Esc: Exit insert mode.

Type :wq: Save and quit.

## 10. Read Content from Files (cat)

cat filename: Display file content.

cat > file: Create a file and add content.

cat >> file: Append content to a file.

Merge Files:

cat file1 file2 >> mergedfile: Merge content of file1 and file2 into mergedfile.

Disk Usage:

du -h /data: Display disk usage in human-readable format.

## 11. Additional Commands

wc filename: Count words in a file.

head filename: Display the first few lines of a file.

grep pattern filename: Search for a pattern in a file.

# HDFS Commands

## 1. List Files and Directories

hadoop fs -ls: List files in HDFS.

Examples:

hadoop fs -ls /: List root directory.

hadoop fs -ls -t -r /: List files, newest first.

hadoop fs -ls -S -h /: List files by size in human-readable format.

## 2. Create and Remove Directories

Create:

hadoop fs -mkdir /user/username/dir: Create a directory.

hadoop fs -mkdir -p /user/username/dir1/dir2: Create nested directories.

Remove:

hadoop fs -rmdir dir: Remove an empty directory.

hadoop fs -rm -R dir: Remove a directory and its contents recursively.

## 3. File Transfers

Local to HDFS:

hadoop fs -put localfile hdfsdir/: Upload file to HDFS.

hadoop fs -copyFromLocal localfile hdfsdir/

HDFS to Local:

hadoop fs -get hdfsfile localdir/

hadoop fs -copyToLocal hdfsfile localdir/

HDFS to HDFS:

hadoop fs -cp source destination

## 4. View and Check Files

View Content:

hadoop fs -cat file: Display file content.

hadoop fs -tail file: Display last few lines of a file.

File System Check:

hdfs fsck file -files -blocks -locations: Perform a file system check.

## 5. Disk Usage and Space

hadoop fs -df -h /: Show disk space in human-readable format.

