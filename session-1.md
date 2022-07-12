# Session 1: Getting started!
In this workshop, we are using **git** and [GitHub.com](https://github.com/).

**Git** is a version control system that lets you track who made changes to what when and has options for easily updating a version of your work. 

**GitHub.com** You will need a free account for part of this workshop. We will follow the instruction to keep your email address private at GitHub.

**Git Vocabulary**
- Commit: (noun) A recorded version of your project. (verb) To record a new version of your project.
- Repository (or repo): where your files are stored, can be on your computer (local) or on GitHub's servers (remote)
- pull: fetching commits from a remote repository and merging them with local changes
- push: sending local commits to a remote repository
  
Definitions adapted from [git-scm.com](https://git-scm.com/docs/gitglossary)

<br>

## Register for a GitHub Account
Go to [GitHub.com](https://github.com), register for an account, and verify it. 

<br>

## Installation Instructions
<br>


### Windows

You will installing [Git Bash](https://gitforwindows.org/) (also called Git for Windows). Detailed instructions can be found via [Software Carpentries](https://carpentries.github.io/workshop-template/#shell).

### MacOS

Open Terminal. It should be located in `Applications/Utilities`. You use Spotlight to locate it as well (<kbd>cmd</kbd>+<kbd>spacebar</kbd> and type "Terminal").

Type `which git` and press Return. If it prints a path (e.g. `/usr/bin/git`), Git is already installed. 

If no path is printed, follow the instructions at [the Software Carpentries](https://carpentries.github.io/workshop-template/#git) for MacOS.

### Linux

Open the terminal. Type `which git` and press Return. If it prints a path (e.g. `/usr/bin/git`), git is already installed. If not, for Debian/Ubuntu run `sudo apt-get install git` and for Fedora run `sudo dnf install git`.

<br>

### Configure git global settings
When we use Git on a new computer for the first time, we need to configure a few things. Below are a few examples of configurations we will set as we get started with Git:
- our name and email address,
- what our preferred text editor is,
- and that we want to use these settings globally (i.e. for every project).

**Windows**:  Open the git shell "Git Bash" you downloaded through the bash installation procedures, or run the command "bash" in your Command Prompt.

**MacOS**:  Open a bash shell in Terminal.

**Linux**:  Use your terminal.

In the bash shell, run the following commands (with your information). The leading `$` indicates that the command should be run in `bash`. Do not insert an additional `$` in your own terminal. If the commands are successful, nothing will print to the terminal.

To use `git` commands, we use the syntax `git SOME_COMMAND`. We will be using `git config` with some added parameters to set up `git`.

**Name configuration**

```bash
$ git config --global user.name "InigoMontoya"
```

**Email configuration**
- Log in to [GitHub.com](https://github.com)
- Click on your profile icon at the top right corner
- Go to Settings
- Click on Emails in the left menu
- Select the check box "Keep my email addresses private" and use the private github.com-supplied email listed in the cnnfiguration below.  You can highlight and copy it with <kbd>Ctrl</kbd>+<kbd>C</kbd> or <kbd>cmd</kbd>+<kbd>C</kbd> (Mac), and paste to the command line with <kbd>Ctrl</kbd>+<kbd>V</kbd> or <kbd>cmd</kbd>+<kbd>V</kbd>.
 
```bash
$ git config --global user.email "1234username@users.noreply.github.com"
```

**Line Heading configuration**

As with other keys, when you hit Return on your keyboard, your computer encodes this input as a character. Different operating systems use different character(s) to represent the end of a line. Because Git uses these characters to compare files, it may cause unexpected issues when editing a file on different machines. 

*Windows*
```bash 
$ git config --global core.autocrlf true
```

*MacOS and Linux* 
```bash 
$ git config --global core.autocrlf input
```

**Editor configuration**

In these sessions, we will be using a basic editor called nano.  There are other ways to configure for more popular editors [here](http://swcarpentry.github.io/git-novice/02-setup/index.html).
```bash
$ git config --global core.editor "nano -w"
```

Check your settings at any time with:  
```bash
$ git config --list
```
<br>

## Create a remote repository on GitHub

Go to GitHub and create a new repository by clicking "New". 

<br>

![Make a repo](img/github_newrepo.png)

<br>

Give your repo a short but descriptive name with no spaces or special characters. Note that your account cannot have two repos with exactly the same name. 

<br>

![Name your repo](img/github_reponame.png)

<br>

You can choose whether or not your repository to be private. If you plan to collaborate with others, you are required to have a public repository unless you pay for a premium GitHub account.

Make sure to initialize with a README, which will give general information about your repository. You can also initialize with a license, which defines what others can and cannot do with your code. 

<br>

## Clone the remote repository to your machine

To get this repository we have initialized onto our local machine we will clone it, which copies its contents. Go to the repository you just made on GitHub. You will see a README.md file and a license file. Click on "Code", which opens a dropdown menu. Copy the HTTPS link, which will be `https://github.com/{USERNAME}/{REPO-NAME}.git`, with your username and repo name, respectively.

<br>

![clone repo](img/github_clone.png)

<br>

Go back to your terminal. Create a new `GitHub` folder in your home directory by running:

```bash
$ mkdir ~/GitHub
```

This uses the Unix command `mkdir` (Make Directory) to create a new folder. We then want to go to that folder with the `cd` (Change Directory) command.

```bash
$ cd ~/GitHub
```

To clone your repository, run the following:

```bash
$ git clone https://github.com/{USERNAME}/{REPO-NAME}.git
```

Move to your newly cloned local repository and list the files with `ls` command.

```bash
$ cd {REPO-NAME}
$ ls
```

You should see the names of the files `LICENSE` and `README.md` printed to the terminal. 

## Alter the README 

You now have a local **downstream** repository on your machine. The remote GitHub repository is referred to as the **upstream** repository. If other users make changes reflected in the upstream repository, you will receive and implement them locally.

We are going to write line to the README and commit that change to version control. In later sessions, we will push that change upstream to make it reflected in GitHub.

First, we are going to use a text editor called `nano` to open `README.md`.

```bash
$ nano README.md
```

<br>

![nano blank](img/nano1.png)

<br>

Tap the <kbd>&#8595;</kbd> key to get to a new line. Write whatever your heart desires ("Hello World!" is a classic). To save or "write" your changes, press <kbd>Ctrl</kbd>+<kbd>O</kbd>, and then hit <kbd>Return</kbd>. Press <kbd>Ctrl</kbd>+<kbd>X</kbd> to exit `nano`.

<br>

![nano blank](img/nano2.png)

<br>

START HERE

### Important Git commands
- `git status`: shows what is in staging and was is being commited.
- `git log`: shows the history of commits
- `git add file_name`: Moves a file to staging.
- `git commit -m "Detailed log message goes here."`: Commits files in staging to history and documents message to the log.



### History of commands from today's session:
```bash
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
