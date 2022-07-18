# Session 2: Interacting with GitHub and Branching

Today, you will be making more changes to your repository, as well as sending those changes to the remote upstream repository on GitHub. This is known as **pushing**. 

## Make a new file

Let's practice making another change and commiting it. We'll use the `touch` command to make a new empty file called `notes.txt`. Make sure you are in the correct directory first. You can do this by running `pwd` (Print Working Directory) and then using `cd` to navigate to the repository. 

```bash
$ touch notes.txt
```

Running `ls` will show you a `notes.txt` is now in your working directory. Run `git status` to see that we can now stage and commit this file. 

```bash
$ git add notes.txt
$ git commit -m "Added notes files"
$ git status
```

`git status` will let us know that all changes have been committed and that we are now 2 commits ahead of what is on GitHub.

## Adding a Personal Access Token
In recent years, GitHub has started to require users to use personal tokens in order to push commits and perform other actions. 

1. Go to GitHub.
2. Click on your profile in the top right, and go to Settings.
3. Scroll to the bottom and click Developer Settings.
4. Go to Personal access tokens.
5. Click Generate new token.
6. Write a short note for what the token is used for (e.g., "Ford Fishman MacBook")
7. (Optional) For maximum security, give an expiration to the token.
8. Check the `repo` box. Make sure all the sub-boxes are checked, as well.
9. Generate token, copy the key, and make sure to store it somewhere securely. You will need to paste it when we run `git push`.

## Pushing to GitHub
Now that we've created the token, we can push our changes to GitHub.

```bash
$ git push
```

Once you run this command, you will prompted to enter your GitHub username followed by the key for the token you just entered. Hit <kbd>Enter</kbd> after typing in your username. Paste in the key with <kbd>Ctrl</kbd>+<kbd>V</kbd> or <kbd>cmd</kbd>+<kbd>V</kbd> (MacOS). Once you paste, it will not display the key in the terminal for security purposes. Hit <kbd>Enter</kbd> again. 

*Notes: The prompt for the key may ask for a password, but your account password will not work. Use the personal access token.*

Once the push goes through, the terminal will print some information about the process, and your changes should now be reflected on GitHub. 

![git push](img/git_push.png)

## Fetch and merge from GitHub

If we are working with others on a project, often our local repository will be out of sync with the remote GitHub repository. In the simplest case, we will simply be one or more commits behind GitHub. To address this, we first want to **fetch** any commits from GitHub and then **merge** them into our local repository. For instance, if someone has created a new file `data.text` and committed it to the GitHub repo, we can run `git fetch` followed by `git merge` to have that file reflected on our machine. When collaborating with others, it is a healthy practice to run these commands before we make any changes and before we push changes.

### Make changes to the README on GitHub


```bash
$ git fetch
$ git merge
```

You should see a message stating that our local repository is already up to date, as no other commits have been made yet.

*Note: The command `git pull` is equivalent to running `git fetch` followed by `git merge`, though it may lead to some unexpected behavior at times. We will discuss this later.*

- `git init`: makes a repostiory of all the subdirectories and files within the working directory.
- `git pull`: fetching commits from a remote repository and merging them with local changes
- `push`: sending local commits to a remote repository
- `git log`: shows the history of commits