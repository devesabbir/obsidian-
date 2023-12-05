### Git Commands

##### `.gitignore`

Create a `.gitignore` file in your root directory

## [](https://github.com/kenmueller/gitignore#ignoring-single-files)Ignoring single files

**Must specify filename and extension**

```shell
example.txt
```

## [](https://github.com/kenmueller/gitignore#keeping-single-files)Keeping single files

```shell
!example.txt
```

## [](https://github.com/kenmueller/gitignore#multiple-files-with-the-same-extension)Multiple files with the same extension

```shell
*.txt
```

## [](https://github.com/kenmueller/gitignore#multiple-files-with-the-same-name)Multiple files with the same name

```shell
example*
```

## [](https://github.com/kenmueller/gitignore#folders)Folders

```shell
examples/
```

## [](https://github.com/kenmueller/gitignore#files-inside-of-folders)Files inside of folders

**You can apply the same techniques for multiple files inside the root directory**

```shell
examples/example.txt
```

## [](https://github.com/kenmueller/gitignore#everything-inside-of-a-folder-except-for-some-files)Everything inside of a folder except for some files

**When first ignoring the whole folder, you must have a star at the end.**

**The star means you are ignoring the files in the folder, while not having a star means that you are ignoring the whole folder**

```shell
examples/*
!examples/example.txt
```

## [](https://github.com/kenmueller/gitignore#ignoring-files-in-every-directory)Ignoring files in every directory

**This ignores all files named example.txt in every folder. You can use the same techniques for ignoring specific names or extensions with this syntax as well.**

```shell
**/example.txt
```

## [](https://github.com/kenmueller/gitignore#ignoring-files-only-in-the-root-directory)Ignoring files only in the root directory

**Must include a slash in the beginning**

```shell
/example.txt
```

## [](https://github.com/kenmueller/gitignore#matching-many-characters)Matching many characters

**This ignores files named `Example.txt` and `example.txt`. You can match against as many characters as you like at once.**

```shell
[Ee]xample.txt
```

 

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

##### File-Folder Creation


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