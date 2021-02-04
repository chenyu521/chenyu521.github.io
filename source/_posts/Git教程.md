---
title: Git教程
date: 2021-02-04 18:50:59
tags: Git
categories:
	- 教程
	- Git
---

# 安装Git

可以直接从Git官网[下载]( https://git-scm.com/downloads) 安装程序，然后按默认选项安装即可。

安装完成后，在开始菜单里找到Git-Git Bash，出现一个类似于命令行窗口一样的东西，说明Git安装成功。

![image-20210204181019540](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210204181019540.png)

安装完成后，进行设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

注意：git config命令的--global参数使用之后表示这台机器上所有的Git仓库都会使用这个配置。

# 创建版本库

- 版本库介绍

  版本库又名仓库，英文名repository，简单理解就是一个目录，这个目录里所有文件都可以被Git管理起来，每个文件的修改、删除，Git都可以跟踪，方便在任何时候都可以追踪历史，或者在将来某个时刻可以“还原”。

- 创建版本库

  - 第一，先选择一个合适的地方，创建一个空目录

  ```
  $ mkdir test
  $ cd test
  $ pwd
  /f/test
  ```

  pwd命令用于显示当前目录

  - 第二，通过`git init`命令把这个目录变成Git可以管理的仓库：

  ```
  $ git init
  Initialized empty Git repository in 
  /f/test
  ```

  这个时候Git就已经把仓库建好了，并且告诉你这是一个空仓库(empty Git repository)，然后当前目录下多了一个`.git`的文件夹，这个文件夹是Git用来跟踪管理版本库的，注意：里面内容请勿修改。

- 将文件添加到版本库

  - 我们先在目录下编写一个`readme.txt`文件，内容随意
  - 使用命令`git add`告诉Git，把文件添加到仓库：

  ```
  $ git add readme.txt
  ```

  - 使用命令`git commit`告诉Git，把文件提交到仓库：

  ```
  $ git commit -m "wrote a readme file"
  ```

  简单理解一下此命令，-m后面输入的是本次提交的说明

  其实也可以`add`多个文件，然后一次`commit`，比如：

  ```
  $ git add file1.txt
  $ git add file2.txt file3.txt
  $ git commit -m "add 3 files."
  ```

  - 可能出现的问题及原因：
    - 输入`git add readme.txt`，得到错误：`fatal:not a git repository(or any of the parent directories)`。
    - Git命令必须在Git仓库目录内执行(`git init`除外)，在仓库目录外执行没有意义。
    - 输入`git add readme.txt`，得到错误`fatal:pathspec 'readme.txt' did not match any files`。
    - 添加某个文件时，该文件必须在当前目录下存在，用`ls`或者`dir`命令查看当前目录的文件，查看文件是否存在，或者是否写错了文件名

# 版本管理