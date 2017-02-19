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

### 4. Operating with Git:

**Note:** Assumption is you have an operative account on a major Git online repository (i.e. [GitHub](http://www.github.com)).

* **Clone Repository** - Clone an online repository, under your local target folder, by using following command:
    ```git clone http://www.repository-to-clone-example-url.com```

* **Add Files to Repository** - If you create files under the Cloned repository, you will need to "declare" them to git. You will do so by using following command:
    ```git add filename-or-filenames```
* **Check Status of Files into your Repository** - If you want to know what is going on under your repository, you will need to "verify" the status. You will do so by using following command:
    ```git status```
* **Commit Files into your Repository** - Once you finish with the changes on the files you are working on under git, you will have to commit them. You will do so by using following command:
    ```git commit -m "Commit Message" filename```
* **Transfer Files into your online Repository** - After commiting your file or files, you may send them to your online repository for consolidation (you will "push" your changes to the repository). You will do so by using following command:
    ```git push -u origin master```
* **Introducing git repository service credentials** - While you transfer files into your git repository, the destination service may request your credentials. This may be reflected on your system requesting username and password: you may be required to enter those credentials to access the destination service repository.
