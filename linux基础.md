# linux操作系统



## 1.linux kernel 内核



操作系统的主要组件，它负责两者之间通信和管理资源



## 2.GNU(革奴)工具



GNU计划——重现当年软件界合作互助的团结精神



开源



## 3.GUI  Desktop环境



## 4.Application应用



# linux内核



## 1.硬件设备



管理使用



## 2.软件程序（系统）



操作控制



## 3.系统内存管理



## 4.文件管理



删除，修改



# 文件系统



读写的标准，分区不同，标准不同



win常用NTFS，ubuntu支持的文件系统：ext，ext2，ext3，ext4



# GNU



UNIX上有的软件，linux不具备。GNU仿UNIX，为linux编写的必须软件



## 1.GNU核心



UNIX上的命令，模仿（移植）到linux。 coreutils



### ⑴处理文本的工具



### ⑵操作文本的工具



### ⑶管理进程的工具



## 2.shell



为用户提供用户界面，用户通过他使用电脑，并且和电脑交互



命令行界面CLI	&	图形用户界面GUI



linux shell一般指CLI



### 常见第三方shell



zsh，korn，ash，tcsh



# 搞定命令，自由使用



man   查询用法（man ls）



www.wangchujiang.com/linux-command	中文查询



# 一些零碎概念



~	当前用户目录



$	等待用户输入



/	linux根目录



用户名@计算计名：当前所在目录$



单点符	.	当前文件的目录



双点符	..	当前文件的父目录



文件扩展通配符



*表示多个符号，？表示一个符号



例：ls -l fhs-2.3*.pdf	列举fhs-2.3 .pdf所有文件



元字符通配符	[]



例：f[a-h]ck



# linux路径



linux中，/xxx表绝对路径，	../xxx表相对路径



## 1.绝对路径（全）



/home/ubuntu/Documents/2/3/4/5



## 2.相对路径（不全）



Documents/2/3/4/5或../Documents/2/3/4/5



### 注：



/Documents/2/3/4/5为错误路径，该路径表示根目录下Documents



# linux目录：



linux一切皆文件



## /sbin



仅限root用户可执行的文件



系统二进制目录，GNU高级管理员使用的命令工具



## /lib



二进制文件的公共库		依赖的文件



## /usr



二进制文件、可执行文件【用户相关】



用户二进制目录



## /usr/local



用户手动汇编的二进制文件，是不会与系统管理器安装的软件冲突的安全区



## /etc



配置文件的集合【Editable Text Config】



系统配置文件目录



## /home



主目录，显示所有用户目录



不同用户的文件夹，包含各自的配置信息和软件



## /boot



启动系统所需的文件，如linux内核



启动目录  开机启动文件



## /dev



软硬盘、驱动的集合



设备目录	设备结点，设备管理器



## /opt



可选软件（包）的集合



可选目录	安装第三方软件，存放数据



## /var



系统运行时发生变化的文件，如缓存和日志



可变目录（存放可变文件）



## /tmp



临时文件目录，重启后不保存



## /proc



监控系统进程的虚拟目录，由内核在运行进程时创建



伪文件系统



## /lost	/find



存放临时文件



## /mnt



挂载目录（手机，U盘），外部设备与电脑连接



## /tmp



临时目录



## /cdrom



光盘



## /media



可移动设备挂载点（mp3）



## /srv



用户二进制目录



## FHS



文件系统层级标准 www.pathname.com/fhs



# shell基础



## ls



ls	展示当前目录所有文件（不包括隐藏）



ls -a	展示包括隐藏所有文件



ll	展示文件详细情况



ls -m 横向展示，以逗号为间隔



ls -l 竖向展示



## cd



cd	进入用户主目录



cd ~	进入用户主目录



cd /	进入根目录



cd -	返回到上次操作之前的目录



cd ..	返回上一级目录



cd ../..	返回上两级目录



cd !$	跳转到上一条命令的最后一个路径



## touch



创建空文件；把已存在的文件的时间标签更新为系统当前时间



例：touch 2.txt



## cp



将源文件或目录（文件/文件夹）复制到目标文件或目录中，使用过程中，相对路径与绝对路径皆可



使用方法：cp 想复制的文件或目录  复制目标地址（若不存在，将新建；若存在，将覆盖）



cp -i	覆盖之前先询问用户（y/n）



注：强烈建议使用此命令，以避免重要文件被覆盖



cp -R/r	指定目录下所有文件与子目录一并处理



## lnk	链接文件



## 1.符号链接（软链接）



快捷方式，原文件（夹）必须存在，类比指针概念



## 2.硬链接



副本，必须创建在同一介质（硬盘？）中



### 区别



#### 软链接



1.以路径形式存在，类似与windows的快捷方式



2.可以跨文件系统



3.可对不存在的文件名进行链接



4.可对目录进行链接



#### 硬链接



1.以文件副本形式存在，但不占用实际空间



2.不允许给目录创建硬链接



3.只能创建于同一个文件系统





<!--软链接不适用于cp命令，对软链接cp类似于拷贝快捷方式-->



<!--多次软链接会造成混乱-->



## mv



移动文件（夹）或对目录重新命名

移动：mv  文件（夹） 目标路径



重命名：mv 文件（夹） 新名字



## rm（最危险命令之一）



rm	删除



rm -i	删除之前询问



rm -f	强制删除



rm -r/R	指定目录下所有文件与子目录一并处理



sudo rm -rf /* 以管理员身份强制删除根目录下所有文件（公家饭眼）



## mkdir



创建目录（文件夹）



mkdir -p	 若建立的目录的上层目录不存在，则一并建立上层目录



rmdir	删除空文件夹（无用）



## file



探测给定文件类型



## 查看文本文件



### cat



打印到标准输出



cat -A 展示所有。此命令下，空格替换为$，Tab替换为^I



### more



显示内容，一次一屏



空格向下一页，B向上一页，Q退出，enter向下一行



### less



浏览内容



PgUp向上翻页，PgDn向下翻页，q退出，home开头，end结尾



/xxx 搜索xxx



## tail&head



显示文件开头/结尾若干行，默认为10行

## linux中的任务管理器

System monitor

ps  top

### ps

报告系统当前进程

ps axo pid,comm,pcpu  查看进程的pid，名称及cpu占用率

pid	程序的id

ppid	上级父程序的id

ps -aux | grep named	查看named进程详细信息

### top

实时查看系统整体运行情况

### kill

kill pid	杀死进程

kill -9	强制终止

## 挂载

硬件->电脑（创建可供操作的临时盘），此过程称为挂载

/mnt	自动挂载点，无写入权限

fdisk	查看磁盘使用情况和磁盘分区

### mount

挂载linux系统外文件；选择分区挂载点

mount	A	B

A（真实路径）映射到B（想要挂载的路径）

### umount

卸载挂载

进程处于使用中时无法卸载，当无法卸载时可使用手动卸载

### 为什么要使用挂载

利用文件夹权限，限制（避免）病毒

### 安卓挂载（了解）

挂载点/run/user/1000/gvfs（无法更改）

<!--挂载必须是分区挂载到目录，不能目录挂载到目录-->

## df&du

df	显示磁盘的相关信息

du	查看文件和磁盘使用的空间情况

-h	缩写列出，增加可读性

## sort

文件排序，不改变文件内容

-n	依照数值的大小排序

-r	以相反的顺序来排序

-M	将前面3个字母依照月份的缩写进行排序

## grep

查找文件里符合条件的字符串	过滤器

grep 内容 目标文件/目录

## linux解压缩

gzip	.gz

zip	.zip

bzip2	.bz2

### tar

打包文件（打包不等于压缩）

打包	n->1

压缩	大->小

linux中先打包后压缩

#### 压缩

例：`tar	-zcvf	log.tar.gz	log2012.log`

先打包，再以gzip压缩。

z->gzip

c->创建新归档

v->显示过程

f->使用名称

log.tar.gz中，log为自取名称，tar用于标示采用tar命令打包

log2012.log为操作内容，可以为文件或文件夹

#### 解压

tar -zxvf

## server模式下安装vmtools

更改挂载点，拷贝到桌面，解压，进入目录，进行安装操作，安装完成之后卸载挂载点





# 光标移动技巧&常用快捷键



↑↓  ctrl+N/P  最近使用过的命令



Tab	快速写入（补全）



pwd 输出当前目录的绝对路径



ctrl+c 强制退出



ctrl+shift+c/v	复制/粘贴



ctrl+←/→  跳过单词



ctrl+A/E 跳到开头/结尾



ctrl+H 删除  相当于Backspace



ctrl+T  目标字母后移一格



ctrl+U/K  清除光标（前/后）所有字母



ctrl+R  搜索最近使用过的命令



ctrl+L	清屏



Pgup	PgDn 翻页



## 自由组合



例：ls -a -l	=	ls -al

# 父子shell

子shell依赖于父shell

ps -f	ps --forest	查看现有的shell

多条命令中以	;	间隔，表示并列依次执行，小括号则表示生成子shell执行括号内的命令

## sleep

延迟当前行动（s）

例：sleep 300&	延时300s且后台执行

## jobs

显示后台运行程序，两种状态（running/done）中括号内为编号，其后为该进程pid

jobs -l	列出pid

## coproac协程

coproac frank av{ sleep 10; }

创建子shell，子shell中执行命令

<!--花括号内两端都有空格-->

## 外部命令和内建命令

### 外部命令

单独创建进程（上帝视角）

### 内建命令（非外部命令）

bash中执行

### type

查看命令类型

hashed或目录	外部命令

shell builtin	内建命令



## history

查看运行过的命令

!编号	执行编号行命令

!!	重复上一条命令

## alias

查看别名/定义别名

alias[别名]=[指令名称]

# 环境变量

何为环境变量？		会员？全球通？

允许在任何位置访问环境变量中的内容

环境变量分为全局变量和局部变量

## 局部变量

当前shell中有用，无法在其父shell或子shell中执行

## printenv

显示环境变量的值

行业规定：系统变量名大写，下划线隔开；用户定义变量名小写，下划线隔开

定义全局变量	export fuck="QNMB"

输出全局变量	echo $fuck

删除变量	uset  fuck

子shell中删除全局变量，父shell中依旧可用，反之不行

## shell

1，登录shell

2，非登录就打开shell

3，运行脚本非交互shell

## 全局变量常见配置文件

~/.bashrc

~/.bash

~/.profile

~/.bash-login

不同发行版有所不同，此处以Ubuntu20.04为例

# 软件安装

## PMS

包管理系统

## 工具依赖

必须靠另一种软件才能运行	battledield->origin

## 安装

apt

apt-get

apt-cache

aptitude	过时，被移除

## 更新

update	查找更新

upgrade	更新

## 卸载

remove

## 第三方软件安装

查文档

# linux用户与权限

系统账户，uid<500,系统服务使用

/etc/passwd

用户名:密码（加密）：UID：组ID：备注：用户目录：默认shell

/etc/shadow

密码存放，加密

用户名：密码（加密）：上次修改至今天数（默认1970.01.01开始）：修改间隔：X天后修改密码：到期Y天前提醒：过期X天后禁用账户：禁用日期：不详

## 创建用户

useradd	名称

## 删除用户

userdel	名称

## 更改密码

sudo passwd

chpasswd

## 更改用户信息

chfn

# 组group

linux组	共享权限，共享资源的权限

ubuntu发行版自行自动创建与用户同名的组，可自行配置

tail  /etc/group

组名：密码：组ID：组列表

## 修改组

groupadd	创建组

groupmod	修改组

groupdel	删除组

usermod	修改用户信息

# 文件与文件夹权限

-|---|---|---

d(文件夹)/-(文件)/l(link文件)|组创始人权限|组下属权限|其他组下属成员权限

r可读；w可写；x可执行

## chmod

修改控制用户对文件的权限

chmod 777  

# linux编辑器

vim	编辑器之神

emacx	神之编辑器

## vim

sudo apt install vim

普通模式（命令操作模式）：操作文件

插入模式：编辑文件

按i，进入insert模式

按ESC，进入普通模式

:w 写入	:q	退出

:wq	保存并退出

:q!	不保存直接退出

### 光标移动

HJKL

上->K

下->J

左->H

右->L

### 翻页

ctrl B 向上一页

ctrl F 向下一页

ctrl E 向下滚动

ctlr Y 向上滚动

shift g 最后一行

gg 开头