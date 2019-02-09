---
layout: post
title:  "My notes on GitHub!"
description: Intro to GitHub
excerpt: Quick intro to github and easy reference of frequently used commands 
date:   2017-09-28 14:55:52 +0200
---
Here are two very interesting videos which would help you get started with GitHub:
1. [https://www.youtube.com/watch?v=SWYqp7iY_Tc](https://www.youtube.com/watch?v=SWYqp7iY_Tc&t=3s){:target="_blank"} (Intro)
2. [https://www.youtube.com/watch?v=HVsySz-h9r4](https://www.youtube.com/watch?v=HVsySz-h9r4&t=1009s){:target="_blank"} (Intro)
3. [https://www.youtube.com/watch?v=xuB1Id2Wxak](https://www.youtube.com/watch?v=xuB1Id2Wxak&t=1701s){:target="_blank"} (Intro + details)

Let's start with one-liners:
- git is a version control tool 
- Github Inc is a organization that provides web-based hosting services for distributed version control
- Github Inc is git based and they have their own features as well
- git is open source 
- git is  written in C and hence it is fast
- git is lightweight (it doesn't use a lot of space or processing power of your computer)
- git does lossless compression of files to store them on local repository or central repository 
- git is secure and it follows SHAI encryption
- git is follows a non-linear structure called Acyclic Graph

Common commands and their use:
- git clone {url} {folder where to clone}
- git init
- git status
- git remote add origin {git url}
- git remote -v


- git add -A
- git commit -m "msg"
- git commit -a -m "msg"
adds the files to the staging area and then commits them.

- git log
- git diff
check the difference between working tree (your files in the project folder) and the local repository  

- git pull origin master
- git push -u origin master

Common Branching commands:
- git Branch
- git branch {brname}
The branch will contain everything in the master branch

- git checkout {brname}
move to the branch specified

- git push -u origin {brname}
push branch to central repo. Be on the branch which you are pushing. 

Few other useful commands:
- git remote get-url origin
- git remote set-url origin  <git@github.com:ankit1khare/Img-Cap.git>

- git reset HEAD --
A little tricky. I'll have to explain this in another post

- git rm --cached . 
Suppose you added a file to staging area. But now you want to remove it since it is not needed anymore but might be needed later on. Use this command to remove a file from index before commit. You have files indexed before commit but you want to remove one of them from index so that you don't commit it accidentally. Changes to the file remain intact. This doesn't apply to "untracked" files.
