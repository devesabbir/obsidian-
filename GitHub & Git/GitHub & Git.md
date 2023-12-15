
# Version Controller 

#### git configuration 

```shell
 # For check confg list
 git config --list

# Set git configuration 
 git config --global user.name "devesabbir"
 git config --global user.email "devssabbir@gmail.com"
 
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

# remote checking
git remote

# git add remote 
git remote add origin <url>

# git add remote 
git remote add vercel <url>

# To push
 git push origin main

# To push
 git push vercel main

# Clone existing repo
 git clone <url>

# Git Pull 
 git pull

```


#git #git-commands #git-basic-commands 

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

```

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

# git remove file (untracked)
 git rm <filename.txt>

```

#git #git-log #git-reset

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



