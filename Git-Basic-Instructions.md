# Basic Git Manual

## A personal Guide to Install and Use Git on Microsoft Windows 10

### 1. Software Download:

* Go to [http://www.git-scm.com](http://www.git-scm.com) and download the right git version for your computer.

### 2. Software Installation on Windows:

* Follow normal installation process, as with any other Windows based installation process.
* On **"Select Component"** screen, please check the following is respected:
    * *Additional Icons* = Optional, not necessary (First Option).
    * *Windows Explore Integration* = "Git Bash Here" and "Git GUI here" should be selected as well. (Second Option).
    * *Associate .git configuration files with the default text editor* = Should be selected. (Third Option).
    * *Associate .sh files to be run with Bash* = Should be selected. (Fourth Option).
    * *Use a TrueType font in all console Windows* = Optional, not necessary (Fifth Option).
* On **"Adjusting your PATH Environment"** screen, please check the following is respected:
    * *Use Git and optional Unix tools from the Windows Command Prompt* = should be selected (Third Option).
* On **"Configuring the line ending conversions"** screen, please check the following is respected:
    * *Checkout Windows-stype, commit Unix-style line endings* = should be selected (First Option).
* On **"Configuring the terminal emulator to use with Git Bash"** screen, please check the following is respected:
    * *Use MinTTY (the default terminal of MSYS2)* = should be selected (First Option).
* On **"Configuring extra options"** screen, please check the following is respected:
    * *Enable file systems caching* = should be selected (First Option).
    * *Enable Git Credential Manager* = should be selected (Second Option).
* Continue normal installation process, as with any other Windows based installation process. Press **"Finish"** once you are done.

### 3. Git Setup on Windows:

* Launch Git Bash on your Windows Machine (Search for **"Git Bash"** Program)
* Create a folder on which you may be able to start working with Git. If existing, just navigate to it from the MINGW64 (Git Bash) Window using the "cd + folder" instructions
* Configure git to be able to work with GitHub or other Git related systems:
    * **Set your Username** - please enter the following command:
    ```git config --global user.name "Username"```
    * **Set your Email** - please enter the following command:
    ```git config --global user.email "example@example.com"``` 

### 4. First Operations with Git:

**Note:** Assumption is you have an operative account on a major Git online repository (i.e. [GitHub](http://www.github.com)).

* **Start git** - Before starting to work with git, you need to initiate it for tracking purposes:
    ```git init```

* **Clone Repository** - Clone an online repository, under your local target folder, by using following command:
    ```git clone http://www.repository-to-clone-example-url.com```

* **Add Files to Repository** - If you create files under the Cloned repository, you will need to "declare" them to git. You will do so by using following command:
    ```git add filename-or-filenames```
* **Check Status of Files into your Repository** - If you want to know what is going on under your repository, you will need to "verify" the status. You will do so by using following command:
    ```git status```
* **Commit Files into your Repository** - Once you finish with the changes on the files you are working on under git, you will have to commit them. You will do so by using following command:
    ```git commit -m "Commit Message" filename```
* **Pushing Files from your local client into your online Repository** - After commiting your file or files, you may send them to your online repository for consolidation (you will "push" your changes to the repository). You will do so by using following command:
    ```git push```
* **Pulling Files from your online Repository into your local client** - In case other changes may have been pushed into the online repository or, if you push your changes on a certain machine into the online repository, and you would like to replicate them into another client where you may be working on, you will have to "pull" the changes into it. You will do so by using following command:
    ```git pull```
* **Discarding changes on a local file** - In case certain changes may not be clear and do not want to be pushed to the repository, you can always checkout the file (worse case scenario, after that, you can always pull the copy in the online repository to make sure everything reverts back to the latest version). You will do so by using following command:
    ```git ckeckout filename (or . for all files within a folder)```
    
* **Introducing git repository service credentials** - While you transfer files into your git repository, the destination service may request your credentials. This may be reflected on your system requesting username and password: you may be required to enter those credentials to access the destination service repository.

### 5. On-going Operations with Git:

**Note:** Assumption is you have been operating with git before, as the following instructions assume recurring interactions.

* **On-going Operations** - Once you have created files and git is active on your repository, every time a file is modified and saved on the local clone of the repository, git will keep track of it. The following commands will have a recurring use on your daily interaction with git and your project:<br><br>

    ```git add filename``` (or `.` or `--all` if you want to add all files in the directory)<br>
    ```git status```<br>
    ```git commit -m "Commit Message" filename```<br>
    ```git commit -am "Commit Message"``` (if you want to add and commit all changes in one go)<br>
    ```git checkout filename (or . if you want to add all files in the directory)```<br>
    ```git push```<br>
    ```git pull```<br>

### 6. Commits Operations:

**Note:** Assumption is you have been operating with git and you have your own repository with multiple commits.

* **Removing a commit wrongly pushed** - it may happen, at some point, that something, somewhere, went terribly wrong in your code. There are two solutions for it:<br><br>

1. Fix it, re-commit the changes and push them to your repository (preferred option).
2. Remove the commit from the repository and go back to the previous state (not preferred).

  **Note:** This is not a preferred way of working, but sometimes you may no other way.

If you want to remove the commit form the repository (Option 2), these are the following steps you need to follow:

`git rebase -i HEAD~2` It will open a file displaying the last two commits into your repository.

A new window will open with a text editor (default git editor is VIM, unless you selected another editor into the `git config --global` configuration file.

The file will show something like the following:

```
pick 6d8301e Bad Commit
pick 971ed7d Fixing Code
# Rebase 3254a6e..971ed7d onto 3254a6e (2 commands)
#
# Commands:
# p, pick = use commit
# r, reword = use commit, but edit the commit message
# e, edit = use commit, but stop for amending
# s, squash = use commit, but meld into previous commit
# f, fixup = like "squash", but discard this commit's log message
# x, exec = run command (the rest of the line) using shell
# d, drop = remove commit
#
# These lines can be re-ordered; they are executed from top to bottom.
#
# If you remove a line here THAT COMMIT WILL BE LOST.
#
# However, if you remove everything, the rebase will be aborted.
#
# Note that empty commits are commented out
```

Go then to the line containing the commit you want to remove and change the "pick" word to "drop".

The first line (containing the bad commit we want to replace) will then look like follows:

```
drop 6d8301e bad commit
pick 971ed7d Fixing Code
.
.
.

```

You will finally need to save the change and quit the editor. For VIM, you should press *ESC* key and then press *:wq* 

**FYI - How to exit the Vim editor**

Hit the *Esc* key; that goes into command mode. Then you have the following options you may need to type (including the colon):

```
:q   - to quit (short for :quit)
:q!  - to quit without saving (short for :quit!)
:wq  - to write and quit (think write and quit)
:wq! - to write and quit even if file has only read permission (if file does not have write permission: force write)
:x   - to write and quit (similar to :wq, but won't write if there are no changes)
:qa  - to quit all (short for :quitall)
```

### 6. Branching Operations:

**Note:** Assumption is you have been operating with git and you have your own repository with multiple commits.

  ```
  git branch branchname
  git checkout branchname
  git branch -d branch_name
  ```
