# Archive and compression

Let's learn how to use tools such as tar (tape archive) and gzip to archive and compress files. We'll also use the same tools to unpack and uncompress files. You might come across term such as tarball which means a set of files packaged together into a single file.

Tools to zip and unzip files

* gzip      -> gunzip
* bzip2     -> bunzip
* xz        -> unxz
* zip       -> unzip


### create a tar file named sites.tar of the /sites


<details><summary>Answer</summary>

```bash
tar cfP sites.tar /sites        #notice the P parameter or --absolute-names to not strip leading slashes from file names when creating archives (you might need to use sudo if you get permission denied.)

```

</details>

### create a compressed tar archive file named sites.tar.gz of the /sites


<details><summary>Answer</summary>

```bash
tar cfPz sites.tar /sites        #the z flag add compression to tar

```

</details>


### using tar list the content of the sites.tar.gz


<details><summary>Answer</summary>

```bash
tar --list -f sites.tar.gz 

tar tf sites.tar.gz             # with tar you can use the dashes or not (t is the same as --list, sorry for the confusion, go ask tar why)

```

</details>


### extract contents of sites.tar.gz to /tmp directory


<details><summary>Answer</summary>

```bash
tar xf sites.tar.gz -C /tmp                 # you can also use --directory instead of -C
```

</details>
