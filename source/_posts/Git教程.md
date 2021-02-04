---
title: Git教程
date: 2021-02-04 18:50:59
tags: Git
categories:
	- 教程
	- Git
cover: https://gitee.com/chenyustudy/pic-go/raw/master/git.jpg
top_img: https://gitee.com/chenyustudy/pic-go/raw/master/git.jpg
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

- 修改readme.txt文件，然后执行`git status`命令查看结果

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status`命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，`readme.txt`被修改过了，但还没有准备提交。

虽然Git告诉我们文件被修改了，但是如果一段时间过后，已经记不清是怎么修改的，这个时候就需要`git diff`这个命令查看：

```
$ git diff readme.txt 
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```

`git diff`顾名思义就是查看difference，通过上面的命令就可以看到，我们在第一行添加了一个单词distributed。

知道对readme.txt作了什么修改后，再提交就放心多了，提交修改和提交新文件的方法一样，第一步是`git add`:

```
$ git add readme.txt
```

同样没有任何输出，在执行第二步`git commit`之前，再运行`git status`看看当前仓库的状态

```
$ git status
On branch master
Changes to be committed:
	(use "git reset HEAD <file>..." to unstage)
	
	modified: readme.txt
```

`git status`告诉我们，将要被提交的修改包括`readme.txt`，下一步，放心的提交了：

```
$git commit -m "add distributed"
[master e475afc] add distributed
 1 file changed,1 insertion(+),1 deletion(-)
```

提交后，我们再用`git status`命令看看仓库的当前状态：

```
$ git status
On branch master
nothing to commit,working tree clean
```

Git告诉我们当前没有需要提交的修改，而且，工作目录是干净的

## 版本回退

​		Git会对每次的提交进行“保存”，这个保存在Git中被称为`commit`，一旦文件改乱了，或者误删了文件，还可以从最近的一个`commit`恢复，然后继续工作，而不是以前的文件全部丢失。

​		我们想想我们的`readme.txt`有几个版本，当然了，时间过去越久，你可能越来越不记得，此时，你需要`git log`命令：

```
$ git log
commit 1094adb7b9b3807259d8cb349e7df1d4d6477073 (HEAD -> master)
Author: chenyu521 <longtao071666@outlook.com>
Date:   Fri May 18 21:06:15 2018 +0800

    append GPL

commit e475afc93c209a690c39c13a46716e8fa000c366
Author: chenyu521 <longtao071666@outlook.com>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: chenyu521 <longtao071666@outlook.com>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
```

`git log`显示从最近到最远的提交日志，我们可以看到3次提交，最近的一次是`append GPL`，上一次是`add distributed`，最早的一次的`wrote a readme file`

好了，现在我们准备版本回退

​		首先，Git必须知道当前版本是哪个版本，在Git中，用`HEAD`表示当前版本，上一个版本即使`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^` ？，这样肯定不好，所以写成`HEAD~100`。

​		现在，我们要把当前版本`append GPL`回退到上一个版本`add distributed`，就可以使用`git reset`命令

```
$ git reset --hard HEAD^
HEAD is now at e475afc add distributed
```

现在我们查看一下`readme.txt`内容，看看是不是版本`add distributed`：

```
$ cat readme.txt
Git is a distributed version control system.
Git is free software.
```

果然我们回来了，此时我们查看`git log`

```
$ git log
commit e475afc93c209a690c39c13a46716e8fa000c366 (HEAD -> master)
Author: chenyu521 <longtao071666@outlook.com>
Date:   Fri May 18 21:03:36 2018 +0800

    add distributed

commit eaadf4e385e865d25c48e7ca9c8395c3f7dfaef0
Author: chenyu521 <longtao071666@outlook.com>
Date:   Fri May 18 20:59:18 2018 +0800

    wrote a readme file
```

最新的哪个版本`append GPL`已经看不到了，想回去，怎么办？

只要窗口没有关掉，找到那个`append GPL`的`commit id`是`1094adb...`，于是我们可以指定回到此版本：

```
$ git reset --hard 1094a
HEAD is now at 83b0afe append GPL
```

版本号写前几位就行

如果你窗口关掉了，找不到`commit id`，那可以使用`git reflog`，这个Git提供的命令用来记录你的每一次命令：

```
$ git reflog
e475afc HEAD@{1}: reset: moving to HEAD^
1094adb (HEAD -> master) HEAD@{2}: commit: append GPL
e475afc HEAD@{3}: commit: add distributed
eaadf4e HEAD@{4}: commit (initial): wrote a readme file
```

从输出可以知道，`append GPL`的`commit id`是`1094adb`，我们就又可以回去了

## 管理修改

`git add`再`git commit`，也可以别着急提交第一次修改，先`git add`第二次修改，再`git commit`，就相当于把两次修改合并后一块提交了：

第一次修改 -> `git add` -> 第二次修改 -> `git add` -> `git commit`

每次修改，如果不用`git add`到暂存区，那就不会加入到`commit`中。

## 撤销修改

命令`git checkout -- readme.txt`意思就是，把`readme.txt`文件在工作区的修改全部撤销，这里有两种情况：

一种是`readme.txt`自修改后还没有被放到暂存区，现在，撤销修改就回到和版本库一模一样的状态；

一种是`readme.txt`已经添加到暂存区后，又作了修改，现在，撤销修改就回到添加到暂存区后的状态。

总之，就是让这个文件回到最近一次`git commit`或`git add`时的状态。

`git checkout -- file`命令中的`--`很重要，没有`--`，就变成了“切换到另一个分支”的命令，我们在后面的分支管理中会再次遇到`git checkout`命令。

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

## 删除文件

命令`git rm`用于删除一个文件。如果一个文件已经被提交到版本库，那么你永远不用担心误删，但是要小心，你只能恢复文件到最新版本，你会丢失**最近一次提交后你修改的内容**。

# 远程仓库

## 添加远程库

```
$ git remote add origin https://github.com/你的用户名/你的仓库名
```

下一步推送本地库内容到远程库：

```
$ git push --set-upstream origin master
```

```
$ git push -u origin master
```

上面两条都可以

把本地库的内容推送到远程，用`git push`命令，实际上是把当前分支`master`推送到远程。

由于远程库是空的，我们第一次推送`master`分支时，加上了`-u`参数，Git不但会把本地的`master`分支内容推送的远程新的`master`分支，还会把本地的`master`分支和远程的`master`分支关联起来，在以后的推送或者拉取时就可以简化命令。



要关联一个远程库，使用命令`git remote add origin git@server-name:path/repo-name.git`；

关联后，使用命令`git push -u origin master`第一次推送master分支的所有内容；

此后，每次本地提交后，只要有必要，就可以使用命令`git push origin master`推送最新修改；

## 从远程库克隆

使用命令`git clone`克隆

```
$ git clone https://github.com/你的用户名/你的仓库名
```

# 分支管理

## 创建和合并分支

首先，我们创建`dev`分支，然后切换到`dev`分支：

```
$ git checkout -b dev
Switched to a new branch 'dev'
```

`git checkout`命令加上`-b`参数表示创建并切换，相当于以下两条命令：

```
$ git branch dev
$ git checkout dev
Switched to branch 'dev'
```

然后，用`git branch`命令查看当前分支：

```
$ git branch
* dev
  master
```

查看分支：`git branch`

创建分支：`git branch <name>`

切换分支：`git checkout <name>`或者`git switch <name>`

创建+切换分支：`git checkout -b <name>`或者`git switch -c <name>`

合并某分支到当前分支：`git merge <name>`

删除分支：`git branch -d <name>`

## 分支管理策略

合并分支时，加上`--no-ff`参数就可以用普通模式合并，合并后的历史有分支，能看出来曾经做过合并，而`fast forward`合并就看不出来曾经做过合并。

## Bug分支

当手头工作没有完成时，先把工作现场`git stash`一下，然后去修复bug，修复后，再`git stash pop`，回到工作现场；

在master分支上修复的bug，想要合并到当前dev分支，可以用`git cherry-pick <commit>`命令，把bug提交的修改“复制”到当前分支，避免重复劳动。

## Feature分支

开发一个新feature，最好新建一个分支；

如果要丢弃一个没有被合并过的分支，可以通过`git branch -D <name>`强行删除。

## 多人协作

- 查看远程库信息，使用`git remote -v`；
- 本地新建的分支如果不推送到远程，对其他人就是不可见的；
- 从本地推送分支，使用`git push origin branch-name`，如果推送失败，先用`git pull`抓取远程的新提交；
- 在本地创建和远程分支对应的分支，使用`git checkout -b branch-name origin/branch-name`，本地和远程分支的名称最好一致；
- 建立本地分支和远程分支的关联，使用`git branch --set-upstream branch-name origin/branch-name`；
- 从远程抓取分支，使用`git pull`，如果有冲突，要先处理冲突。

因此，多人协作的工作模式通常是这样：

1. 首先，可以试图用`git push origin <branch-name>`推送自己的修改；
2. 如果推送失败，则因为远程分支比你的本地更新，需要先用`git pull`试图合并；
3. 如果合并有冲突，则解决冲突，并在本地提交；
4. 没有冲突或者解决掉冲突后，再用`git push origin <branch-name>`推送就能成功！

如果`git pull`提示`no tracking information`，则说明本地分支和远程分支的链接关系没有创建，用命令`git branch --set-upstream-to <branch-name> origin/<branch-name>`。

这就是多人协作的工作模式，一旦熟悉了，就非常简单。

- rebase操作可以把本地未push的分叉提交历史整理成直线；
- rebase的目的是使得我们在查看历史提交的变化时更容易，因为分叉的提交需要三方对比。

# 标签管理

## 创建标签

- 命令`git tag <tagname>`用于新建一个标签，默认为`HEAD`，也可以指定一个commit id；
- 命令`git tag -a <tagname> -m "blablabla..."`可以指定标签信息；
- 命令`git tag`可以查看所有标签。

## 操作标签

- 命令`git push origin <tagname>`可以推送一个本地标签；
- 命令`git push origin --tags`可以推送全部未推送过的本地标签；
- 命令`git tag -d <tagname>`可以删除一个本地标签；
- 命令`git push origin :refs/tags/<tagname>`可以删除一个远程标签。