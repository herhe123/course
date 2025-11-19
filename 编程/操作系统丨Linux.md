操作系统分为哪些模块：参照计算机原理，计算机的组成部分是CPU、内存、总线以及外设构成的。

操作系统的模块与之对应：
1、管理CPU的叫==处理机管理==；2、管理内存的叫==内存管理==；3、管理外设的叫==**设备管理**==，外设管理需要相应的驱动程序；4、外加一个计算机原理里面没有的，人机交互模块，也叫Shell，这里有图形化界面的Shell，和命令行界面的shell。好像漏了总线，总线是通过==总线控制器管理，完全硬件实现==，所以不需要管理模块。

编写程序时使用的高级语言通过编译器准换为计算机理解的二进制代码，还需要加载到内存中，而操作系统帮助可执行程序加载到内存中并分配其资源

**进程processes**：正在执行的程序

**线程threads**：进程执行的基本单位

一个进程可以有一个线程或多个线程

# Linux

## cut

https://zhuanlan.zhihu.com/p/381898924

```
cut [-bn] [file] 或 cut [-c] [file] 或 cut [-df] [file]
```

`cut` 命令从文件的每一行剪切字节、字符或字段并将这些字节、字符或字段写至标准输出。

如果不指定 `file` 参数， `cut` 命令将读取标准输入。 必须指定 `-b`、`-c` 或 `-f` 标志之一。

主要参数含义： 

`-b`: 以**字节**为单位进行分割 
`-c`: 以**字符**为单位进行分割 
`-d`: 自定义分隔符进行分割，默认为制表符号
`-f`: 与 `-d` 一起使用，用分隔符分割后，指定显示哪些部分
`-n`：取消分割多字节字符，仅和 `-b` 标志一起使用。

test.txt文本内容：

*name:liren*
*age:47*
*study:linux*
*hate:social*

### 按冒号分隔

```
cat test.txt | cut -d: -f2
```

输出结果：

*liren*
*47*
*linux*
*social*

## 按首字母排序

```
cat test.txt | sort -bf
```

输出结果：

*age:47*
*hate:social*
*name:liren*
*study:linux*

## 重复行只打印一次

文本内容：

*name:liren*
*age:47*
*study:linux*
*hate:social*
*hate:social*

```
cat test.txt | uniq
```

输出：

*name:liren*
*age:47*
*study:linux*
*hate:social*

## wc

文件的统计信息（行、单词数、字节）

```
wc test.txt
```

## grep

查找某行

```
cat test.txt | grep name
```

或

```
grep name test.txt
```

## apt -get

检索新的包列表

```
sudo apt-get update
```

## ls

`ls-l`以长格式显示文件和目录信息，包括权限、所有者、大小、创建时间等。

第一列的字符表示文件或目录的类型和权限。其中第一个字符表示文件类型

- \- 表示普通文件
- d 表示目录
- l 表示符号链接
- c 表示字符设备文件
- b 表示块设备文件
- s 表示套接字文件
- p 表示管道文件

在使用 **ls -l** 命令时，第一列的其余 9 个字符表示文件或目录的访问权限，分别对应三个字符一组的 **rwx** 权限。例如

- r 表示读取权限
- w 表示写入权限
- x 表示执行权限
- \- 表示没有对应权限

前三个字符表示所有者的权限，中间三个字符表示所属组的权限，后三个字符表示其他用户的权限。例如：

```
-rw-r--r-- 1 user group 4096 Feb 21 12:00 file.txt
```

表示文件名为file.txt的文件，所有者具有读写权限，所属组和其他用户只有读取权限。

drwxr-xr-x.t(拆分`d`目录 ；`rwx`所有者读写执行权限 ； `r-x`其他读取、执行权限)

## chmod

7读取写入执行
6读取写入
5读取执行
4只读
3写入执行
2写入
1执行
0没有权限

```
chmod 640 file.txt
```

## linux访问控制

linux中一切都是对象，每个用户都有它创建的对象，有root的管理员账户



# b站版本

解释器：翻译解释命令行，/bin/bash，称为shell（外壳）；将用户提交指令转变成内核理解的指令

内核：核心部分，管理cpu、内存、磁盘等

## ls

`/`根目录下所有目录

- 一级目录：
  - bin,sbin:存放可执行文件
  - dev：存放硬件设备
  - home：普通用户的主目录
  - root:管理员账号的主目录
  - mnt：挂载外部设备的目录
  - media:自动识别并挂载的设备目录
  - proc：内存数据的映射，不占用实际的硬盘空间
  - tmp：临时文档目录
  - var：变化的数据，如：系统日志、邮箱
  - boot:系统启动文档（内核）
  - etc：各种系统配置文件
  - opt：第三方软件
  - usr：与用户有关的各种数据

`-l`

以长格式显示文件和目录信息，包括权限、所有者、大小、创建时间等。

如：drwxr-xr-x.t(拆分`d`目录 ；`rwx`所有者读写执行权限 ； `r-x`其他读取、执行权限)

`-l -h`（或`-lh`)

字节单位简写

`-d`只看目录本身

`-ld`只看目录属性

`-a`列出隐藏文档

## 快捷键

tab自动补全

ctrl+l或clear：清屏

ctrl+c：放弃当前任务

Esc+.：粘贴上一条命令的参数

## 命令

pwd当前目录

`cd`改变指定目录

- cd（或cd ~):回到home	
- ~表示该用户的主目录
- `cd ..`返回上一个目录（中间空一格）
- `cd ../..`返回多个目录

`su - admin2`：切换另一个用户

`mkdir -p study/ccna/youtube`递归创建多个目录（嵌套）

`rmdir study`删除文件夹

`touch file1 file2 file3`测试创建指定名称的文件（内容为空）

`cat file1`读取短文件内容

`less`读取长文件内容，pgup,pgdn翻页，q退出

`cp work/ccna.md testcopy.txt`复制某目录下文件到当前位置

`cp -r work study`复制文件夹

`rm file.txt`删除文件

`rm -r study`删除文件夹

`mv file.txt 指定的位置`移动文件到指定文件夹

`man`帮助

## vim编辑器

`vi test.txt`进入编辑器命令行模式；按字母i进入插入模式，更改文本；输入q!退出；ESC进入命令模式；wq保存并退出

## 服务控制

systemctl系统控制器，启动、停止服务

```
//运行状态
systemctl start httpd//启动
systemctl stop httpd//停止
systemctl status httpd//服务器状态
systemctl restart httpd
//开机自启
systemctl enable httpd
systemctl disable httpd
```

## 安全开关

防火墙：内核的网络保护

关闭防火墙：

```
systemctl disable firewalld -now
```

SELinux：内核的系统保护，通过内核启动参数、启动配置

```
vi /etc/selinux/config
SELinux=Permassive（宽松）Enforcing(强制保护)Disabled(禁用)（重启后生效）
setenforce 0|1立即宽松/强制模式
getenforce查看结果
```

## 配置网络

```
rht-vmctl reset red
```

virtual machine manager-allow-<img src="C:\Users\Admin\AppData\Roaming\Typora\typora-user-images\image-20240502185753712.png" alt="image-20240502185753712" style="zoom:50%;" />

`nmtui`-设置系统主机名（第三个）（set system hostname)-按照题目要求，==设置主机名==；再进第一个-第一项回车-移到`ipv4`-手动（`manual`)-`show`回车-`address`按照题目要求，==设置ip地址==；`Gateway`，==设置网关==；`dns`,==设置dns服务器==；`空格`，选中==require ipv4 addressing for this connection==,选中==automatically connect== ，ok回车，按tab键到back；再进第二个,`deactivate`，回车两次，back返回，最后exit

真机远程连接到虚拟机`ssh root@red.net0.example.com`
