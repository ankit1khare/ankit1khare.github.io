---
layout: post
title:  "My notes on GitHub!"
description: Intro to GitHub
excerpt: Quick intro to github and easy reference of frequently used commands 
date:   2017-09-28 14:55:52 +0200
---
**Here are two very interesting videos which would help you get started with GitHub:**
1. [https://www.youtube.com/watch?v=SWYqp7iY_Tc](https://www.youtube.com/watch?v=SWYqp7iY_Tc&t=3s){:target="_blank"} (Intro)
2. [https://www.youtube.com/watch?v=HVsySz-h9r4](https://www.youtube.com/watch?v=HVsySz-h9r4&t=1009s){:target="_blank"} (Intro)
3. [https://www.youtube.com/watch?v=xuB1Id2Wxak](https://www.youtube.com/watch?v=xuB1Id2Wxak&t=1701s){:target="_blank"} (Intro + details)

**Let's start with one-liners:**
- git is a version control tool 
- Github Inc is a organization that provides web-based hosting services for distributed version control
- Github Inc is git based and they have their own features as well
- git is open source 
- git is  written in C and hence it is fast
- git is lightweight (it doesn't use a lot of space or processing power of your computer)
- git does lossless compression of files to store them on local repository or central repository 
- git is secure and it follows SHAI encryption
- git is follows a non-linear structure called Directed Acyclic Graph (DAG)
<br><br>

**Setup:**
- ssh-keygen
- cat <path of ssh key>
<br> Add the key to your github settings. After this, you will be able to push or pull from your central repo.
  
<br>

**Common commands and their use:**
- git clone {url} {folder where to clone}
- git init
- git status
- git remote add origin {git url}
- git remote -v

<br><br>
- git add -A
- git commit -m "msg"
- git commit -a -m "msg"
adds the files to the staging area and then commits them.
- git checkout <last 8 digit of your commit hash id> <filename to revert>

<br>
- git log
- git diff
check the difference between working tree (your files in the project folder) and the local repository  

<br>
- git pull origin master
- git push -u origin master

<br><br>

**Common Branching commands:**
- git Branch
- git branch {brname}
The branch will contain everything in the master branch

<br>
- git checkout {brname}
move to the branch specified

- git checkout -b[ branch_name]
<br>This command will create a new branch and checkout the new branch at the same time.

- git push -u origin {brname}
push branch to central repo. Be on the branch which you are pushing. 
<br><br>

**Few other useful commands:**
- git remote get-url origin
- git remote set-url origin  <git@github.com:ankit1khare/Img-Cap.git>

- git reset HEAD --
A little tricky. I'll have to explain this in another post

- git rm --cached . 
<br>Suppose you added a file to staging area. But now you want to remove it since it is not needed anymore but might be needed later on. Use this command to remove a file from index before commit. You have files indexed before commit but you want to remove one of them from index so that you don't commit it accidentally. Changes to the file remain intact. This doesn't apply to "untracked" files.

- git merge <branch_name>
<br>Suppose you want to merge your new branch with master. Then you must be on master branch and the branch name in above command must be your new branch. So, be on destination branch where merging is happening.

- git branch --merged
<br> Displays all the merges occured so far.

- git rebase <branch-name>
<br> You are on master. And you have a branch ahead of master. Now, when you rebase the branch it will copy all the new content from your branch to master and set the head of your branch to the tip of your master linearly. So, master will have everything that was extra in new branch but it would seem like you developed all this linearly.
  
