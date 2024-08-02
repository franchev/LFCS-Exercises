# Learn about hard links and soft links

## Hard links

Here let's learn a little bit about Hard links and why we use them in Linux. Hard links can be used to create multiple references to a single file. Here are some nice bullet points obtained from this link (https://www.geeksforgeeks.org/soft-hard-links-unixlinux/) regarding hard links: 

* Hard links point to the same inode value of the original file
* Each hard linked file is assigned the same Inode value as the original. As a result, they reference the same physical file location. They are flexible and remain linked even if the original or linked files are moved throughout the file system. They are unable to cross different file systems.
* Links have file contents
* Removing a link reduces the link count and does not impact other links
* If you change the filename of the original file, then the hard links will continue to work.
* If original file is removed then the link will still show the content of the file
* The size of the hard link file is same as the original file
* You can only hard link to files, not directories




### Create a hard link of this file /home/testuser/file1.txt to this location /home/testuser2/file1.txt

<details><summary>Answer</summary>

```bash
stat /home/testuser/file1.txt                           # To view the number of links (currently might be just 1)

ln /home/testuser/file1.txt /home/testuser2/file1.txt   # ln [original filename] [link name]

stat /home/testuser/file1.txt                           # To view the number of links (will now update to show that there are 2 links)
```

</details>


## Soft links

Here let's learn a little bit about soft links and why we use them in Linux. Soft links are similar to file shortcut feature which is used in Windows. Here are some nice bullet points obtained from this link (https://www.geeksforgeeks.org/soft-hard-links-unixlinux/) regarding soft links: 

* Soft links are nothing more than paths pointing to a file (a shortcut)
* Each soft linked file contains a separate Inode value that points to the original file. 
* Soft links can be linked across different file systems. However, if the original file is deleted or moved, the soft linked file will not work correctly (called hanging link).
* Soft link contains the path for the original file and not the contents
* Soft links can link to a directory
* The size of the soft link is equal to the length of the path of the original file we gave.




### Create a soft link of this file /home/testuser/file1.txt to this location /home/testuser2/file1.txt

<details><summary>Answer</summary>

```bash

ln -s /home/testuser/file1.txt /home/testuser2/file1.txt    # ln -s [original filename] [link name]


readlink /home/testuser2/file1.txt                          # to read where the link is pointing to
```

</details>
