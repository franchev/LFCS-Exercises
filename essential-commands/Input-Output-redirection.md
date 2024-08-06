# IO Redirection

Learn about Iput Output Redirection in Linux. This link has some good information: https://www.geeksforgeeks.org/input-output-redirection-in-linux/. To summarize:

* When a command is executed in Linux, it can take an input, give output, or do both. You can use redirection to perform additional functionalities. For example, you can redirect the output of a command to a file or pipe it to another command for additional functionalities.

* You will come across: standard output (STDOUT), standard error (STDERR).

* Types of Redirection:
    * Overwrite redirection: to store/save output of a command
        *  ">" standard output
        * "<" standard input
        * example:
            * cat  > file.txt
              linux is good
            * cat < file.txt
              Welcome
    * Append Redirection: Append the output to a file without overwritting it
        * ">>" Standard output
        * "<<" standard input
    * Merge Redirection: allows you to redirect the output of a command or a program to a specific file descriptor instead of standard output. The syntax for using this is ">&" operator followed by the file descriptor number.
        * Error redirection: command 2> error.txt


Please see some examples below:


### save script normal output to stdout.txt


<details><summary>Answer</summary>

```bash
./scriptname > stdout.txt
```

</details>


### save script normal and error output to alloutput.txt


<details><summary>Answer</summary>

```bash
./scriptname > stdout.txt 2>&1          # notice 2>&1, this means output standard error(stderr) to standard output (stdout)
```

</details>


### save script errors output to errors.txt


<details><summary>Answer</summary>

```bash
./scriptname 2> errors.txt          
```

</details>


### append the content of file1.txt to file2.txt without overwritting file2.txt


<details><summary>Answer</summary>

```bash
cat file1.txt >> file2.txt                     
```

</details>

