# Linux学习

## 系统目录

![linux目录结构](imgs/dir.jpg)

1. `/bin`:
   `bin` 是 `Binary`(二进制文件)的缩写，这个目录存放着最经常使用的命令.比如：
   a) `ls` 查看该目录下的所有文件
   b) `su`、`sudo`、`apt` .....等等
   c) 终端命令中的所有输入的操作指令
2. `/boot`:
   `boot`(计算机启动)
   这里是存放启动Linux时使用的一些核心文件,包含一些连接文件以及镜像文件。
3. `/dev`:
   `Device`:设备的缩写,该目录下存放的是Linux的外部设备,在Linux中访问设备的方式和访问文件的方式是相同的。
4. `/etc`:
   `etc`是`Etcetera(等等)`的缩写,这个目录用来存放所有的系统管理所需要的配置文件和子目录。
5. `/home`:
   用户的主目录，在Linux下每个用户都有一个自己的目录,一般该目录名是以用户的账号命名的,如home->alice,bob,eve等。
6. `/lib`:
   `lib`是`Library`(库)的缩写，这个目录存放着系统最基本的动态连接共享库，类似于Windows中的dll文件，几乎所有的应用程序都需要这些共享库。
7. `/lost+found`:这个目录一般是空的，当系统非法关机后，这里就存放了一些文件。
8. `/media`:Linux会自动识别一些设备：U盘、光驱等等，当识别后，linux就会把这些设备挂载到这个目录下。
9. `/mut`:系统提供该目录是为了让用户临时挂载别的文件系统的，我们可以将光驱挂载在 /mnt/ 上，然后进入该目录就可以查看光驱里的内容了。
10. `/opt`:(optional)可选:
    这是给主机额外安装软件所摆放的目录。比如你安装一个ORACLE数据库则就可以放到这个目录下。默认是空的。
11. `/root`:系统管理员
12. `/sbin`:(super user)是 Superuser Binaries (超级用户的二进制文件) 的缩写，这里存放的是系统管理员使用的系统管理程序。
13. `/selinux`:这个目录是 Redhat/CentOS 所特有的目录，Selinux 是一个安全机制，类似于 windows 的防火墙，但是这套机制比较复杂，这个目录就是存放selinux相关的文件的。
14. `/usr`:(unix shared resources)共享资源的缩写
    这是一个非常重要的目录，用户的很多应用程序和文件都放在这个目录下，类似于 windows 下的 program files 目录。
    14.1 `/usr/bin`:系统用户使用的应用程序。
    14.2 `/usr/sbin`:超级用户使用的比较高级的管理程序和系统守护程序。
    14.3 `/usr/src`:内核源代码默认的放置目录。
15. `/var`:var 是 variable(变量) 的缩写，这个目录中存放着在不断扩充着的东西，我们习惯将那些经常被修改的目录放在这个目录下。包括各种日志文件.
16. `/run`:是一个临时文件系统，存储系统启动以来的信息。当系统重启时，这个目录下的文件应该被删掉或清除。如果你的系统上有 /var/run 目录，应该让它指向 run。

## linux文件的基本属性

### 修改文件或用户权限

1. `chown`:change ownerp 修改所属用户与组
2. `chmod`:change mode 修改用户权限

- `ls -l`:显示文件属性以及文件所属的用户和组
  >jxn@jxn:~/Downloads$ ls -l  
总用量 148028  
drwxr-xr-x 3 jxn jxn     4096 7月   9 11:11 firefox-89.0.2  
-rw-r--r-- 1 jxn jxn 75443270 7月   9 10:01 firefox-89.0.2.tar.bz2  
-rw-r--r-- 1 jxn jxn 76127160 7月   8 16:37 opera-stable_77.0.4054.203_amd64.deb  
  - `d`:directory 目录
  - `-`:file 文件
  - `l`:link file 链接文件
  - `b`:装置文件里的可供存储的接口设备(可随机存取装置)
  - `c`:装置文件里的串行端口设备,例如键盘、鼠标等

   接下来的字符串中，以三个为一组`rwx`;`r`:read;`w`:write;`x`:execute执行,注意:这三个权限的位置不会变，如果没有权限，就会出现减号`-`;  
   ![文件权限](imgs/file-llls.jpg)  
   ![文件权限说明](imgs/file-desc.png)
- `whoami`:显示是那个用户

## 常用命令

- `ls` 查看该目录下所有的文件
  - `-a` 显示隐藏的文件 `all`的英文缩写
  - `-l` 列表形式显示 `list`的英文缩写
  - `-la` 以列表形式显示所有文件包含隐藏文件
