<h1> Essential Commands 20%</h1>

<h2>Understanding Essential commands</h2>
<li>Basic Git Operations</li>
<li>Create, configure, and troubleshoot services</li>
<li>Monitor and troubleshoot system performance and services</li>
<li>Determine application and service specific constraints</li>
<li>Troubleshoot diskspace issues</li>
<li>Work with SSL certificates</li>
<br>


<h2>How to copy, move, delete files and directories</h2>

<p> Linux fileSystem is a tree with the root directory known as the top directory represented by "/"</p>

<h3>List files in current and different locations</h3>

<details><summary>Answer</summary>

```bash
# current location
ls -la

# different location
ls -l /var/log
```

</details>

<h3> Change between directories</h3>

<details><summary>Answer</summary>

```bash
cd /var/log                 # cd to a absolute path
cd ..                       # take us one directory up (.. is the parent directory of the current location)

```

</details>

<h3> Create and delete a file name text.txt</h3>

<details><summary>Answer</summary>

```bash
touch text.txt              # will create an emtpy file named text.txt
rm -rf text.txt             # removes a file without prompting

```

</details>

<h3> Create and delete a directory named dir1</h3>

<details><summary>Answer</summary>

```bash
mkdir dir1                  # make a directory named dir1
rmdir dir1                  # removes a directory without any children
rm -rf dir1                 # removes a directory recursively
```

</details>

</details>

<h3> Create this directory /tmp/tests/test1 even though the directory /tmp/tests does not exist. Use the mkdir --help to find the argument that allows you to make parent directories as needed</h3>

<details><summary>Answer</summary>

```bash
mkdir --help                # view help for the mkdir command
mkdir -p /tmp/tests/test1   # -p, --parents no error if existing, make parent directories as needed
```

</details>

<h3> Copy files</h3>

<details><summary>Answer</summary>

```bash
cp file1 file2              # copy file1 to file2
cp file1 /home/testuser/    # copy file to /home/testuser/ directory
cp -r dir1 /home/testuser/  # Copies dir1 recursively to /home/testuser/
```

</details>

<h3> Copy directory /tmp/files to /home/testuser</h3>

<details><summary>Answer</summary>

```bash
cp -r /tmp/files /home/testuser/      # notice the -r meaning recursively, this is required when copying directories
```

</details>

<h3> Move files</h3>

<details><summary>Answer</summary>

```bash
mv file1 file2              # will rename file1 to file2
mv file1 /home/testuser/    # will move file1 to /home/testuser/
```

</details>

<h3> Move the content of the directory /home/testuser/tmp excluding itself to /home/testuser/backup </h3>

<details><summary>Answer</summary>

```bash
mv /home/test/tmp/* /home/testuser/backup/
```

</details>


<h2>Hard links</h2>

<p> Here let's learn a little bit about Hard links and why we use them in Linux. Hard links can be used to create multiple references to a single file. Here are some nice bullet points obtained from this link (https://www.geeksforgeeks.org/soft-hard-links-unixlinux/) regarding hard links: 

* Hard links point to the same inode value of the original file
* Each hard linked file is assigned the same Inode value as the original. As a result, they reference the same physical file location. They are flexible and remain linked even if the original or linked files are moved throughout the file system. They are unable to cross different file systems.
* Links have file contents
* Removing a link reduces the link count and does not impact other links
* If you change the filename of the original file, then the hard links will continue to work.
* If original file is removed then the link will still show the content of the file
* The size of the hard link file is same as the original file
* You can only hard link to files, not directories




<h3>Create a hard link of this file /home/testuser/file1.txt to this location /home/testuser2/file1.txt</h3>

<details><summary>Answer</summary>

```bash
stat /home/testuser/file1.txt                           # To view the number of links (currently might be just 1)

ln /home/testuser/file1.txt /home/testuser2/file1.txt   # ln [original filename] [link name]

stat /home/testuser/file1.txt                           # To view the number of links (will now update to show that there are 2 links)
```

</details>

<h2>Soft links</h2>

<p> Here let's learn a little bit about soft links and why we use them in Linux. Soft links are similar to file shortcut feature which is used in Windows. Here are some nice bullet points obtained from this link (https://www.geeksforgeeks.org/soft-hard-links-unixlinux/) regarding soft links: 

* Soft links are nothing more than paths pointing to a file (a shortcut)
* Each soft linked file contains a separate Inode value that points to the original file. 
* Soft links can be linked across different file systems. However, if the original file is deleted or moved, the soft linked file will not work correctly (called hanging link).
* Soft link contains the path for the original file and not the contents
* Soft links can link to a directory
* The size of the soft link is equal to the length of the path of the original file we gave.




<h3>Create a soft link of this file /home/testuser/file1.txt to this location /home/testuser2/file1.txt</h3>

<details><summary>Answer</summary>

```bash

ln -s /home/testuser/file1.txt /home/testuser2/file1.txt    # ln -s [original filename] [link name]


readlink /home/testuser2/file1.txt                          # to read where the link is pointing to
```

</details>