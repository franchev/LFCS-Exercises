# Working with files

There are a sets of tools that are useful to view, edit, manipulate, search files in linux. Please review:
* `cat command`: to print the content of a file to standard output
* `sed command`: to manipulate strings in a file
* `grep command`: to search for specific strings in a file
* `egrep command`: extended global regular expression (you can also use grep -E to gain this functionality)
* `less and more commands`: to view and search through a file
* `vim editor`: to edit a file
* `cut command`: to print specific fields from a file
* `sort command`: To sort strings
* `uniq command`: to print unique string (beware the strings must be consecutive)
* `diff command`: to view the difference between files

Regular expression (RegEX) is also very useful when manipulating files and strings. Please review this tutorial: https://www.guru99.com/linux-regular-expressions.html

Below we'll explore some exercises


### View the top 5 lines of a file


<details><summary>Answer</summary>

```bash
head -5 filename

```

</details>

### Find lines in a file that contains the word password case insensitive


<details><summary>Answer</summary>

```bash
grep -iw 'password' /etc/passwd

```

</details>

### Find file that has an octal permission of 442 in the current directory


<details><summary>Answer</summary>

```bash
find -perm 442

```

</details>

### In this file can you extract the 2nd column (use any tools of your choosing)
us-states-capitals.txt
us;ma;boston
us;ny;buffalo
us;nh;concord


<details><summary>Answer</summary>

```bash
cut -d ';' -f 2 us-states-capitals.txt

```

</details>


### change all the words canada with the word us in a file 

<details><summary>Answer</summary>

```bash
sed 's/canada/us/g' file1.txt           # this will only output the potential change, but won't make the change. Notice the g (it means global, if you don't pass that, sed will only parse the first string matching the string in the search)
sed -i 's/canada/us/g' file1.txt        # the -i parameter mean in place, so it'll change the actual file.
sed -i 's/canada/us/gi' file1.txt       # will ignore the case sensitivity (notice the i after the g at the end of the sed command)
sed -i '100,500s/canada/us/g' file1.txt # will only change from line 100 - 500

```

</details>


### Count how many numbers start with the number 3 in file1.txt

<details><summary>Answer</summary>

```bash
grep -c '^2' file1.txt
egrep '^2' file1.txt | wc               # wc (word count) can also be used in this case to count number of lines, words, and bytes contained in a file

```

</details>


### Get the last 100 lines from a file

<details><summary>Answer</summary>

```bash
tail -n 100 file.txt

```

</details>

