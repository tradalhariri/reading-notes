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
 > ` git config --global user.name "Jane Smith" `

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







