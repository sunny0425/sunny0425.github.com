---
layout: post
title: "Fork A Repo on Github"
date: 2012-08-08 18:28
comments: true
categories: 
---
由 [Github Help](https://help.github.com/articles/fork-a-repo) 写的这份总结。
Fork 的流程总是忘记，在这里做个备忘，以供大家参考。

以 "Spoon-Knife" 项目为例

* 在需要 fork 的项目页面，点击 “Fork” 按钮
* clone 到本地
```
$ git clone https://github.com/username/Spoon-Knife.git
# Clones your fork of the repo into the current directory in terminal
```
* clone之后，有个默认的远程仓库叫做 “origin” 指向到 Github 上你自己的 fork。而不是原始的远程仓库（ fork 源），为了保持和 fork 源一致，需要添加另一个远程仓库叫做 “upstream”。
```
$ cd Spoon-Knife
# Changes the active directory in the prompt to the newly cloned "Spoon-Knife" directory
$ git remote add upstream https://github.com/octocat/Spoon-Knife.git
# Assigns the original repo to a remote called "upstream"
$ git fetch upstream
# Pulls in changes not present in your local repository, without modifying your files
```
* 在做了一些提交到你自己的本地代码库之后，push 到你自己的远程代码库：
```
$ git push origin master
# Pushes commits to your remote repo stored on GitHub
```
* 如果 fork 源代码库有更新，你可以把这些更新放到自己的 fork 的项目中
```
$ git fetch upstream
# Fetches any new changes from the original repo
$ git merge upstream/master
# Merges any changes fetched into your working files
```
* 将代码提交到 Github 上你自己的项目
```
$ git push origin master
```