Git:
====
+ Downloas Git from https://git-scm.com/downloads
+ Install it

Version controll system:
========================
+ Version control is a system that records changes to a file or set of files over time so that you can recall specific versions later

Centralized Version controll system:
====================================
+ In this centralized source control, there is server(master) and one or more users(clients)involved.Here the server is master repository which contains all the version of source code
+ The master repository contains updated version of the source code.Users can pulls the source code from the master and then do the own changes to the source code.Finally push the updated code to the central(master) repository
+ Github remote repository,SVM(Apache subversion)

Distributed Version Control System:
===================================

+ Working offline
+ Data will not be lost
+ Git,Mercurial are examples

Uses of Git& Github:
====================
+ While doing Global certifications like Udacity,Coursera they will prefer Git&Github
+ We can track history of files in the project
+ While working on a project to collaborate with team members we can use Git&Github

Git options:
============
+ Git Bash emulates a bash environment on windows. It lets you use all git features in command line plus most of standard unix commands
+ Git GUI is a Graphical User Interface letting you use Git without touching command line. It is an alternative among other Git clients

+ To check version of git use `git --version` command

Linux commands in git bash:
===========================

+ In linux to navigate from one folder to another folder we have to use cd(change directory) `cd foldername`
+ cd → change directory
	+ Eg: `cd folder name`
	+ `cd` → navigate to the home
	+ `cd..` → navigate to the parent folder
	+ `cd -` → going back to the previous location
	+ `cd ../..` → navigate to parent of the parent folder

+ `PWD` - Present Working Directory(folder)
	+ Displays the current location of CLI
+ To create new folder we have to use `mkidir foldername`
	+ `rmdir` folder name → removes empty folders
	- If the folder contains a file then first remove the file present in the folder and come back and remove the folder when it is empty.
+ To see list of files in folder use `ls`
+ To create file `touch | vim(open editor)  filename`
	+ `touch` → to create a new file. eg: touch test.txt
	+ `touch file1.txt file2.txt` → creating multiple files at a time
	+ `touch file{1..10}.txt` →  creating 10 files at a time
	+ When you create file using vim editor after writing of code use `:w` to save code and `:q` to exit from the editor
	+ To edit file use `nano filename`.It will open nano editor in that write your code.To save and exit nano editor use `ctrl+x` and then click `y` it will goto save mode file path `Filename name to write : filename` and then click on `Enter`.It will go back to project folder.Then see your edited code by `cat filename`

+ `echo` → to enter data into file eg: echo test want to enter >> filename
	- Eg: `echo hello world >> test.txt`
	- `echo secondline>>test.txt`
	- `echo {1..110} >> test.txt` → prints numbers from 1 to 110
+ `cat test.txt` → display data inside the test file
	- `cat file.txt ||` more → to display all numbers between 1 to 1000000
+ To remove any file use `rm filename`
	+ To remove folder `rm -r foldername`
	+ To move all files at a time `git rm -r cached .`
+ If the file doesn’t exist then create a file and copy data. It adds data to the previous data
	+ `cat file1 >> file` → create file1 and copy data of file1 into file2
	- **Example:**
		- `cat hello.txt>>sample.txt`
		- O/P hello.txt contains “hai”
		- sample.txt file doesn’t exist when we execute it creates the file and copy data from hello.txt to sample.txt
	- **o/p**:
		- hello.txt:” hai”
		- sample.txt:” hai”
		- If you do the same process then newly data adds to venkat.txt

Git commands:
===============
+ First we need to initialize git repositroy by `git init`
+ To see  git folder use `ls -a`(It will show hidden files also)

+ Main in git we have 3 areas
	+ Untracked area(those files(red color files) are not adding to git )
	+ Staging area (Files(green color) added to git)
	+ Commit area
+ To check files are tracked or untracked we can use `git status`
+ To check the status of a file use `git status`
+ To add a single file to stage area use `git add filename`
+ To add multiple files to `git add . or git add --all`
+ To move file from staging area to untracked area use `git rm --cached filename`
+ Commit all the files by using `git commit -m "Version1`+ For every commit a SHA(Secure Hash Algorithm) key with 40 characters length will generate to theck that one use `git log`

+ if it is asking tell me who you are? like this we have to configure git with username and email

Configurations:
===============
+ We have to configure git by providing username and email globally(better to use github logins)
+ git config --global user.name "Username"
+ git config --global user.email "your email"


+ If we want check particulr n-commit data we have to use first seven chareacters of a SHA key. For that use `git log --oneline`
+ We can check the files in first commit by using SHA key with command of `git checkout xxxxxxx`(first 7characters of SHA key).Which means we can get the data at the first commit.Similary we can get the data @ nth position commit

+ After switch to particular commit you can update data and then commit finalupdated data.
+ To check the number of commits ` git rev-list --count HEAD`

Note:
=====
```In case if you updated data with new commit if you want to continue with coomit create new branch with those commit by usning `git branch branchname xxxxxxx(sha key).```


+ Then switch to master branch by using `git checkout master` 

Change commit message:
----------------------
+ To change latest commit message use `git commit --amend -m "updated".To change commit message when head-->master is possible`

Delete commit:
--------------
+ To delete latest commit use `git reset HEAD^`.If you want to delete with data with commit use `git reset --hard Head^`
+ To delete number of commits use `git reset --hard HEad~2` here i want to delete 2 latest commits
+ To delete specific commit we have to user "git rebase --onto --branchname ~ number to delete the commit branchname ~ number(Head to master is @which commit) to kept branchname "
+ `git rebase --onto master~3(delete first commit(1-commit(delete),2-commit,(3)final-commit:master will head to 3rd commit)) master~1 master`


### Cloning of Remote repositiory:
==================================

 + clone
 	+ No need to extract
 + zip
   + We need to extract zip folder

## Procedure to push prject into central repository:
=====================================================

1. Initialize git in local repository by using `git init`
2. Check files status by using `git status`
3. Add all files to git with help of `git add . or git add --all`
4. Change to commit area by `git commit -m "Message"`
5. If it asks tuser.name and email then we have to configure those things by `git config --global user.name "githubusername"` and `git config  --global user.email "githubemail"`
6. Check username and email once byusing  `git config --global user.name ` and `git config  --global user.email`
7. Add remote origin from the github repository by using `git remote add origin "url"`
8. Push the source code in to github by using `git push origin master or git push -u origin master`


## Branch:
==========

+ To check number of brances we have to use `git branch`
+ To create new branch use `git branch newbranchname`
+ To change from one brnach to another branch use `git checkout newbranchname`
+ Delete branch in local git
	+ To delete particular branch after merge  `git branch -d branchname`
	+ To delete particular branch before merge `git branch -D branchname` 
+ Delete branch in remote
	+ To delete particular branch in github `git push remotename --delete branchname` 
	+ Ex: `git push origin --delete kalyan`
+ To merge brach you have to use `git merge newbrachname`.It will add the source code in newbranchname to active branch (master)
### remote commands:
====================
+ To check remote mode we have to use `git remote`
+ To change remotename use`git remote origin origin5`
+ To delete any remote `git remote remove remotename`

### Fork:
=========
+ To copy from remote to remote(copy one github account project to another github account)

### contribute:
===============
+ Add changes to fork project locally and contribute to owner


### Steps to contribute:
-------------------------
1. Fork the repository
2. Clone the repository
3. Create a new branch and add changes to the source code
4. Push the changes to remote
5. Compare & pull request

### Collaborate:
================

+ People who added by m owner they can able to modify files(add/delete) but not delete the project 

# React project uplode:
===========
+ 1. Create git repository with same name(ex: react-app)

2. Install GitHub pages in app folder 

npm install gh-pages --save-dev

3. *Package.json:* u need to add few elements in package.json

"homepage" : "https://username.github.io/appname

Ex: https://Raja.github.io/react-app

Scripts: 5
"predeploy" : " npm run build",
 "deploy":"gh-pages  -d  build"
}

Save it

4.  Git init

5. git remote add origin <GitHub link>

6. npm run deploy

7. Git stasts ( not mandatory)

8. Git add . Or git add --all

9. Git commit -am "<message>"

10. Git push origin master *Or* git push -u origin master
