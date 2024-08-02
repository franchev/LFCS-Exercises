## Standard File Permissions

run the ls -l command to view permission about a file or directory. This link: https://phoenixnap.com/kb/linux-file-permissions provides a good explanation on linux permission. 

Let's focus on the example of the permissions for a file

```bash
-rw-r--r--       
```

* The first character is the file type and can be either: a regular file (-), a directory (d), a symbolic link (i), character device (c), Socket File (s), Pipe (p), a Block Device (b)
* The next three characters is the user's (owner's) permissions.
* The next three represents the group's permissions
* the last three represents permissions for all other users


These are the types of permissions

* -: means no permission
* Read (r) the read permission lets users view the contents of a file or list the contents of a directory
* Write (w) The write permission let users modify file's contents or add, remove, or rename files in a directory
* Execute (x) The execute permission allows users to execute a file or enter a directory. For files, the execute permission is required to execute a program or scrit. For directories, the execute permission is required to access contents of the directory.


Special permissions worth mentioning

* setuid (Set User Id): Allows a user to execute a file with the permissions of the file's owner, rather than the permissions of the user executing the file
* setgid (Set Group ID): allows a user to execute a file with the permissinos of the file's group, rather than the permission of the user executing the file.
* Sticky bit: when applied to a directory, ensures that only the owner of a file within that directory or the root user can delete or rename the file, even if other users have write permissions on the directory.

Octal Notation

* You can use octal notation to set permissions. It represents permissions using a 3 digit number where each digit corresponds to the sum of the permissions for the owner, group, and others, respectiveily. Each permission type is assigned a numeric value: read(4), write (2), and execute (1). Basic example 755 means read, write, and execute permissions for the owner, then read and execute permissions for the group and other users.




### Set the group on this file /home/testuser/file1.txt to allusers


<details><summary>Answer</summary>

```bash
chgrp allusers /home/testuser/file1.txt

```

</details>

### Change the owner on this file /home/testuser/file1.txt to testuser2


<details><summary>Answer</summary>

```bash
sudo chown testuser2 /home/testuser/file1.txt               # only the root user can change the owner of a file
ls -l /home/testuser/file1.txt                              # view the permission on the file

```

</details>


### Find files and directories that were modified a minute ago in the /var directory


<details><summary>Answer</summary>

```bash
find /var -cmin -1

```

</details>

### Find files and directories in the /var/log directory that only group can write to


<details><summary>Answer</summary>

```bash
find /var/log/ -perm /g=w

```

</details>

### Find file that has an octal permission of 442 in the current directory


<details><summary>Answer</summary>

```bash
find -perm 442

```

</details>

### Find file that has a size of 200k in the /var/log directory


<details><summary>Answer</summary>

```bash
find /var/log -size 200k

```

</details>


### Find all files in the /usr directory with the size between 0MB and 5MB

<details><summary>Answer</summary>

```bash
sudo find /usr -type f -size +0M -size -5M

```

</details>


### Set Setuid, Setgid, and sticky bit permission on a directory named /home/testuser1/testdir


<details><summary>Answer</summary>

```bash
chmod u+s /home/testuser1/testdir   # Setuid
chmod g+s /home/testuser1/testdir   # setGid
chmod +t /home/testuser1/testdir    # sticky bit

ls -l /home/testuser1               # to view the permissions set
```

</details>




### Remove the write permission of the group from /home/testuser/file1.txt


<details><summary>Answer</summary>

```bash
chmod g-w /home/testuser/test1.txt

```

</details>