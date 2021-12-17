# Git / GitHub ACP

## Version Control

> **Version Control System** , VCS, allows one to revisit multiple versions of a file or set of files by recording changes. With the help of VCS, one can revert a file or project to a previous version, as well as track modifications and modifiers and compare those changes.<br>
> **Local Version Control VCS**, is a single database on the users hard dicks that stores changes to files.<br>
> **Centralized Version Control**, CVS, is a way for a developer team to collaborate on a single file or a set of files. This can be done on a single server storing all of the changes and file version, which can be accessed by various clients. This enables programmers to have visibility of other team members with certain files. <br>
> **Distributed Version Control**, DVCS, allows clients to create mirrored repositores. These data backups can be places easily on the server to replace any lost information <br>
> While DVCS allows for multiple mirrored repositories, programmers working in teams can collaborate with each other in verious wayt to complete a joint project, which allows the use of various simultaneous workflows. 

## Git Explained


### ***Snapshots***

Git is a DVCS that stores data in a file system made up of snapshots. When one saves a changed version of a project, it's called a **commit**. Git creates a snapshot of the file and stores a reference to it.  

### ***Local Operations***

Git mostly relies on local operations because most necessary information can be found in local resources. In turn, since the project's history resides on the local disk, it eliminates the need to fetch history information from the server which makes working on the project even quicker. 

### ***Tracking Changes***

All changes are tracked by Git and Git will always detect file corruption or loss of information in transit. 

### ***Loss of Data***

Git minimizes the possibility of irreversible damage to files, like accidentally lost data. 

### ***States***

Files in Git can be in three main states:

* ***Committed***: Data is securely stored in a local database <br>
* ***Modified***: File has been changed but not committed to the database <br>
* ***Staged***: Flagged a file's changed version to be committed in the next snapshot. 

## History of Git

Created in 2005 by Linus Toralds, chief architect of the Linux kernal. 

## Let's Get Started

### Download Git

Git can be installed in three ways:
1. Install as a package
2. install via another installer
3. Download and compile the source code. 

### Graphical Clients

Git has Graphical User Interface (GUI) tools. However, users can also utilize third-party tools created for particular platforms.

Access for a plethora of GUI clients for Mac, Windows, and Linux by clicking [here](https://git-scm.com/downloads/guis).

### Cloning

You can create a copy of an existing Git repository from a particular server by using the clone command with a repository's URL:

> git clone https://gihub.com/test

By cloning the file, you have copied all versions of all files for a project. By initiating this command, it leads to the creation of a directory called "tese", with an initialized .git directory inside it, which has copies of all versions of all files for the specified project. It also retrieves the newest version of the project. 

To clone a repository into a directory with another name of your choosing, use the following command format: 

> $ git clone https://github.com/test mydirectory

This makes a copy of the target repository in a directory named "mydirectory"

## Workflow

### Local Repository Structure

Local Git repository has three components:

1. Working Directory: The actual files reside here. 
2. Index: The area used for staging
3. Head: Points to the most recent commit

### Saving Changes

All files in a checked out (or working) copy of a project file are either in a tracked or untracked state.

* ***Tracked***: Can be modified, unmodified, or staged; there were part of the most recent file snapshot. <br>
* ***Untracked***: Not in the last snapshot and do not current reside in the staging area. 

### The Life Cycle of File Status

1. After editing a file, Git flags it as modified because of changes made after the previous commit. 
2. You stage the modified file. 
3. Then, you commit staged changes.
4. Check File Status at anytime usinng the command `git status`.

### Tracking and Staging a New File

* ***Single File***: Track one file only by uses the following format: <br>
> git add filename

* ***All Files***: Track all files in a repository by using the followning command: <br>
> $ git add *

After adding a new file called EXAMPLE, you would see information regarding changes to be committed when using the `git status` command:

> $ git status
>
> On branch master
>
> Changes to be committed: 
>
>   (use "git reset HEAD ..." to unstage)

> new file: EXAMPLE

### Committing a File

After staging one or multiple files, you should commit the changes and record what you did within the commit message:

> $ git commit -m "made changes to a,b,c"

### Committing All Changes

> $ git commit -a

### NEXT, Pushing Changes

Next, you would push changes to a remote repository. 

> $ git push origin master

### Stashing Changes

Not ready to commut changes but don't want to lose them either? `git stash` is a great option. This command temporarily removes changes and hides the, give a clean working directory. To continuel use `git stash apply` command to retrieve the hidden changes

## Remote Repositories

The best way to collaborate is on Git projects, which will be on remote repositories. Teams can use remote repositories to push information to and pull data from. 

### Cloned Repositories

As mentioned earlier, for cloned repositories, Git will automatically give the name "origin" to the server from which you cloned and the name "master" to your local branch. 

## Seeing Your Remotes

`git remote` -  will allow you to view the short names, such as "origin", of all specified remote handles. 

`git remote -v` - will allow you to view the remote URLs next to their corresponding short names. 

### Adding Remotes

`git remote add shortname url` - create a new remote Git repository with a short name. 

### Fetching

Fetching entails pulling data that you don't have from a remote project. 

`git fetch [remote-name]` -  is the command format

For cloned, repositories, use the command `git fetch origin` to pull down any new changes that were pushed to the server since you cloned or last fetched from it. 

### Pushing

Push your changes "upstream" for sharing, you would use the following `git push` command format:

> git push [remote-name][branch-name]

Example: <br>
> git push origin master

One can only successfully push chnages upstream if you have write acces for the server from which you cloned, and if someone else has not pushed chnages upstream that you haven't pulled yet. If a collaborator pushed chnages upstream after you ad cloned, the push will not be successful. At this point, one would have to pull new changes and merge them with the branch before you can successfully push your changes upstream. 

### Renaming/Removing Remotes

#### Rename

To rename a remote's short name, use the `git remote rename` command. 

Example: <br>
> $ git remote rename js jane
>
> git remote
>
> origin
>
> jane

In the above example you can see that the remote's short name has been changed from js to Jane. 

#### Remove 

To remove, use the git remote rm command:

Example: <br>
> $ git remote rm jane
>
> git remote
>
> origin


[<---BACK](README.md)
