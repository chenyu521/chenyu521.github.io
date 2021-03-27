---
title: linux基础
date: 2021-03-09 21:38:36
tags:
	- 教程
	- Linux
	- 笔记
categories:
	- 教程
	- Linux
---

# Linux系统简介

## 什么是Linux

 Linux 就是一个操作系统，就像你多少已经了解的 Windows（xp，7，8）和 Mac OS 。

## Linux与Windows有什么不同？

- 免费与收费
- 软件与支持
- 安全性
- 使用习惯
- 可定制性

# 基本概念及操作

## 什么是终端

 通常我们在使用 Linux 时，并不是直接与系统打交道，而是通过一个叫做 Shell 的中间程序来完成的，在图形界面下为了实现让我们在一个窗口中完成用户输入和显示输出，Linux 系统还提供了一个叫做终端模拟器的程序（Terminal）。

## 命令行

> 在Linux中，最重要的就是命令，这就包含了两个过程，输入和输出
>
> 输入：输入当然就是打开终端，然后按键盘输入，然后按回车执行
>
> 输出：输出会返回你想要的结果

## 重要快捷键

- `Tab`：使用Tab键来进行命令补全
- `Ctrl`+`C`：强行终止当前程序
- `Ctrl`+`d`：键盘输入结束或退出终端
- `Ctrl`+`s`：暂停当前程序，暂停后按下任意键恢复运行
- `Ctrl`+`z`：将当前程序放到后台运行，恢复到前台为命令`fg`
- `Ctrl`+`a`：将光标移至输入行头，相当于`home`键
- `Ctrl`+`e`：将光标移至输入行末，相当于`End`键
- `Ctrl`+`k`：删除从光标所在位置到行末
- `Alt`+`Backspace`：向前删除一个单词
- `Shift`+`PgUp`：将终端显示向上滚动
- `Shift`+`PgDn`：将终端显示向下滚动

### 学会利用历史输入命令

很简单，你可以使用键盘上的方向上键`↑`，恢复你之前输入过的命令，你一试便知。

### 学会使用通配符

 通配符是一种特殊语句，主要有星号（*）和问号（?），用来对字符串进行模糊匹配（比如文件名、参数名）。当查找文件夹时，可以使用它来代替一个或多个真正字符；当不知道真正字符或者懒得输入完整名字时，常常使用通配符代替一个或多个真正字符。

例如：

```bash
ls *.txt
```

[![1](https://gitee.com/chenyustudy/pic-go/raw/master/document-uid735639labid2timestamp1531471952505.png)](https://gitee.com/chenyustudy/pic-go/raw/master/document-uid735639labid2timestamp1531471952505.png)

```bash
touch love_{1..10}_shiyanlou.txt
```

[![pic](https://gitee.com/chenyustudy/pic-go/raw/master/document-uid735639labid2timestamp1531471982853.png)](https://gitee.com/chenyustudy/pic-go/raw/master/document-uid735639labid2timestamp1531471982853.png)

Shell常用通配符：

| 字符                    | 含义                                       |
| ----------------------- | ------------------------------------------ |
| `*`                     | 匹配 0 或多个字符                          |
| `?`                     | 匹配任意一个字符                           |
| `[list]`                | 匹配 list 中的任意单一字符                 |
| `[^list]`               | 匹配 除 list 中的任意单一字符以外的字符    |
| `[c1-c2]`               | 匹配 c1-c2 中的任意单一字符 如：[0-9][a-z] |
| `{string1,string2,...}` | 匹配 string1 或 string2 (或更多)其一字符串 |
| `{c1..c2}`              | 匹配 c1-c2 中全部字符 如{1..10}            |

### 学会在命令行中获取帮助

在 Linux 环境中，如果你遇到困难，可以使用`man`命令，它是`Manual pages`的缩写。

你可以使用如下方式来获得某个命令的说明和使用方式的详细介绍：

```bash
man <command_name>
```

比如你想查看 man 命令本身的使用方式，你可以输入：

```bash
man man
```

通常情况下，man 手册里面的内容都是英文的，这就要求你有一定的英文基础。man 手册的内容很多，涉及了 Linux 使用过程中的方方面面。为了便于查找，man 手册被进行了分册（分区段）处理，在 Research UNIX、BSD、OS X 和 Linux 中，手册通常被分为 8 个区段，安排如下：

| 区段 | 说明                                      |
| ---- | ----------------------------------------- |
| 1    | 一般命令                                  |
| 2    | 系统调用                                  |
| 3    | 库函数，涵盖了 C 标准函数库               |
| 4    | 特殊文件（通常是/dev 中的设备）和驱动程序 |
| 5    | 文件格式和约定                            |
| 6    | 游戏和屏保                                |
| 7    | 杂项                                      |
| 8    | 系统管理命令和守护进程                    |

要查看相应区段的内容，就在 man 后面加上相应区段的数字即可，如：

```bash
man 1 ls
```

会显示第一区段中的`ls`命令 man 页面。

所有的手册页遵循一个常见的布局，为了通过简单的 ASCII 文本展示而被优化，而这种情况下可能没有任何形式的高亮或字体控制。一般包括以下部分内容：

**NAME（名称）**

> 该命令或函数的名称，接着是一行简介。

**SYNOPSIS（概要）**

> 对于命令，正式的描述它如何运行，以及需要什么样的命令行参数。对于函数，介绍函数所需的参数，以及哪个头文件包含该函数的定义。

**DESCRIPTION（说明）**

> 命令或函数功能的文本描述。

**EXAMPLES（示例）**

> 常用的一些示例。

**SEE ALSO（参见）**

> 相关命令或函数的列表。

也可能存在其它部分内容，但这些部分没有得到跨手册页的标准化。常见的例子包括：OPTIONS（选项），EXIT STATUS（退出状态），ENVIRONMENT（环境），BUGS（程序漏洞），FILES（文件），AUTHOR（作者），REPORTING BUGS（已知漏洞），HISTORY（历史）和 COPYRIGHT（版权）。

通常 man 手册中的内容很多，你可能不太容易找到你想要的结果，不过幸运的是你可以在 man 中使用搜索`/<你要搜索的关键字>`，查找完毕后你可以使用`n`键切换到下一个关键字所在处，`shift+n`为上一个关键字所在处。使用`Space`（空格键）翻页，`Enter`（回车键）向下滚动一行，或者使用`k`，`j`（vim 编辑器的移动键）进行向前向后滚动一行。按下`h`键为显示使用帮助（因为 man 使用 less 作为阅读器，实为`less`工具的帮助），按下`q`退出。

想要获得更详细的帮助，你还可以使用`info`命令，不过通常使用`man`就足够了。如果你知道某个命令的作用，只是想快速查看一些它的某个具体参数的作用，那么你可以使用`--help`参数，大部分命令都会带有这个参数，如：

```bash
ls --help
```

# 用户及文件权限管理

## Linux用户管理

Linux 是一个可以实现多用户登录的操作系统，比如“李雷”和“韩梅梅”都可以同时登录同一台主机，他们共享一些主机的资源，但他们也分别有自己的用户空间，用于存放各自的文件。但实际上他们的文件都是放在同一个物理磁盘上的甚至同一个逻辑分区或者目录里，但是由于 Linux 的 **用户管理** 和 **权限机制**，不同用户不可以轻易地查看、修改彼此的文件。

### 查看用户

```bash
who am i

# 或者

who mom likes
```

`who` 命令其它常用参数

| 参数 | 说明                       |
| ---- | -------------------------- |
| `-a` | 打印能打印的全部           |
| `-d` | 打印死掉的进程             |
| `-m` | 同`am i`，`mom likes`      |
| `-q` | 打印当前登录用户数及用户名 |
| `-u` | 打印当前登录用户登录信息   |
| `-r` | 打印运行等级               |

### 创建用户

在 Linux 系统里， `root` 账户拥有整个系统至高无上的权限，比如新建和添加用户。

> root 权限，系统权限的一种，与 SYSTEM 权限可以理解成一个概念，但高于 Administrator 权限，root 是 Linux 和 UNIX 系统中的超级管理员用户帐户，该帐户拥有整个系统至高无上的权力，所有对象他都可以操作，所以很多黑客在入侵系统的时候，都要把权限提升到 root 权限，这个操作等同于在 Windows 下就是将新建的非法帐户添加到 Administrators 用户组。更比如安卓操作系统中（基于 Linux 内核）获得 root 权限之后就意味着已经获得了手机的最高权限，这时候你可以对手机中的任何文件（包括系统文件）执行所有增、删、改、查的操作。

大部分 Linux 系统在安装时都会建议用户新建一个用户而不是直接使用 root 用户进行登录，当然也有直接使用 root 登录的例如 Kali（基于 Debian 的 Linux 发行版，集成大量工具软件，主要用于数字取证的操作系统）。一般我们登录系统时都是以普通账户的身份登录的，要创建用户需要 root 权限，这里就要用到 `sudo` 这个命令了。不过使用这个命令有两个大前提，一是你要知道当前登录用户的密码，二是当前用户必须在 `sudo` 用户组。

su，su- 与 sudo

**需要注意 Linux 环境下输入密码是不会显示的。**

`su <user>` 可以切换到用户 user，执行时需要输入目标用户的密码，`sudo <cmd>` 可以以特权级别运行 cmd 命令，需要当前用户属于 sudo 组，且需要输入当前用户的密码。`su - <user>` 命令也是切换用户，但是同时用户的环境变量和工作目录也会跟着改变成目标用户所对应的。

现在我们新建一个叫 `lilei` 的用户：

```bash
sudo adduser lilei
```

给lilei用户设置密码

```bash
sudo passwd lilei
```

现在你已经创建好一个用户，并且你可以使用你创建的用户登录了，使用如下命令切换登录用户：

```bash
su -l lilei
```

输入刚刚设置的 lilei 的密码，然后输入如下命令并查看输出：

```bash
who am i
whoami
pwd
```

## 用户组

在 Linux 里面每个用户都有一个归属（用户组），用户组简单地理解就是一组用户的集合，它们共享一些资源和权限，同时拥有私有资源，就跟家的形式差不多，你的兄弟姐妹（不同的用户）属于同一个家（用户组），你们可以共同拥有这个家（共享资源），爸妈对待你们都一样（共享权限），你偶尔写写日记，其他人未经允许不能查看（私有资源和权限）。当然一个用户是可以属于多个用户组的，正如你既属于家庭，又属于学校或公司。

### 查看用户组

在 Linux 里面如何知道自己属于哪些用户组呢？

方法一：使用 groups 命令

```bash
groups <username>
```

方法二：查看 `/etc/group` 文件

```bash
cat /etc/group | sort
```

这里 `cat` 命令用于读取指定文件的内容并打印到终端输出，后面会详细讲它的使用。 `| sort` 表示将读取的文本进行一个字典排序再输出，然后你将看到如下一堆输出，你可以在最下面看到你想查的用户组信息
没找到？没关系，你可以使用 `grep` 命令过滤掉一些你不想看到的结果：

```bash
cat /etc/group | grep -E "username"
```

`/etc/group` 文件格式说明

/etc/group 的内容包括用户组（Group）、用户组口令、GID（组 ID） 及该用户组所包含的用户（User），每个用户组一条记录。格式如下：

> group_name:password:GID:user_list

你看到上面的 password 字段为一个 `x`，并不是说密码就是它，只是表示密码不可见而已。

这里需要注意，如果用户的 GID 等于用户组的 GID，那么最后一个字段 `user_list` 就是空的，这里的 GID 是指用户默认所在组的 GID，可以使用 `id` 命令查看。

### 将其它用户加入 sudo 用户组

默认情况下新创建的用户是不具有 root 权限的，也不在 sudo 用户组，可以让其加入 sudo 用户组从而获取 root 权限：使用 `usermod` 命令可以为用户添加用户组，同样使用该命令你必需有 root 权限，你可以直接使用 root 用户为其它用户添加用户组，或者用其它已经在 sudo 用户组的用户使用 sudo 命令获取权限来执行该命令。

```bash
groups lilei
sudo usermod -G sudo lilei
groups lilei
```

然后你再切换回 lilei 用户，现在就可以使用 sudo 获取 root 权限了。

### 删除用户和用户组

删除用户是很简单的事：

```bash
sudo deluser lilei --remove-home
```

使用 `--remove-home` 参数在删除用户时候会一并将该用户的工作目录一并删除。如果不使用那么系统会自动在 /home 目录为该用户保留工作目录。

删除用户组可以使用 `groupdel` 命令，倘若该群组中仍包括某些用户，则必须先删除这些用户后，才能删除群组。

## Linux文件权限

> 文件权限就是文件的访问控制权限，即哪些用户和组群可以访问文件以及可以执行什么样的操作。
>
> Unix/Linux 系统是一个典型的多用户系统，不同的用户处于不同的地位，对文件和目录有不同的访问权限。为了保护系统的安全性，Unix/Linux 系统除了对用户权限作了严格的界定外，还在用户身份认证、访问控制、传输安全、文件读写权限等方面作了周密的控制。
>
> 在 Unix/Linux 中的每一个文件或目录都包含有访问权限，这些访问权限决定了谁能访问和如何访问这些文件和目录。

我们之前已经很多次用到 `ls` 命令了，如你所见，我们用它来列出并显示当前目录下的文件，当然这是在不带任何参数的情况下，它能做的当然不止这么多，现在我们就要用它来查看文件权限。

使用较长格式列出文件：

```bash
ls -l
```

[![image-20210220140745129](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220140745129.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220140745129.png)

你可能除了知道最后面那一项是文件名之外，其它项就不太清楚了，那么到底是什么意思呢：

[![pic](https://gitee.com/chenyustudy/pic-go/raw/master/3-10.png)](https://gitee.com/chenyustudy/pic-go/raw/master/3-10.png)

- 文件类型

关于文件类型，这里有一点你必需时刻牢记 **Linux 里面一切皆文件**，正因为这一点才有了设备文件（ `/dev` 目录下有各种设备文件，大都跟具体的硬件设备相关）这一说。 `socket`：网络套接字。`pipe` 管道，这个东西很重要，我们以后将会讨论到，这里你先知道有它的存在即可。`软链接文件`：链接文件是分为两种的，另一种当然是“硬链接”（硬链接不常用，而软链接等同于 Windows 上的快捷方式，你记住这一点就够了）。

- 文件权限

读权限，表示你可以使用 `cat <file name>` 之类的命令来读取某个文件的内容；写权限，表示你可以编辑和修改某个文件的内容；

执行权限，通常指可以运行的二进制程序文件或者脚本文件，如同 Windows 上的 `exe` 后缀的文件，不过 Linux 上不是通过文件后缀名来区分文件的类型。你需要注意的一点是，**一个目录同时具有读权限和执行权限才可以打开并查看内部文件，而一个目录要有写权限才允许在其中创建其它文件**，这是因为目录文件实际保存着该目录里面的文件的列表等信息。

所有者权限，这一点相信你应该明白了，至于所属用户组权限，是指你所在的用户组中的所有其它用户对于该文件的权限，比如，你有一个 iPad，那么这个用户组权限就决定了你的兄弟姐妹有没有权限使用它破坏它和占有它。

- 链接数

> 链接到该文件所在的 inode 结点的文件名数目（关于这个概念涉及到 Linux 文件系统的相关概念知识，不在本课程的讨论范围，感兴趣的用户可以查看 [硬链接和软链接的联系与区别](https://www.ibm.com/developerworks/cn/linux/l-cn-hardandsymb-links/index.html#major2)）。

- 文件大小

> 以 inode 结点大小为单位来表示的文件大小，你可以给 ls 加上 `-lh` 参数来更直观的查看文件的大小。

明白了文件权限的一些概念，我们顺带补充一下关于 `ls` 命令的一些其它常用的用法：

- 显示除了 `.`（当前目录）和 `..`（上一级目录）之外的所有文件，包括隐藏文件（Linux 下以 `.` 开头的文件为隐藏文件）。

```bash
ls -a
```

当然，你可以同时使用 `-a` 和 `-l` 参数：

```bash
ls -al
```

查看某一个目录的完整属性，而不是显示目录里面的文件属性：

```bash
ls -dl <目录名>
```

- 显示所有文件大小，并以普通人类能看懂的方式呈现：

```bash
ls -asSh
```

其中小 s 为显示文件大小，大 S 为按文件大小排序，若需要知道如何按其它方式排序，可以使用 `man ls` 命令查询。

### 变更文件所有者

> 若前面已经执行删除 lilei 用户的命令，这里重新创建一下。

切换到 lilei 用户，然后在 /home/lilei 目录新建一个文件，命名为 `iphone11`。

```bash
su - lilei
pwd
touch iphone11
ls -alh iphone11
```

可见文件所有者是 lilei ：

[![image-20210220142508133](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220142508133.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220142508133.png)

现在切换回到 test 用户，使用以下命令变更文件所有者为 test。

```bash
# 需要切换到 test 用户执行以下操作
cd /home/lilei
ls
sudo chown test iphone11
```

现在查看，发现文件所有者成功修改为 test。

[![image-20210220142709932](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220142709932.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220142709932.png)

### 修改文件权限

如果你有一个自己的文件不想被其他用户读、写、执行，那么就需要对文件的权限做修改。文件的权限有两种表示方式：

- 方式一：二进制数字表示

[![pic](https://gitee.com/chenyustudy/pic-go/raw/master/3-14.png)](https://gitee.com/chenyustudy/pic-go/raw/master/3-14.png)

每个文件有三组固定的权限，分别对应拥有者，所属用户组，其他用户，**记住这个顺序是固定的**。文件的读写执行对应字母 `rwx`，以二进制表示就是 `111`，用十进制表示就是 `7`，对进制转换不熟悉的同学可以看看 [进制转换](https://baike.baidu.com/item/进制转换/3117222)。例如我们刚刚新建的文件 iphone11 的权限是 `rw-rw-rw-`，换成对应的十进制表示就是 666，这就表示这个文件的拥有者，所属用户组和其他用户具有读写权限，不具有执行权限。

如果我要将文件 `iphone11` 的权限改为只有我自己可以用那么就可以用这个方法更改它的权限。

为了演示，我先在文件里加点内容：

```bash
echo "echo \"hello test\"" > iphone11
```

然后修改权限：

```bash
chmod 600 iphone11
ls -alh iphone11
```

[![image-20210220143226694](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220143226694.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220143226694.png)

切换到 lilei 用户，尝试写入和读取操作，可以看到 lilei 用户已经不能读写这个 iphone11 文件了：

[![image-20210220143334585](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220143334585.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220143334585.png)

## adduser 和 useradd 的区别是什么

答：`useradd` 只创建用户，不会创建用户密码和工作目录，创建完了需要使用 `passwd <username>` 去设置新用户的密码。`adduser` 在创建用户的同时，会创建工作目录和密码（提示你设置），做这一系列的操作。其实 `useradd`、`userdel` 这类操作更像是一种命令，执行完了就返回。而 `adduser` 更像是一种程序，需要你输入、确定等一系列操作。

# Linux目录结构及文件基本操作

## 目录路径

### 路径

有人可能不明白这路径是指什么，有什么用。顾名思义，路径就是你要去哪儿的路线嘛。如果你想进入某个具体的目录或者想获得某个目录的文件（目录本身也是文件）那就得用路径来找到了。

使用 `cd` 命令可以切换目录，在 Linux 里面使用 `.` 表示当前目录，`..` 表示上一级目录（**注意，以 `.` 开头的文件都是隐藏文件，所以这两个目录必然也是隐藏的，你可以使用 `ls -a` 命令查看隐藏文件**），`-` 表示上一次所在目录，`～` 通常表示当前用户的 `home` 目录。使用 `pwd` 命令可以获取当前所在路径（绝对路径）。

进入上一级目录：

```bash
cd ..
```

进入你的 `home` 目录：

```bash
cd ~
# 或者 cd /home/<你的用户名>
```

使用 `pwd` 获取当前路径：

```bash
pwd
```

#### 绝对路径

关于绝对路径，简单地说就是以根” / “目录为起点的完整路径，以你所要到的目录为终点，表现形式如： `/usr/local/bin`，表示根目录下的 `usr` 目录中的 `local` 目录中的 `bin` 目录。

#### 相对路径

相对路径，也就是相对于你当前的目录的路径，相对路径是以当前目录 `.` 为起点，以你所要到的目录为终点，表现形式如： `usr/local/bin` （这里假设你当前目录为根目录）。你可能注意到，我们表示相对路径实际并没有加上表示当前目录的那个 `.` ，而是直接以目录名开头，因为这个 `usr` 目录为 `/` 目录下的子目录，是可以省略这个 `.` 的（以后会讲到一个类似不能省略的情况）；如果是当前目录的上一级目录，则需要使用 `..` ，比如你当前目录为 `/home/shiyanlou` 目录下，根目录就应该表示为 `../../` ，表示上一级目录（ `home` 目录）的上一级目录（ `/` 目录）。

下面我们以你的 `home` 目录为起点，分别以绝对路径和相对路径的方式进入 `/usr/local/bin` 目录：

```bash
# 绝对路径
cd /usr/local/bin
# 相对路径
cd ../../usr/local/bin
```

## Linux文件的基本操作

### 新建

#### 新建空白文件

使用 `touch` 命令创建空白文件，关于 `touch` 命令，其主要作用是来更改已有文件的时间戳的（比如，最近访问时间，最近修改时间），但其在不加任何参数的情况下，只指定一个文件名，则可以创建一个指定文件名的空白文件（不会覆盖已有同名文件），当然你也可以同时指定该文件的时间戳，更多关于 `touch` 命令的用法，会在文件搜索中涉及。

```bash
touch test
```

新建目录

使用 `mkdir`（make directories）命令可以创建一个空目录，也可同时指定创建目录的权限属性。

创建名为“ test ”的空目录：

```bash
mkdir test
```

使用 `-p` 参数，同时创建父目录（如果不存在该父目录），如下我们同时创建一个多级目录（这在安装软件、配置安装路径时非常有用）：

```bash
mkdir -p father/son/grandson
```

这里使用的路径是相对路径，代表在当前目录下生成，当然我们直接以绝对路径的方式表示也是可以的。

还有一点需要注意的是，若当前目录已经创建了一个 test 文件，再使用 `mkdir test` 新建同名的文件夹，系统会报错文件已存在。这符合 Linux 一切皆文件的理念。

### 复制

#### 复制文件

使用 `cp` 命令（copy）复制一个文件到指定目录。

将之前创建的 `test` 文件复制到 `/home/shiyanlou/father/son/grandson` 目录中：

```bash
cp test father/son/grandson
```

是不是很方便啊，如果在图形界面则需要先在源目录复制文件，再进到目的目录粘贴文件，而命令行操作步骤就一步到位了嘛。

#### 复制目录

如果直接使用 `cp` 命令复制一个目录的话，会出现如下错误：

[![image-20210220151423315](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220151423315.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220151423315.png)

要成功复制目录需要加上 `-r` 或者 `-R` 参数，表示递归复制，就是说有点“株连九族”的意思：

```bash
cd /home/test
mkdir family
cp -r father family
```

[![image-20210220151609230](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220151609230.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220151609230.png)

### 删除

#### 删除文件

使用 `rm`（remove files or directories）命令删除一个文件：

```bash
rm test
```

有时候你会遇到想要删除一些为只读权限的文件，直接使用 `rm` 删除会显示一个提示`是否删除有写保护的普通空文件'test'?`

你如果想忽略这提示，直接删除文件，可以使用 `-f` 参数强制删除：

```bash
rm -f test
```

#### 删除目录

跟复制目录一样，要删除一个目录，也需要加上 `-r` 或 `-R` 参数：

```bash
rm -r family
```

遇到权限不足删除不了的目录也可以和删除文件一样加上 `-f` 参数：

```bash
rm -rf family
```

### 移动文件与文件重命名

#### 移动文件

使用 `mv`（move or rename files）命令移动文件（剪切）。命令格式是 `mv 源目录文件 目的目录`。

例如将文件“ file1 ”移动到 `Documents` 目录：

```bash
mkdir Documents
touch file1
mv file1 Documents
```

[![image-20210220152800512](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220152800512.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220152800512.png)

#### 重命名

`mv` 命令除了能移动文件外，还能给文件重命名。命令格式为 `mv 旧的文件名 新的文件名`。

例如将文件“ file1 ”重命名为“ myfile ”：

```bash
mv file1 myfile
```

#### 批量重命名

要实现批量重命名，`mv` 命令就有点力不从心了，我们可以使用一个看起来更专业的命令 `rename` 来实现。不过它要用 perl 正则表达式来作为参数，关于正则表达式我们要在后面才会介绍到，这里只做演示，你只要记得这个 `rename` 命令可以批量重命名就好了，以后再重新学习也不会有任何问题，毕竟你已经掌握了一个更常用的 `mv` 命令。

`rename` 命令并不是内置命令，若提示无该命令可以使用 `sudo apt-get install rename` 命令自行安装。

```bash
cd /home/test/

# 使用通配符批量创建 5 个文件:
touch file{1..5}.txt

# 批量将这 5 个后缀为 .txt 的文本文件重命名为以 .c 为后缀的文件:
rename 's/\.txt/\.c/' *.txt

# 批量将这 5 个文件，文件名和后缀改为大写:
rename 'y/a-z/A-Z/' *.c
```

[![image-20210220153732699](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220153732699.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220153732699.png)

### 查看文件

- 使用cat, tac和nl命令查看文件

前两个命令都是用来打印文件内容到标准输出（终端），其中 `cat` 为正序显示，`tac` 为倒序显示。

> 标准输入输出：当我们执行一个 shell 命令行时通常会自动打开三个标准文件，即标准输入文件（stdin），默认对应终端的键盘、标准输出文件（stdout）和标准错误输出文件（stderr），后两个文件都对应被重定向到终端的屏幕，以便我们能直接看到输出内容。进程将从标准输入文件中得到输入数据，将正常输出数据输出到标准输出文件，而将错误信息送到标准错误文件中。

比如我们要查看之前从 `/etc` 目录下拷贝来的 `passwd` 文件：

```bash
cd /home/shiyanlou
cp /etc/passwd passwd
cat passwd
```

可以加上 `-n` 参数显示行号：

```bash
cat -n passwd
```

[![image-20210220154053263](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154053263.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154053263.png)

`nl` 命令，添加行号并打印，这是个比 `cat -n` 更专业的行号打印命令。

这里简单列举它的常用的几个参数：

```bash
-b : 指定添加行号的方式，主要有两种：
    -b a:表示无论是否为空行，同样列出行号("cat -n"就是这种方式)
    -b t:只列出非空行的编号并列出（默认为这种方式）
-n : 设置行号的样式，主要有三种：
    -n ln:在行号字段最左端显示
    -n rn:在行号字段最右边显示，且不加 0
    -n rz:在行号字段最右边显示，且加 0
-w : 行号字段占用的位数(默认为 6 位)
```

[![image-20210220154159835](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154159835.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154159835.png)

你会发现使用这几个命令，默认的终端窗口大小，一屏显示不完文本的内容，得用鼠标拖动滚动条或者滑动滚轮才能继续往下翻页，要是可以直接使用键盘操作翻页就好了，那么你就可以使用下面要介绍的命令。

- 使用more和less命令分页查看文件

如果说上面的 `cat` 是用来快速查看一个文件的内容的，那么这个 `more` 和 `less` 就是天生用来”阅读”一个文件的内容的，比如说 man 手册内部就是使用的 `less` 来显示内容。其中 `more` 命令比较简单，只能向一个方向滚动，而 `less` 为基于 `more` 和 `vi` （一个强大的编辑器）开发，功能更强大。`less` 的使用基本和 `more` 一致，具体使用请查看 man 手册，这里只介绍 `more` 命令的使用。

使用 `more` 命令打开 `passwd` 文件：

```bash
more passwd
```

[![image-20210220154329854](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154329854.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154329854.png)

打开后默认只显示一屏内容，终端底部显示当前阅读的进度。可以使用 `Enter` 键向下滚动一行，使用 `Space` 键向下滚动一屏，按下 `h` 显示帮助，`q` 退出。

- 使用head和tail命令查看文件

这两个命令，那些性子比较急的人应该会喜欢，因为它们一个是只查看文件的头几行（默认为 10 行，不足 10 行则显示全部）和尾几行。还是拿 passwd 文件举例，比如当我们想要查看最近新增加的用户，那么我们可以查看这个 `/etc/passwd` 文件，不过我们前面也看到了，这个文件里面一大堆乱糟糟的东西，看起来实在费神啊。因为系统新增加一个用户，会将用户的信息添加到 passwd 文件的最后，那么这时候我们就可以使用 `tail` 命令了：

```bash
tail /etc/passwd
```

甚至更直接的只看一行， 加上 `-n` 参数，后面紧跟行数：

```bash
tail -n 1 /etc/passwd
```

[![image-20210220154513965](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154513965.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220154513965.png)

关于 `tail` 命令，不得不提的还有它一个很牛的参数 `-f`，这个参数可以实现不停地读取某个文件的内容并显示。这可以让我们动态查看日志，达到实时监视的目的。

### 查看文件类型

我们可以使用 `file` 命令查看文件的类型：

```bash
file /bin/ls
```

[![image-20210220155045432](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220155045432.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220155045432.png)

说明这是一个可执行文件，运行在 64 位平台，并使用了动态链接文件（共享库）。

与 Windows 不同的是，如果你新建了一个 shiyanlou.txt 文件，Windows 会自动把它识别为文本文件，而 `file` 命令会识别为一个空文件。这个前面我提到过，在 Linux 中文件的类型不是根据文件后缀来判断的。当你在文件里输入内容后才会显示文件类型。

[![image-20210220162449416](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220162449416.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220162449416.png)

### 编辑文件

在 Linux 下面编辑文件通常我们会直接使用专门的命令行编辑器比如（emacs，vim，nano），由于涉及 Linux 上的编辑器的内容比较多，且非常重要，故我们有一门单独的基础课专门介绍这中一个编辑器 vim 。

> 强烈建议正在学习这门 Linux 基础课的你先在这里暂停一下，去学习 [vim 编辑器](https://www.lanqiao.cn/courses/2)的使用（至少掌握基本的操作），然后再继续本课程后面的内容，因为后面的内容会假设你已经学会了 vim 编辑器的使用。

如果你想更加快速地入门，可以直接使用 Linux 内部的 vim 学习教程，输入如下命令即可开始：

```bash
vimtutor
```

[![image-20210220162626963](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220162626963.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220162626963.png)

# 环境变量与文件查找

## 环境变量

### 变量

要解释环境变量，得先明白变量是什么，准确的说应该是 Shell 变量，所谓变量就是计算机中用于记录一个值（不一定是数值，也可以是字符或字符串）的符号，而这些符号将用于不同的运算处理中。通常变量与值是一对一的关系，可以通过表达式读取它的值并赋值给其它变量，也可以直接指定数值赋值给任意变量。为了便于运算和处理，大部分的编程语言会区分变量的类型，用于分别记录数值、字符或者字符串等等数据类型。Shell 中的变量也基本如此，有不同类型（但不用专门指定类型名），可以参与运算，有作用域限定。

> 变量的作用域即变量的有效范围（比如一个函数中、一个源文件中或者全局范围），在该范围内只能有一个同名变量。一旦离开则该变量无效，如同不存在这个变量一般。

在 Shell 中如何创建一个变量，如何给变量赋值和如何读取变量的值呢？这部分内容会在 [高级 bash 脚本编程指南](https://www.lanqiao.cn/courses/944) 这门课中详细介绍，这里我简单举例说明一下：

使用 `declare` 命令创建一个变量名为 tmp 的变量：

```bash
declare tmp
```

> 其实也可以不用 declare 预声明一个变量，直接即用即创建，这里只是告诉你 declare 的作用，这在创建其它指定类型的变量（如数组）时会用到。

使用 `=` 号赋值运算符，将变量 tmp 赋值为 shiyanlou。注意，与其他语言不同的是， Shell 中的赋值操作，`=` 两边不可以输入空格，否则会报错。

```bash
# 正确的赋值
tmp=test

# 错误的赋值
tmp = test
```

读取变量的值，使用 `echo` 命令和 `$` 符号（**$ 符号用于表示引用一个变量的值，初学者经常忘记输入**）：

```bash
echo $tmp
```

[![image-20210220163933546](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220163933546.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220163933546.png)

**注意：并不是任何形式的变量名都是可用的，变量名只能是英文字母、数字或者下划线，且不能以数字作为开头。**

### 环境变量

简单理解了变量的概念，就很容易理解环境变量了。环境变量的作用域比自定义变量的要大，如 Shell 的环境变量作用于自身和它的子进程。在所有的 UNIX 和类 UNIX 系统中，每个进程都有其各自的环境变量设置，且默认情况下，当一个进程被创建时，除了创建过程中明确指定的话，它将继承其父进程的绝大部分环境设置。Shell 程序也作为一个进程运行在操作系统之上，而我们在 Shell 中运行的大部分命令都将以 Shell 的子进程的方式运行。

[![1](https://gitee.com/chenyustudy/pic-go/raw/master/5-3.png)](https://gitee.com/chenyustudy/pic-go/raw/master/5-3.png)

通常我们会涉及到的变量类型有三种：

- 当前 Shell 进程私有用户自定义变量，如上面我们创建的 tmp 变量，只在当前 Shell 中有效。
- Shell 本身内建的变量。
- 从自定义变量导出的环境变量。

也有三个与上述三种环境变量相关的命令：`set`，`env`，`export`。这三个命令很相似，都是用于打印环境变量信息，区别在于涉及的变量范围不同。详见下表：

| 命 令    | 说 明                                                        |
| -------- | ------------------------------------------------------------ |
| `set`    | 显示当前 Shell 所有变量，包括其内建环境变量（与 Shell 外观等相关），用户自定义变量及导出的环境变量。 |
| `env`    | 显示与当前用户相关的环境变量，还可以让命令在指定环境中运行。 |
| `export` | 显示从 Shell 中导出成环境变量的变量，也能通过它将自定义变量导出为环境变量。 |

[![1](https://gitee.com/chenyustudy/pic-go/raw/master/5-3.png)](https://gitee.com/chenyustudy/pic-go/raw/master/5-3.png)

你可以更直观的使用 `vimdiff` 工具比较一下它们之间的差别：

```bash
temp=test
export temp_env=test
env|sort>env.txt
export|sort>export.txt
set|sort>set.txt
```

上述操作将命令输出通过管道 `|` 使用 `sort` 命令排序，再重定向到对象文本文件中。管道的概念后面我们会学到，现在你知道这是什么意思就行了。

```bash
vimdiff env.txt export.txt set.txt
```

使用 `vimdiff` 工具比较导出的几个文件的内容，退出 `vimdiff` 需要按下 Esc 后输入 `:q` 即可退出。

[![image-20210220173803346](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220173803346.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220173803346.png)

[![image-20210220173827239](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220173827239.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220173827239.png)

关于哪些变量是环境变量，可以简单地理解成在当前进程的子进程有效则为环境变量，否则不是（有些人也将所有变量统称为环境变量，只是以全局环境变量和局部环境变量进行区分，我们只要理解它们的实质区别即可）。我们这里用 `export` 命令来体会一下，先在 Shell 中设置一个变量 `temp=test`，然后再新创建一个子 Shell 查看 `temp` 变量的值

**注意：为了与普通变量区分，通常我们习惯将环境变量名设为大写。**

**永久生效**

但是问题来了，当你关机后，或者关闭当前的 shell 之后，环境变量就没了啊。怎么才能让环境变量永久生效呢？

按变量的生存周期来划分，Linux 变量可分为两类：

1. 永久的：需要修改配置文件，变量永久生效；
2. 临时的：使用 export 命令行声明即可，变量在关闭 shell 时失效。

这里介绍两个重要文件 `/etc/bashrc`（有的 Linux 没有这个文件） 和 `/etc/profile` ，它们分别存放的是 shell 变量和环境变量。还有要注意区别的是每个用户目录下的一个隐藏文件：

```bash
# .profile 可以用 ls -a 查看
cd /home/shiyanlou
ls -a
```

[![image-20210220174301273](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220174301273.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220174301273.png)

这个 .profile 只对当前用户永久生效。因为它保存在当前用户的 Home 目录下，当切换用户时，工作目录可能一并被切换到对应的目录中，这个文件就无法生效。而写在 `/etc/profile` 里面的是对所有用户永久生效，所以如果想要添加一个永久生效的环境变量，只需要打开 `/etc/profile`，在最后加上你想添加的环境变量就好啦。

### 命令的查找路径与顺序

查看 `PATH` 环境变量的内容：

```bash
echo $PATH
```

默认情况下你会看到如下输出：

```bash
/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games
```

创建一个 Shell 脚本文件，你可以使用 gedit，vim，sublime 等工具编辑。如果你是直接复制的话，建议使用 gedit 或者 sublime，否则可能导致代码缩进混乱。

```bash
cd /home/shiyanlou
touch hello_shell.sh
gedit hello_shell.sh
```

在脚本中添加如下内容，保存并退出。

**注意不要省掉第一行，这不是注释，有用户反映有语法错误，就是因为没有了第一行。**

```bash
#!/bin/bash

for ((i=0; i<10; i++));do
    echo "hello shell"
done

exit 0
```

为文件添加可执行权限，否则执行会报错没有权限：

```bash
chmod 755 hello_shell.sh
```

执行脚本：

```bash
cd /home/shiyanlou
./hello_shell.sh
```

创建一个 C 语言 `hello world` 程序：

```bash
cd /home/shiyanlou
gedit hello_world.c
```

输入如下内容，同样不能省略第一行。

```c
#include <stdio.h>

int main(void)
{
    printf("hello world!\n");
    return 0;
}
```

保存后使用 gcc 生成可执行文件：

```bash
gcc -o hello_world hello_world.c
```

**gcc 生成二进制文件默认具有可执行权限，不需要修改。**

在 `/home/test` 家目录创建一个 `mybin` 目录，并将上述 `hello_shell.sh` 和 `hello_world` 文件移动到其中：

```bash
cd /home/shiyanlou
mkdir mybin
mv hello_shell.sh hello_world mybin/
```

现在你可以在 `mybin` 目录中分别运行你刚刚创建的两个程序：

```bash
cd mybin
./hello_shell.sh
./hello_world
```

[![image-20210220175339796](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220175339796.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220175339796.png)

[![image-20210220175434996](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220175434996.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220175434996.png)

回到上一级目录，也就是 `test` 家目录，当再想运行那两个程序时，会发现提示命令找不到，除非加上命令的完整路径，但那样很不方便，如何做到像使用系统命令一样执行自己创建的脚本文件或者程序呢？那就要将命令所在路径添加到 `PATH` 环境变量了。

### 添加自定义路径到“PATH”环境变量

在前面我们应该注意到 `PATH` 里面的路径是以 `:` 作为分割符的，所以我们可以这样添加自定义路径：

```bash
PATH=$PATH:/home/test/mybin
```

**注意这里一定要使用绝对路径。**

现在你就可以在任意目录执行那两个命令了（注意需要去掉前面的 `./`）。你可能会意识到这样还并没有很好的解决问题，因为我给 PATH 环境变量追加了一个路径，它也只是在当前 Shell 有效，我一旦退出终端，再打开就会发现又失效了。有没有方法让添加的环境变量全局有效？或者每次启动 Shell 时自动执行上面添加自定义路径到 PATH 的命令？下面我们就来说说后一种方式——让它自动执行。

在每个用户的 home 目录中有一个 Shell 每次启动时会默认执行一个配置脚本，以初始化环境，包括添加一些用户自定义环境变量等等。实验楼的环境使用的 Shell 是 zsh，它的配置文件是 `.zshrc`，相应的如果使用的 Shell 是 Bash，则配置文件为 `.bashrc`。它们在 `etc` 下还都有一个或多个全局的配置文件，不过我们一般只修改用户目录下的配置文件。Shell 的种类有很多，可以使用 `cat /etc/shells` 命令查看当前系统已安装的 Shell。

[![image-20210220190454237](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220190454237.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220190454237.png)

### 修改和删除已有变量

#### 变量修改

变量的修改有以下几种方式：

| 变量设置方式                   | 说明                                         |
| ------------------------------ | -------------------------------------------- |
| `${变量名#匹配字串}`           | 从头向后开始匹配，删除符合匹配字串的最短数据 |
| `${变量名##匹配字串}`          | 从头向后开始匹配，删除符合匹配字串的最长数据 |
| `${变量名%匹配字串}`           | 从尾向前开始匹配，删除符合匹配字串的最短数据 |
| `${变量名%%匹配字串}`          | 从尾向前开始匹配，删除符合匹配字串的最长数据 |
| `${变量名/旧的字串/新的字串}`  | 将符合旧字串的第一个字串替换为新的字串       |
| `${变量名//旧的字串/新的字串}` | 将符合旧字串的全部字串替换为新的字串         |

比如我们可以修改前面添加到 PATH 的环境变量，将添加的 mybin 目录从环境变量里删除。为了避免操作失误导致命令找不到，我们先将 PATH 赋值给一个新的自定义变量 mypath：

```bash
mypath=$PATH
echo $mypath
mypath=${mypath%/home/shiyanlou/mybin}
# 或使用通配符 * 表示任意多个任意字符
mypath=${mypath%*/mybin}
```

可以看到路径已经不存在了。

#### 变量删除

可以使用 `unset` 命令删除一个环境变量：

```bash
unset mypath
```

[![image-20210220191131912](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191131912.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191131912.png)

### 让环境变量立即生效

前面我们在 Shell 中修改了一个配置脚本文件之后（比如 zsh 的配置文件 home 目录下的 `.zshrc`），每次都要退出终端重新打开甚至重启主机之后其才能生效，很是麻烦，我们可以使用 `source` 命令来让其立即生效，如：

```bash
cd /home/shiyanlou
source .zshrc
```

`source` 命令还有一个别名就是 `.`，上面的命令如果替换成 `.` 的方式就该是：

```bash
. ./.zshrc
```

[![image-20210220191409381](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191409381.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191409381.png)

## 搜索文件

> 与搜索相关的命令常用的有 `whereis`，`which`，`find` 和 `locate`。

- `whereis` 简单快速

```bash
whereis who
whereis find
```

[![image-20210220191514096](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191514096.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191514096.png)

你会看到 `whereis find` 找到了三个路径，两个可执行文件路径和一个 man 在线帮助文件所在路径，这个搜索很快，因为它并没有从硬盘中依次查找，而是直接从数据库中查询。

`whereis` 只能搜索二进制文件（`-b`），man 帮助文件（`-m`）和源代码文件（`-s`）。如果想要获得更全面的搜索结果可以使用 `locate` 命令。

- `locate` 快而全

使用 `locate` 命令查找文件也不会遍历硬盘，它通过查询 `/var/lib/mlocate/mlocate.db` 数据库来检索信息。不过这个数据库也不是实时更新的，系统会使用定时任务每天自动执行 `updatedb` 命令来更新数据库。所以有时候你刚添加的文件，它可能会找不到，需要手动执行一次 `updatedb` 命令（在我们的环境中必须先执行一次该命令）。注意这个命令也不是内置的命令，在部分环境中需要手动安装，然后执行更新。

```bash
sudo apt-get update
sudo apt-get install locate
sudo updatedb
```

它可以用来查找指定目录下的不同文件类型，如查找 `/etc` 下所有以 sh 开头的文件：

```bash
locate /etc/sh
```

> 注意，它不只是在/etc目录下查找，还会自动递归子目录进行查找

[![image-20210220191813718](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191813718.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220191813718.png)

查找 `/usr/share/` 下所有 jpg 文件：

```bash
locate /usr/share/*.jpg
```

> 环境里使用 zsh，在 `~/.zshrc` 文件里添加了 `setopt nonomatch` 配置，这样就不会>自动处理和修复命令，因此可以不使用 `\` 转义。如果其他环境中执行该命令提示 `zsh: no matches found: /usr/share/*.jpg`，则可以在 `.zshrc` 中添加上述配置，或者使用 `\` 转义。

如果想只统计数目可以加上 `-c` 参数，`-i` 参数可以忽略大小写进行查找，`whereis` 的 `-b`、`-m`、`-s` 同样可以使用。

- `which` 小而精

`which` 本身是 Shell 内建的一个命令，我们通常使用 `which` 来确定是否安装了某个指定的程序，因为它只从 `PATH` 环境变量指定的路径中去搜索命令并且返回第一个搜索到的结果。也就是说，我们可以看到某个系统命令是否存在以及执行的到底是哪一个地方的命令。

```bash
which man
which nginx
which ping
```

[![image-20210220192254586](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192254586.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192254586.png)

- `find` 精而细

`find` 应该是这几个命令中最强大的了，它不但可以通过文件类型、文件名进行查找而且可以根据文件的属性（如文件的时间戳，文件的权限等）进行搜索。

这条命令表示去 `/etc/` 目录下面 ，搜索名字叫做 interfaces 的文件或者目录。这是 `find` 命令最常见的格式，千万记住 `find` 的第一个参数是要搜索的地方。命令前面加上 `sudo` 是因为 test 只是普通用户，对 `/etc` 目录下的很多文件都没有访问的权限，如果是 root 用户则不用使用。

```bash
sudo find /etc/ -name interfaces
```

[![image-20210220192411566](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192411566.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192411566.png)

> **注意 find 命令的路径是作为第一个参数的， 基本命令格式为 find [path][option] [action] 。**

与时间相关的命令参数：

| 参数     | 说明                   |
| -------- | ---------------------- |
| `-atime` | 最后访问时间           |
| `-ctime` | 最后修改文件内容的时间 |
| `-mtime` | 最后修改文件属性的时间 |

下面以 `-mtime` 参数举例：

- `-mtime n`：n 为数字，表示为在 n 天之前的“一天之内”修改过的文件
- `-mtime +n`：列出在 n 天之前（不包含 n 天本身）被修改过的文件
- `-mtime -n`：列出在 n 天之内（包含 n 天本身）被修改过的文件
- `-newer file`：file 为一个已存在的文件，列出比 file 还要新的文件名

[![1](https://gitee.com/chenyustudy/pic-go/raw/master/5-8.png)](https://gitee.com/chenyustudy/pic-go/raw/master/5-8.png)

列出 home 目录中，当天（24 小时之内）有改动的文件：

```bash
find ~ -mtime 0
```

[![image-20210220192533815](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192533815.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192533815.png)

列出用户家目录下比 /etc 目录新的文件：

```bash
find ~ -newer /etc
```

[![image-20210220192603025](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192603025.png)](https://gitee.com/chenyustudy/pic-go/raw/master/image-20210220192603025.png)

## 玩个好玩的

> 模仿黑客帝国代码雨效果
>
> sudo apt-get install cmatrix
>
> 修改字体为黑底绿字
>
> 执行cmatrix
>
> 还可以改变代码的颜色：
>
> ```bash
> cmatrix -C red
> ```

# 文件打包与解压缩

​		在 Windows 上最常见的不外乎这两种 `*.zip`，`*.7z` 后缀的压缩文件。而在 Linux 上面常见的格式除了以上两种外，还有 `.rar`，`*.gz`，`*.xz`，`*.bz2`，`*.tar`，`*.tar.gz`，`*.tar.xz`，`*.tar.bz2`，简单介绍如下：

| 文件后缀名 | 说明                           |
| ---------- | ------------------------------ |
| `*.zip`    | zip 程序打包压缩的文件         |
| `*.rar`    | rar 程序压缩的文件             |
| `*.7z`     | 7zip 程序压缩的文件            |
| `*.tar`    | tar 程序打包，未压缩的文件     |
| `*.gz`     | gzip 程序（GNU zip）压缩的文件 |
| `*.xz`     | xz 程序压缩的文件              |
| `*.bz2`    | bzip2 程序压缩的文件           |
| `*.tar.gz` | tar 打包，gzip 程序压缩的文件  |
| `*.tar.xz` | tar 打包，xz 程序压缩的文件    |
| `*tar.bz2` | tar 打包，bzip2 程序压缩的文件 |
| `*.tar.7z` | tar 打包，7z 程序压缩的文件    |

## zip压缩打包程序

- 使用zip打包文件夹，注意输入完整的参数和路径：

```bash
cd /home/test
zip -r -q -o test.zip
/home/test/Desktop
du -h test.zip
file test.zip
```

上面命令将目录 `/home/test/Desktop` 打包成一个文件，并查看了打包后文件的大小和类型。第一行命令中，`-r` 参数表示递归打包包含子目录的全部内容，`-q` 参数表示为安静模式，即不向屏幕输出信息，`-o`，表示输出文件，需在其后紧跟打包输出文件名。后面使用 `du` 命令查看打包后文件的大小（后面会具体说明该命令）。

- 设置压缩级别为 9 和 1（9 最大，1 最小），重新打包：

```bash
zip -r -9 -q -o test_9.zip /home/test/Desktop -x ~/*.zip
zip -r -1 -q -o test_1.zip /home/test/Desktop -x ~/*.zip
```

这里添加了一个参数用于设置压缩级别 `-[1-9]`，1 表示最快压缩但体积大，9 表示体积最小但耗时最久。最后那个 `-x` 是为了排除我们上一次创建的 zip 文件，否则又会被打包进这一次的压缩文件中，**注意：这里只能使用绝对路径，否则不起作用**。

我们再用 `du` 命令分别查看默认压缩级别、最低、最高压缩级别及未压缩的文件的大小：

```bash
du -h -d 0 *.zip ~ | sort
```

通过 man 手册可知：

- `-h`， --human-readable（顾名思义，你可以试试不加的情况）
- `-d`， --max-depth（所查看文件的深度）

## 使用unzip命令解压缩zip文件

将 test.zip` 解压到当前目录：

```bash
unzip test.zip
```

使用安静模式，将文件解压到指定目录：

```bash
unzip -q test.zip -d ziptest
```

上述指定目录不存在，将会自动创建。如果你不想解压只想查看压缩包的内容你可以使用 `-l` 参数：

```bash
unzip -l test.zip
```

**注意：** 使用 unzip 解压文件时我们同样应该注意兼容问题，不过这里我们关心的不再是上面的问题，而是中文编码的问题，通常 Windows 系统上面创建的压缩文件，如果有有包含中文的文档或以中文作为文件名的文件时默认会采用 GBK 或其它编码，而 Linux 上面默认使用的是 UTF-8 编码，如果不加任何处理，直接解压的话可能会出现中文乱码的问题（有时候它会自动帮你处理），为了解决这个问题，我们可以在解压时指定编码类型。

使用 `-O`（英文字母，大写 o）参数指定编码类型：

```bash
unzip -O GBK 中文压缩文件.zip
```

## tar打包工具

在 Linux 上面更常用的是 `tar` 工具，tar 原本只是一个打包工具，只是同时还是实现了对 7z、gzip、xz、bzip2 等工具的支持，这些压缩工具本身只能实现对文件或目录（单独压缩目录中的文件）的压缩，没有实现对文件的打包压缩，所以我们也无需再单独去学习其他几个工具，tar 的解压和压缩都是同一个命令，只需参数不同，使用比较方便。

下面先掌握 `tar` 命令一些基本的使用方式，即不进行压缩只是进行打包（创建归档文件）和解包的操作。

- 创建一个 tar 包：

```bash
cd /home/test
tar -P -cf test.tar /home/test/Desktop
```

上面命令中，`-P` 保留绝对路径符，`-c` 表示创建一个 tar 包文件，`-f` 用于指定创建的文件名，注意文件名必须紧跟在 `-f` 参数之后，比如不能写成 `tar -fc test.tar`，可以写成 `tar -f test.tar -c ~`。你还可以加上 `-v` 参数以可视的的方式输出打包的文件。

- 解包一个文件（`-x` 参数）到指定路径的**已存在**目录（`-C` 参数）：

```bash
mkdir tardir
tar -xf test.tar -C tardir
```

- 只查看不解包文件 `-t` 参数：

```bash
tar -tf shiyanlou.tar
```

- 保留文件属性和跟随链接（符号链接或软链接），有时候我们使用 tar 备份文件当你在其他主机还原时希望保留文件的属性（`-p` 参数）和备份链接指向的源文件而不是链接本身（`-h` 参数）：

```bash
tar -cphf etc.tar /etc
```

对于创建不同的压缩格式的文件，对于 tar 来说是相当简单的，需要的只是换一个参数，这里我们就以使用 `gzip` 工具创建 `*.tar.gz` 文件为例来说明。

- 我们只需要在创建 tar 文件的基础上添加 `-z` 参数，使用 `gzip` 来压缩文件：

```bash
tar -czf test.tar.gz /home/test/Desktop
```

- 解压 `*.tar.gz` 文件：

```bash
tar -xzf test.tar.gz
```

![此处输入图片的描述](https://doc.shiyanlou.com/document-uid735639labid61timestamp1532339561961.png)

现在我们要使用其它的压缩工具创建或解压相应文件只需要更改一个参数即可：

| 压缩文件格式 | 参数 |
| ------------ | ---- |
| `*.tar.gz`   | `-z` |
| `*.tar.xz`   | `-J` |
| `*tar.bz2`   | `-j` |

> tar 命令的参数很多，不过常用的就是上述这些，需要了解更多你可以查看 man 手册获取帮助。

## 总结

说了这么多，其实平常使用的参数并没有那么复杂，只需要记住常用的组合就可以了。 常用命令：

- zip：
- 打包 ：zip something.zip something （目录请加 -r 参数）
- 解包：unzip something.zip
- 指定路径：-d 参数
- tar：
- 打包：tar -cf something.tar something
- 解包：tar -xf something.tar
- 指定路径：-C 参数