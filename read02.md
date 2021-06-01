# Version Contol

Version Contol is a system that records any changes or modifications on a file or a project directory so we can review these versions and decide whether if we want to keep these changes or refuse them.

# Local Version Control 
It is installed on alocal machine and has a one database to store all versions of project modifications.

#  Centralized Version Control

Because the team members working on their own project to share their files ,their modifications and their works, they need a system to store all project modifications. This system is called CVCS . It allows administrators to review the changes made by team members and give them more control on the team members priviledges.


#  Distributed Version Control
The weakness of CVCS is there is a one place -which is a server - for storing all the changes made by the team members.
What if that server goes down or the central database hard disk was damaged , then all works will be lost.
So the solution for this problem is the DVCS.

DVCS allows team members to create snapshots of their repositories and by this way if there is any lost on a server these snapshots can be easily places on that server and keeping the work safe.

#  What is the Git

* Snapshots:
Git is DVCS that stors the snapshots of the team members on a file system. if you save the changes of your projects -commit it- then Git create snapshot of it and create a reference to it.if you do not do anything to your project it store a reference to previouse version of your work.

* Local Operations :
The important information can be found on a local machine so Git relies on local operations .
You can do anything without needing to be online or on VPN.

* Tracking Changes  :
Git works as a Gatekeeper.It detects any changes or any corruption to any file. It tracks any changes made on any project.

* Loss of data :
Loss of your commited data on git is like an impossible by any way.


* State :
The files on Git have three main states
1. commited
2. modified
3. staged

![Three States](https://i.stack.imgur.com/kslSd.png)



# Graphical Clients
There are a Graphical User Interface tools for Git which  users can use it instead of CLI.


# Initial Customization

* Configuration of Variables

 `git config` is a tool that allows the setting of configuration variables.

* Identity Setting
 To set a user name and a user email we do the following in the CLI 
  ` git config --global user.name "Jane Smith" `

   `git config --global user.email "example@email.com" `

* Default Text Editor
 To set a specific text editor like emacs we write the following command :
  > ` git config --global core.editor emacs `

  * Check Settings
  To check settings we write
    ` git config --list`
   
   * Getting Help
   To get more info about any command say it is a cd cooomand you can write:

  ` git help cd `

  # Setting up a Git Repository

   * Importing
   To import an existing project to the git we write the following commands:

   `cd directoryName`
   `git init`
Till now the tracking files has not started yet.
 
 we need to write the following commands to start tracking the files.
  
` git add *.c `
`git add LICENSE`
`git commit -m “any message here” `

* Cloning

we can clone a copy of any public repository by writing this command :
`git clone https://github.com/test `

this will copy alll versions of all files inside that repository 

to clone a repository and rename it to any name you choose :

`git clone https://github.com/test directoryName `


# Workflow

* Local Repository Structure

The local Git repository has three components:

1. Working Directory: The actual files exists here.
2. Index: The area used for staging
3. Head: Points to the most recent commit

![Local Repository Structure](https://blog.udemy.com/wp-content/uploads/2015/08/image036.png)

* Saving Changes

there are two states for files
1. Tracked : Tracked files can be modified, unmodified, or staged.
2. Untracked :the files do not currently exists in the staging area.

* The Life Cycle of File Status
1. when you edit a file, Git marks it as modified.
2. You stage the modified file.
3. You commit staged files.

![The Life Cycle of File Status](https://blog.udemy.com/wp-content/uploads/2015/08/image006.png)

* Check File Status
To check the file state we write the following command 

`git status`
 if the output was "nothing to commit" this means that there is no untracked files.

 * Tracking and Staging a New File

1. Single File 
To track a single file we write:
` git add filename`
2. All Files
To tarck all files we write :

` git add *`

* Committing a File
to commit a file or multiple files after staging them we write:
 `git commit -m “made change x,y,z”`
* Committing All Changes
to commit a snapshots of all files we write:

`git commit -a `

* Pushing Changes

to push the changed directory to the remote repository we write the following command :

`git push origin master`
 
* Stashing Changes

if you are not ready to commit your modifications you can stash them by writing `git stash` and the directory will look clean and the changes are hidden and when you decide to commit these changes you can restore them by writing `git stash apply`

# Remote Repositories



* Cloned Repositories
When you clone a repository from a server Git will automatically give the name "origin" to that server and the name "master" to your local branch.

* Seeing Your Remotes
 `git remote` command shows you all  remote servers names like  “origin,” .

`git remote -v`command shows you all  remote servers names in addition to their urls .

 `cd example`

`git remote -v`

`remote1 https://github.com/remote1/example (fetch)`

`remote1 https://github.com/remote1/example (push)`

`remote2 https://github.com/remote2/example (fetch)`

`remote2 https://github.com/remote2/example (push)`

`remote3 https://github.com/remote3/example (fetch)`

`remote3 https://github.com/remote3/example (push)`









