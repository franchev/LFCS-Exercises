<h1>LFCS (Linux Foundation Certified System Administrator) Exercises </h1>

<h2>Introduction </h2>

Welcome, I'm currently studying to get the LFCS certification. Since this is a hands-on certification, I'm documenting things to practice here. I've also documented information about the exam. Links will also be provided. 

You can find information about the exam here: https://training.linuxfoundation.org/certification/linux-foundation-certified-sysadmin-lfcs/


My tactic while taking the exam was to at least visit each question once. Then I would attempt right away to do the questions that I knew. If I didn't get it right on the first go, I would attempt once again. If I didn't get it then, I would move on to the next question and mark the unfinished one in the notepad (provided in the exam browser page.)

<h2>Exam Detail</h2>
  
1. Length: 2 hours
1. Amount of questions: 15-20 performance-based tasks
1. Cost: $300
1. passing score: 66%
1. You'll get your grade within 36 hours

<h2>Learning tools</h2>

1. udemy: https://www.udemy.com/course/linux-foundation-certified-systems-administrator-lfcs
2. killercoda for interative labs: https://killercoda.com/lfcs
3. kodekloud for interactive labs: https://ullabs.kodekloud.com/courses/udemy-linux-foundation-certified-system-administrator-lfcs/

<h2> Things that will help you during the exam</h2>

<p> You can access help and manual for commands</p>

1. Most if not all commands have a --help flag (i.e ls --help)
2. man pages are also available (i.e man journalctl)
3. apropos shows the manual sections that contain any of the keywords specified by the Keyword parameter in their title. 
```bash
    # regarding apropos, when using for the first time, you need to create the database
    sudo mandb
```
4. Remember auto-completion using tab



<h2>Contents</h2>

* [Essential commands 20%](https://github.com/franchev/LFCS-Exercises/blob/main/essential-commands) 
    * [Basic Git Operations](https://github.com/franchev/LFCS-Exercises/blob/main/essential-commands/git.md)
    * Create, configure, and troubleshoot services
    * Monitor and troubleshoot system performance and services
    * Determine application and service specific constraints
    * Troubleshoot diskspace issues
    * [Work with SSL certificates](https://github.com/franchev/LFCS-Exercises/blob/main/essential-commands/ssl.md)
* [Operations Deployment 25%](https://github.com/franchev/LFCS-Exercises/blob/main/operations-deployment) 
* [Users and Groups 10%](https://github.com/franchev/LFCS-Exercises/blob/main/users-and-groups)
    * [Create and manage local user and group accounts](https://github.com/franchev/LFCS-Exercises/blob/main/users-and-groups/manage-local-users-and-group-accounts.md)
    * [Manage personal and system-wide environment profiles](https://github.com/franchev/LFCS-Exercises/blob/main/users-and-groups/manage-profiles.md)
    * [Configure user resource limits](https://github.com/franchev/LFCS-Exercises/blob/main/users-and-groups/configure-user-resource-limits.md) 
    * [Configure and manage ACLs](https://github.com/franchev/LFCS-Exercises/blob/main/users-and-groups/configure-manage-acls.md) 
    * [Configure the system to use LDAP user and group accounts](https://github.com/franchev/LFCS-Exercises/blob/main/users-and-groups/configure-ldap.md)
* [Networking 25%](https://github.com/franchev/LFCS-Exercises/blob/main/networking)
* [Storage 20%](https://github.com/franchev/LFCS-Exercises/blob/main/storage)
