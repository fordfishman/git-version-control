# Session 1: Getting started!
In this workshop, we are using **git** and [GitHub.com](https://github.com/).

## Installation Instructions
Follow the [Software Carpentry's Instructions](https://carpentries.github.io/workshop-template/#git) to install git for your operating system. 

**Git** is a version control system that lets you track who made changes to what when and has options for easily updating a version of your work. 

**GitHub.com** You will need a free account for part of this workshop.  We will follow the instruction to keep your email address private at GitHub.

**Git Vocabulary**
- Commit:
- Repository:

### Configure git global settings
When we use Git on a new computer for the first time, we need to configure a few things. Below are a few examples of configurations we will set as we get started with Git:
- our name and email address,
- what our preferred text editor is,
- and that we want to use these settings globally (i.e. for every project).

**MacOS**:  Open a bash shell under Applications > Utilities > Terminal

**Windows**:  Open the git shell "Git Bash" you downloaded through the bash installation procedures, or run the command "bash" in your Command Prompt.

**Linux**:  Use your terminal


In the bash shell, run the following commands (with your information):

**Name configuration**

`$ git config --global user.name "Vlad Dracula"`


**Email configuration**
- Log in to [GitHub.com](https://github.com)
- Click on your profile icon at the top right corner
- Go to Settings
- Click on Emails in the left menu
- Select the check box "Keep my email addresses private" and use the private github.com-supplied email listed in the cnnfiguration below.  You can highlight and copy it with ctrl+C, and paste to the command line with Ctrl+V.

`$ git config --global user.email "1234username@users.noreply.github.com"`


**Line Heading configuration**

As with other keys, when you hit Return on your keyboard, your computer encodes this input as a character. Different operating systems use different character(s) to represent the end of a line. Because Git uses these characters to compare files, it may cause unexpected issues when editing a file on different machines. 

*On macOS and Linux* `$ git config --global core.autocrlf input`

*On Windows*. `$ git config --global core.autocrlf true`

**Editor configuration**

In these sessions, we will be using a basic editor called nano.  There are other ways to configure for more popular editors [here](http://swcarpentry.github.io/git-novice/02-setup/index.html).
`$ git config --global core.editor "nano -w"`


Check your settings at any time with:  `git config --list`


## Commands to create and check on a repository
- `git init`: makes a repostiory of all the subdirectories and files within the working directory.
- `git status` shows what is in staging and was is being commited.
- `git log` shows the history of commits
- `git add file_name`: Moves a file to staging.
- `git commit -m "Detailed log message goes here."`: Commits files in staging to history and documents message to the log.

### History of commands from today's session:
```
# This is a comment.  Any text after a hashtag is not executed in the command line prompt.
# Your command line is indicated by a $

# Change directory (cd) to the desktop
cd ~/Desktop

# Make a new directory (mkdir) named planets
mkdir planets

# Change directory (cd) into the planets directory (also called a folder).
cd planets

# Tell Git to make planets a repository—a place where Git can store versions of our files:
git init
 
# List files (ls) including hidden files (-a) in the directory
ls -a
# This will show us a new directory .git where version history is stored

# Use nano editor to create a new file named mars.txt
nano mars.txt

  # Type the text below into the mars.txt file:
  # Cold and dry, but everything is my favorite color
  # Press ctrl+O to write out (save) the file
  # Press Ctrl+X to exit the nano editor

# See what's in the file with concatenate (cat)
cat mars.txt

# Check the status of the repository
git status

# Output: # # # # #
# On branch master
# Initial commit
# Untracked files:
#   (use "git add <file>..." to include in what will be committed)
# # # # # # # # # #

# The “untracked files” message means that there’s a file in the directory 
# that Git isn’t keeping track of. 

# Tell Git to track a file using git add:
git add mars.txt

# Now check the status:
git status

# Output: # # # # #
# On branch master
# Initial commit
# Changes to be committed:
#  (use "git rm --cached <file>..." to unstage)
#	new file:   mars.txt
# # # # # # # # # #

# Commit the file(s) from staging into a copy permanently inside the special .git directory
# Use -m to provide a short, descriptive, and specific comment for later
$ git commit -m "Start notes on Mars as a base"

git status

# Output: # # # # #
# On branch master
# nothing to commit, working directory clean
# # # # # # # # # #

# it tells us everything is up to date. 

# Check what we've done recently with the project's history log
git log


```
