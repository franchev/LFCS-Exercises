## Using the find command to search for files and directories


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


### Find all files in the /usr that are both 200K and with permission 0442

<details><summary>Answer</summary>

```bash
sudo find /usr -type f -size 200k -o -perm 0442

```

</details>
