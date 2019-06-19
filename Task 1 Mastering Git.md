#                   Task 1: Mastering Git

## Solution 1:

### What is VCS ?

The VCS (Version control system) itself justify   i.e., it saves a version of our project after making certain changes without VCS ,this becomes very difficult and confusing as well.

### It's Importance:

Without the help of VCS more than a person cannot work on a single project simultaneously. With a VCS , everybody on the team is able to work on any file at any time. The VCS will later allow  you to merge all the changes into a common version.

Being able to restore the older versions of a file or  project . It prevent you in messing up all the files.

When you save a new versions of a project, your VCS provides you a short description of what was changed ,in  this way it helps you to understand  how your project evolved between versions.

It can behave as “backup”. Every team has  full-blown version in his disk including project complete details but suddenly  their is server break down and also our backup drives fails at time  VCS helps in recovery from local Git repository.  

## Solution 2: 

###  Clone a Git repository

1. On GitHub,      navigate to the main page of the repository.

2. Under the repository name, click  Download

3. In the clone with HTTPs section, click  to copy the clone URL for the repository.

4. Open Git Bash.

5. Change the current working directory to the location where you want the cloned directory to be     made.

6. Type git clone, and then paste the URL you copied in Step 2.

7. Press **Enter**;

    Your local clone will be created.

## Solution 3 :

### Git pull:                                                                                                  

The git pull command is actually a combination of two other commands, git fetch followed by git merge. 

In the first stage of operation git pull will execute a git fetch scoped to the local branch that HEAD is pointed at. Once the content is downloaded, git pull will enter a merge workflow. A new merge commit will be-created and HEADupdated to point at the new commit.

​                                 ![vcs1.PNG](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image002.gif)

​                                  ![vcs2.PNG](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image004.gif)                       

 

 

​                                 ![vcs3.PNG](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image006.gif)

![img](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image007.gif)![img](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image007.gif)

### Git Push:

Git push is most commonly used to publish an upload local changes to a central repository.

Push the specified branch to <remote>, along with all of the necessary commits and internal objects. This creates a local branch in the destination repository. To prevent you from overwriting commits, Git won’t let you push when it results in a non-fast-forward merge in the destination repository. Same as the above command, but force the push even if it results in a non-fast-forward merge. Do not use the --force flag unless you’re absolutely sure you know what you’re doing.

​                                                           ![vsc22.PNG](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image009.gif)

 

​                                                 ![vcs2.3.PNG](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image011.gif)



## Solution 4 :

#### Use the git status command, to check the current state of the repository.

**RUN:**

git status

 

You will see:

**RESULT:**

$ git status

\# On branch master

nothing to commit (working directory clean)

 

 The command checks the status and reports that there’s nothing to commit, meaning the repository stores the current state of the working directory, and there are no changes to record.

We will use the git status, to keep monitoring the states of both the working directory and the repository.

 

## Solution 5 :

### Creating and switching to a branch

·        To create a new branch there is a `git branch` command.

·        After you have created a branch, you need to switch in this branch using a `git checkout`command.

 

​                                    $ git branch <branch_name>

​                                    $ git checkout <branch_name>

 

·        But it is also possible to create a new Git branch and switch in this branch using only one `git checkout` command 

​                                    $ git checkout -b <branch_name>



## Solution 6 :

### Connecting to a remote repository:

When you clone a repository from a remote server, Git automatically remembers this connection for you. It saves it as a remote called "origin" by default.
 In other cases where you started with a fresh local repository, no remote connections are saved. In that situation, we need to connect our local repository to a new remote before we can try some remote interactions:

$ git remote add crash-course-remote 

  

Note: that each remote repository consists of two lines

 The first one is the "fetch URL" which is used for reading access. The second one is the "push URL", used when you want to write data to the remote. In many cases, both URLs are the same. However, you can also use this to define different URLs for read and write access (for security and performance reasons).

Also note that you can connect as many remotes to a local repository as you like. In my case, you saw that another remote named "origin" is already present - although we didn't configure this! This was added by Git automatically when we cloned from the remote server (which we did at the beginning of this book). Exactly as with the "master" branch, the name "origin" for this remote is only a naming convention. It's just a normal remote repository like any other.



##  Solution 7 :

### Merging two branches:

Git merge will combine multiple sequences of commits into one unified history. In the most frequent use cases

. In these scenarios, git merge takes two commit pointers, usually the branch tips, and will find a common base commit between them. Once Git finds a common base commit it will create a new "merge commit" that combines the changes of each queued merge commit sequence.

Say we have a new branch feature that is based off the masterbranch. We now want to merge this feature branch into master.

![https://wac-cdn.atlassian.com/dam/jcr:86eba9ec-9391-45ea-800a-948cec1f2ed7/Branch-2.png?cdnVersion=411](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image013.gif)

Invoking this command will merge the specified branch feature into the current branch, we'll assume master. Git will determine the merge algorithm automatically (discussed below).

![https://wac-cdn.atlassian.com/dam/jcr:83323200-3c57-4c29-9b7e-e67e98745427/Branch-1.png?cdnVersion=411](file:///C:\Users\Ayushman\AppData\Local\Temp\msohtmlclip1\01\clip_image015.gif)

Merge commits are unique against other commits in the fact that they have two parent commits. When creating a merge commit Git will attempt to auto magically merge the separate histories for you. If Git encounters a piece of data that is changed in both histories it will be unable to automatically combine them. This scenario is a version control conflict and Git will need user intervention to continue. 

##  Solution 8 :

### Resolving merging conflicts:

If the two branches you're trying to merge both changed the same part of the same file, Git won't be able to figure out which version to use. When such type of situation arises, it stops right before the merge commit so that you can resolve the conflicts manually.

The great part of Git's merging process is that it uses the familiar edit/stage/commit workflow to resolve merge conflicts. When you encounter a merge conflict, running the git status command shows you which files need to be resolved. For example, if both branches modified the same section of Goodmoring.py, you would see something like the following:

```
On branch master
Unmerged paths:
(use "git add/rm ..." as appropriate to mark resolution)
both modified: Goodmorning.py
```

##  Solution 9 :

### Committing changes:

We can commit changes in our file by doing following steps

1. Install and configure Git locally.

2. Create your own local clone of a repository.

3. Create a new Git branch.

4. Edit a file and stage your changes.

5. Commit your changes.

6. Push your changes to GitHub.

7. Make a pull request.

8. Merge upstream changes into your fork.

9. Merge changes on GitHub into your local clone.

## Solution 10 :

### Stash changes:

The git stash command takes your uncommitted changes and, saves them away for later use, and then reverts them from your working copy. For example:

```
$ git status
On branch master
Changes to be committed:
new file: style.css
Changes not staged for commit:
modified: index.html
$ git stash
Saved working directory and index state WIP on master: 5002d47 our new homepage
HEAD is now at 5002d47 our new homepage
$ git status
On branch master
nothing to commit, working tree clean
```

 

At this point you're free to make changes, create new commits, switch branches, and perform any other Git operations; then come back and re-apply your stash when you're ready.

 

You can re-apply previously stashed changes with git stash pop:

```
$ git status
On branch master
nothing to commit, working tree clean
$ git stash pop
On branch master
Changes to be committed:
new file: style.css
Changes not staged for commit:
modified: index.html
Dropped refs/stash@{0} (32b3aa1d185dfe6d57b3c3cc3b32cbf3e380cc6a)
```

Popping your stash removes the changes from your stash and reapplies them to your working copy.

Alternatively, you can reapply the changes to your working copy and keep them in your stash with git stash apply:

```
$ git stash apply
On branch master
Changes to be committed:
new file: style.css
Changes not staged for commit:
modified: index.html
```

This is useful if you want to apply the same stashed changes to multiple branches.

 The basics of stashing, there is one caveat with git stash you need to be aware of ,by default Git won't stash changes made to untracked or ignored files.

 