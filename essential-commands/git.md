# Git commands

Git is an open-source version control system (VCS) which is used for software engineers to collaborate on projects.

Here are some good resources to learn git:

* https://learngitbranching.js.org/
* https://ohmygit.org/
* https://www.atlassian.com/git/tutorials/what-is-git


Below, let's learn some git terms and commands.

* repository: is located insite the .git/ directory inside a project. It is used to track changes made to files in your project. This will build a history over time, making it possible for you to revert and push new changes. By deleting the .git directory inside of your project, you would have deleted your project's history.
* log: logs are committed snapshots. With the git log command you can view project history and search for specific changes.
* commit: In a git repository records a snapshot of all the tracked files in your directory
* branches: Git branches are a pointer to a snapshot of your changes. A branch is a new/separate version of the main repository. Think of it as a separate workspace for your code.
* clone: Use to target an existing repository and create a clone, or copy of the target repository.
* merge: git merge is a way to combine work from two different branch. Merging creates a special commit with two unique parents. Creating a combination of the commits.
* rebase: this is another way to combine work between branches. Rebasing takes a set of commits, copies them, and put them down. This is a good way to make a nice linear sequence of commits. The commit log / history of the repository will look cleaner.
* HEAD: this is the symbolic name of the currently checked out commit. This is the current commit you are working on top of. HEAD always points to the most recent commit. HEAD refers to the currently checked-out branch's latest commit. However, in a detached HEAD state, the HEAD does not point to any branch, but instead points to a specific commit or the remote repository. In a git detached HEAD state allows you to explore any commit in your commit history. You can run code change experiments. You can test out any desired code changes on a specific commit without worrying whether it will affect any branch
* Refs: a ref is an indirect way of referring to a commit. They are stored in the .git/refs directory. the .git/refs/heads directory defines all the local branches in your repository. Here are some important refs:
    * Special refs
        * HEAD -> The currently check-out commit/branch
        * FETCH_HEAD -> the most recently fetched branch from a remote repo
        * ORIG_HEAD -> A backup reference of the HEAD before drastic changes occurs.
        * MERGE_HEAD -> the commits that you're merging into the current branch with git merge
        * CHERRY_PICK_HEAD -> the commit that you are cherry-picking
    * Relative refs: You can refer to commits relative to another commit.
        * ~: the ~ character lets you reach parent commits (git show HEAD~1). Moving upwards a number of times.
        * ^: The caret character follow the first parent of a merge commit. (git show HEAD^: parent of current branch/commit). You can use the caret character to move more than one generation: (git show HEAD^^: grandparent of current branch/commit). Moving upwards a commit at a time.
* reverse changes: Git gives you the ability to revert changes. A couple of commands that you can use to undo changes are git reset and git revert. 
    * git reset reverses changes by moving a branch reference backwards in time to an older commit (better used for local branches, not suited for remote branches.)
    * git revert is better suited for changes that will be shared with others.
* Cherry-pick: allows you to move commits(s) wherever you like.
* local vs remote: when you create a branch, they are locally created. Only you can see local branches, it only exist on your local machine. Eventually, you'll want to sync your commits that are on your machine to a remote location. Remote branch is a branch that is located on a remote location (in most cases origin). Push your newly created local branch to origin. This will now be available to other users.

### initialize a new git repository in a project directory


<details><summary>Answer</summary>

```bash
cd project
git init                    
```

</details>

### create a file, stage it, then commit it to the main branch


<details><summary>Answer</summary>

```bash
touch file1.txt
git add file1.txt
git commit -m 'adding file1.txt'            # the -m flag means that you are adding a comment to your commit                  
```

</details>

### create a new branch name hotfix and switch to it.


<details><summary>Answer</summary>

```bash
git checkout -b hotfix                      # the -b flag creates the branch and switch to it                    
```

</details>


### make a change and commit it in the hotfix branch. Then merge the hotfix branch into the main branch


<details><summary>Answer</summary>

```bash
git checkout hotfix
touch file2.txt
git commit -m 'adding file2'
git checkout main
git merge hotfix             
```

</details>


### checkout a new branch named bugfix, commit a change. Return to the main branch, then make a new commit. Rebase bugfix branch onto main.


<details><summary>Answer</summary>

```bash
git checkout bugfix
git commit -m 'fixing silly bug'
git checkout main
git commit -m 'adding something fun'
git checkoug bugfix
git rebase main
```

</details>


### checkout to the main branch, and detach the HEAD from the main branch


<details><summary>Answer</summary>

```bash
git checkout main
git log                 # copy the hash of a commit
git checkout commithash # This will now point HEAD to the commit hash. You can also just specify enough characters of the hash until git sees it as a unique identifier for the commit (normally the first six characters or so)

```

</details>


### checkout the parent commit of hotfix


<details><summary>Answer</summary>

```bash
git checkout hotfix
git checkout HEAD^

```

</details>


### Delete the hotfix branch 


<details><summary>Answer</summary>

```bash
git branch -d hotfix
error: Cannot delete branch 'hotfix' checked out at /project            # this error indicates that the branch that you are trying to delete is the checked out branch

git checkout main

git branch -d hotfix                                                    # now it'll delete the local branch after we checkout to main
git branch -D hotfix                                                    # this will delete the branch  whether tracking or non-tracking (forcefully)
git branch -rd <remote>/branchname                                      # delete a remote-tracking branch

```

</details>


### Create a new branch name bugfix & push it to the remote location


<details><summary>Answer</summary>

```bash
git checkout -b bugfix
git push -u origin bugfix

```

</details>


### pull a remote branch


<details><summary>Answer</summary>

```bash
git pull origin mynewbranch

```

</details>

### cloning a repository


<details><summary>Answer</summary>

```bash
git clone <repository location/name.git>

```

</details>