[TOC]

## 基础命令

### ss

ss -tanlp t:tcp下进程，a:所有sockets，n:显示端口号，l:监听方式，p:进程

### ls

ls -alh -d h:以human_readable的方式显示文件大小，d只显示dir

ls -alh -r r:反转查询结果

ls -alh -R R：以递归的方式

ls -alh -1  1:数字1表示每一行只显示一个文件

ls -al |wc -1 参看当前文件夹下文件及目录的数量

-rwxrwxrwx

第一个参数：-等价于f表示regular文件，普通文件

d文件，蓝色或绿色

c字符设备，深黄色

b块设备，浅黄色

l 软连接，蓝绿色

s socket文件，粉色

### stat

touch 文件名 三个时间都改变

stat redis.conf(文件名)

atime: 访问文件的时间

mtime:修改文件的时间

ctime:元数据改变的时间，比如修改了文件名字

### cd

cd - 回到上一次的操作路径

### basename dirname

basename  (esc.)   当前目录的最后一部分

dirname 除了最后一部分之前的路径部分

### alias

alias  ll  查看命令别名

### which whereis whatis

which alias查看命令在哪个目录下

whereis alias查看命令在哪个目录下,  还能显示手册位置

whatis alias查看命令的类型及具体介绍

### type

type ls 查看命令是外部还是内部命令

### echo(回显)

echo:默认后面有一个\n

echo /{a,b}/{c,d}   # /a/c /a/d /b/c /b/d

echo {a,b}\*{c,d}   #  a\*d b\*c\* b\*d

echo{a..z..2}

### cp

cp /etc/redis.conf{,.bak} ./  #复制到根目录

### cat

cat *.txt  将txt文件连到一起

tac *.txt 将txt文件连到一起, 文件顺序不变，文件内容反转连接

### yum

yum -y install tree  默认是yes

### tree

tree / -L1 查看根目录下面的一层

tree -d 只显示目录

### rm

rm -r  a 递归的移除目录

### mkdir

mkdir -pv   如果没有父目录则新键一个父目录，并且显示详情

### tail

tail -f redis.conf  将指针定位到文件的末尾，一般日志文件实用

tail -n100 redis.conf 将指针定位到文件的第100行  

 ### ln

ln -s 目录或文件1  目录或文件2    -s一定要写这样才能看清楚从谁到谁的链接

建立连接时2一定要不存在，软连接建立完成时，使用stat查看状态时，stat -L, 如果原文件改变了，软连接则会跟进，如果不加-L，则原文件变了软连接状态不会跟进。

## 基础知识

### 家目录与根目录

root用户下面的家目录~

home下面的家目录~

root和home都在系统的根目录下/

### 查看帮助的几种方法

help 命令

命令 --help

命令 -h

man 命令

### 路径搜索过程

linux系统：hash-builtin-path   不会找当前路径，只会从path 中查找，找不到就找不到，如果想要查找当前路径需要在前面加一个点。

window系统：先搜素当前路径在搜素path路径，查看目录内容实用dir命令(隐藏与不隐藏都能查到)

### 通配符

ls -d s*  以s开头的目录，后面可以是任意个包括0个字符

ls -d s??  以s开头的目录，后面需要有2个字符

ls -d s?*  以s开头的目录，后面需要有2个以上字符

ls -d s* [0-9]  以s开头的目录，以数字结尾，中间可以有任意个字符

### 





