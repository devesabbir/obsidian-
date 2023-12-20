
# Version Controller 

#### git configuration 

```shell
 # For check confg list
 git config --list

# Set git configuration 
 git config --global user.name "devesabbir"
 git config --global user.email "devssabbir@gmail.com"
 
```

#### git ssh method

```shell
# generate ssh-key in windows os
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

```


#git #github #git-config

##### file-folder creation


```bash

 # To make Directory
  mkdir [directoryname]
 # To remove directory 
  rmdir [directoryname]
 # To rename directory 
  mv [old_name] [new_name]
  # To create a new file 
  touch [filename.txt]
 # To Rename File 
  mv [filename.txt] [newname.txt]
 # To Delete file 
  rm [filename.xt]
```


#git #file_folder_creation

####  git initialize commands


```shell

 # to check present working directory
 pwd
 # To initialize git
 git init

 # check status
 git status

 # Add changes to git
 git add .

# commit all changes to git 
 git commit -m "message"

# git add and commit all
git commit -am "<commit message>"

# remote checking
git remote

# git add remote 
git remote add origin <url>

# git add remote 
git remote add vercel <another-url>

# To push  
 git push origin main

# To push on vercel
 git push vercel main

# To remove remote
git remote rm vercel

# Clone existing repo
 git clone <url>

# Git Pull 
 git pull

```

#git #git-commands #git-basic-commands #git-push

#### git branch

```shell
# Show all branch
git branch --list

# Create new branch 
git branch dev/sabbir

# Switch to branch
git switch dev/sabbir

# Switch to branch
git checkout main

# Create new branch and switch immediately
git checkout -b <branch name>

# Merge to another branch
git merge dev/sabbir

# Delete branch (commited required)
git branch -d <branch name>

# Delete branch (without committed)
git branch -D <branch name>

# Rename/Modify branch name
git branch -m <rename branch>

# Rename/Modify branch name (Forces a rename of the branch even if the new branch name already exists.)
git branch -M <rename branch>

```

#git #git-branch 

#### git Log & Reset


```shell 
# Git Log
git log

# Git Log in One Line
git log --oneline

# git reflog
git reflog

# git reset as committed history
git reset --hard <commited id>

# git remove file (untracked & delete)
 git rm <filename.txt>

# git remove tracking from committed
git rm --cached <file.txt>

```

#git #git-log #git-reset #git-rm


##### git stash

```bash

 # To check stash list
   git stash list
   
# To stash the changes
   git stash 
   
 # To updated stash with messages
   git stash push -m "any messages"
   
 # To apply the most recent stash 
   git stash apply
  
  # To apply a specific stash 
   git stash apply [index]

  # To apply and remove the most recent stash 
   git stash pop 
   
  # To apply and remove a specific stash 
   git stash pop [index]
   
  # To remove most recent stash 
   git stash drop 

  # To remove a specific stash 
   git stash drop [index]

  # To clear stash list
   git stash clear

  
```

#git #stash


#### git fork

In Git, a "fork" typically refers to a copy of a repository that is made by a user (or organization) on a hosting service, usually to propose changes to someone else's project or to use someone else's project as a starting point for your own work. Forking a repository is commonly associated with platforms like GitHub, GitLab, and Bitbucket.

Here's how the process generally works:

1. **Creating a Fork:**
    
    - You find a project on a Git hosting service that you're interested in.
    - You fork the project, creating your copy of the repository.
2. **Making Changes:**
    
    - You make changes to your forked repository, typically in a branch.
    - You can push these changes to your forked repository.
3. **Creating a Pull Request:**
    
    - If you want to contribute your changes back to the original project, you create a pull request.
    - The pull request is a way of proposing your changes to the original project.
4. **Review and Merge:**
    
    - The owner of the original project (or someone with the necessary permissions) reviews your changes.
    - If they approve, they can merge your changes into the original project.

Forking is commonly used in open-source development. It allows contributors to work on changes independently, without directly affecting the original project. It also makes it easier for maintainers to review and manage contributions.

Here is a brief example using GitHub:

1. **Forking a Repository:**
    
    - Visit the GitHub repository you want to fork.
    - Click the "Fork" button in the upper right corner of the GitHub page.
    - This creates a copy of the repository under your GitHub account.
2. **Clone Your Fork:**
    
    - Clone your forked repository to your local machine using `git clone`.
3. **Make Changes:**
    
    - Create a new branch (`git checkout -b feature-branch`) and make your changes.
4. **Push Changes:**
    
    - Push your changes to your fork on GitHub (`git push origin feature-branch`).
5. **Create a Pull Request:**
    
    - On GitHub, navigate to your forked repository.
    - GitHub will usually prompt you to create a pull request for the branch you just pushed.
6. **Review and Merge:**
    
    - The maintainers of the original repository review your changes and, if they are satisfied, merge them into the main project.

Keep in mind that the exact steps might vary slightly depending on the hosting service (GitHub, GitLab, Bitbucket, etc.) you are using.


#git #git-fork

##### `.gitignore`

Create a `.gitignore` file in your root directory

##### Ignoring single files

**Must specify filename and extension**

```shell
# Must specify filename and extension
example.txt
```

##### Keeping single files

```shell
# Keeping single files
!example.txt
```

##### Multiple files with the same extension

```shell
# Multiple files with the same extension
*.txt
```

##### git not ignore specific file

```bash 
 # git not ignore specific file
 *.log  
!important.log
```
##### Multiple files with the same name

```shell
# Multiple files with the same name
example*
```

##### Folders

```shell
# Folders
examples/
```

##### Files inside of folders

**You can apply the same techniques for multiple files inside the root directory**

```shell
# Files inside of folders
examples/example.txt
```

##### Everything inside of a folder except for some files

**When first ignoring the whole folder, you must have a star at the end.**

**The star means you are ignoring the files in the folder, while not having a star means that you are ignoring the whole folder**

```shell
# Everything inside of a folder except for some files
examples/*
!examples/example.txt
```

##### Ignoring folder in any level or depth within the project directory.

**This ignores all folder named example in any level or depth within the project directory.**

```shell
# Ignoring folder in every directory
**/example
```

##### Ignoring files in every directory

**This ignores all files named example.txt in every folder. You can use the same techniques for ignoring specific names or extensions with this syntax as well.**

```shell
# Ignoring files in every directory
**/example.txt
```

##### Ignoring files only in the root directory

**Must include a slash in the beginning**

```shell
# Ignoring files only in the root directory
/example.txt
```

##### Matching many characters

**This ignores files named `Example.txt` and `example.txt`. You can match against as many characters as you like at once.**

```shell
# Matching many characters
[Ee]xample.txt
```

#git #git-ignore

