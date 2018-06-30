title: 02. Linux基础
speaker: LI YANG
transition: slide3
files: /js/demo.js,/css/demo.css
theme: light
usemathjax: yes


[slide]
# Linux基础

[slide]
# Ubuntu简介
Ubuntu 是一款构建于 Linux 内核之上、完全开放源码的操作系统。Ubuntu 社群的理念：软件应可免费取得，人们能无障碍的使用软件工具，且不会有任何功能上的差异；人们应有定制和修改软件的自由，且方式不受限制。

> Ubuntu (发音"oo-BOON-too"--“乌邦图”) 是一个南非的民族观念，着眼于人们之间的忠诚和联系，含义是 `待人以仁` ，另一种翻译是： `天下共享的信念，连接起每个人` 。


[slide]
# Ubuntu桌面环境
- GNOME: Ubuntu 默认桌面环境
- KDE: 主流桌面


[slide]
# 4.5 Linux 基础
Unix 最初主要使用命令行界面，图形用户界面及其窗口、图标、菜单等都构建在基本的命令行;在命令行里可以管理和访问 Linux 的任何资源。


[slide]
# 软件包管理器
在 Linux 里安装程序有许多方法，但是最简单的方法是使用发行版自带的包管理器（Package Manager PM）。 `PM` 可以确保安装上所需的缺失文件（也称为依赖包），以便程序正确运行，我们可以通过在线源来安装`PM` 。 

 


[slide]
# 目录和文件系统
Linux 和 Unix 文件系统被组织成一个有层次的树形结构。

- 文件系统的最上层是` / `，或称为 根目录
- 在 Unix 和 Linux 的设计理念中，`一切皆为文件 —— 包括硬盘、分区和可插拔介质`。这就意味着所有文件和目录都位于根目录中。 

```bash
# 范例
/home/food/cheese.odt  完整路径
它指向  cheese.odt 文件，而该文件位于 food 目录下
food 目录又位于 home 目录，
home 目录又位于根目录 / 下。 
```


[slide]
# 根目录结构1
在根 ` / `目录下，有一组重要的系统目录列表如下：

- `/bin` - 重要的二进制 (binary) 应用程序
- `/boot` - 启动 (boot) 配置文件
- `/dev` - 设备 (device) 文件
- `/etc` - 配置文件、启动脚本等 (etc)
- `/home` - 本地用户主 (home) 目录
- `/lib` - 系统库 (libraries) 文件
- `/lost+found` - 在根 (/) 目录下提供一个遗失+查找(lost+found) 系统
- `/media` - 挂载可移动介质 (media)，诸如 CD、数码相机等

[slide]
# 根目录结构2
- `/mnt` - 挂载 (mounted) 文件系统
- `/opt` - 提供一个供可选的 (optional) 应用程序安装目录
- `/proc` - 特殊的动态目录，用以维护系统信息和状态，包括当前运行中进程信息
- `/root` - root (root) 用户主文件夹，读作“slash-root”
- `/sbin` - 重要的系统二进制 (system binaries) 文件
- `/sys` - 系统 (system) 文件
- `/tmp` - 临时(temporary)文件
- `/usr` - 包含绝大部分所有用户(users)都能访问的应用程序和文件
- `/var` - 经常变化的(variable)文件，诸如日志或数据库等



[slide]
# 主目录 `home`
每个用户都有自己的主目录，通常位于 `/home/user`。在主目录里，你可以存放文档 `/home/user/documents` 、`程序连接`、音乐 `/home/user/Music` 或其它任何东西。我们可以在主目录里创建文件和文件夹，随意进行组织，就像在我们自己的家里那样。根据我们的权限设置，我们可以允许或拒绝任何其他用户（Root 用户除外）访问这些文件。



[slide]
# 权限
Linux 所有文件都有权限（读`read`、写`write`、运行`execute`），超级用户 `root` 
不受其限制；其简写是`R/W/X`；Linux 是多用户系统，因此每个用户都有自己的密码，这样可以限制别人对其文件的访问。

- 读(read): 允许显示/打开该文件 可以显示目录内容
- 写(write): 可以编辑或删除该文件 可以更改目录内容
- 可执行(execute): 可执行文件可以作为程序运行 可以进入该目录

[slide]
# 权限分类
每个文件都有三组权限加以保护，按重要性依次排列：
- 用户(user): 适用于该文件的所有者
- 组(group): 适用于该文件所属的组
- 其他(other): 适用于所有其他用户

[slide]
# 组权限
每个用户都属于一个或多个组，用户可以设置自己的文件/文件夹权限。这就是组权限，比如 `Joe` 和 `Susan` 同属 `Accounting` 组，那么他们可以允许 `Accounting` 组成员访问各自的文件，同时限制 `Sales` 组成员访问自己的文件。

[slide]
# ROOT权限
`Root` 根用户（不要和文件系统的/即根目录混淆），有权处置所有文件，是唯一能够更改系统全局设置的用户。根用户拥有自己的密码，用来进行系统维护。这一差别可以防止普通用户在系统上安装有害的间谍软件，或删除重要文件。


[slide]
# 超级用户ROOT和SUDO

Linux中 `root` 用户具有最高管理权限，但是 Ubuntu 把 root 用户禁用了，而是将系统管理权限授予特定用户，他们可以使用 `sudo` 执行管理任务。 

默认情况下，系统安装中创建的第一个用户帐号具有使用 `sudo` 的权限。 使用 `sudo` 只需在执行的命令前加上 `sudo` 即可，随后输入密码。 



[slide]
# 神奇的命令行界面(CLI)
在类似开始菜单里，`Terminal` 程序可以启动一个终端，和 DOS 窗口有点相近，但实际上它比 DOS 出现更早，功能也更强大，这就是命令行界面 `Command Line Interface CLI`，也尝尝常常被称为命令行或者 `shell`。

> 要启动一个终端，可以选择 `应用程序 → 附件 → 终端`  
> 快捷方式：`Ctrl + Alt + T`

[slide]
# 超级用户Root
- 启动 `Terminal` 时，默认是权限受限的普通用户。要进入 `Root` 用户模式，只需键入 `su [回车键]`，然后输入 `Root 密码 [回车键]`。 
- `Root` 用户可以破坏任何人的数据，包括Linux运行所需的系统文件。
- 退出 `Terminal` 或 `su` 模式，可输入 `exit [回车键]`或直接按`Ctrl+D`。

> Ubuntu的默认root密码是随机的，即每次开机都有一个新的root密码。 必须通过 `sudo passwd`修改。


[slide]
# 常用管理命令
- 查看目录 ls (List): 用不同颜色、经过排列的文本列出目录下的文件。
- 创建目录 mkdir (MaKeDIRectory): 创建目录。
- 删除目录 rmdir (RemoveDIRectory): 删除目录。
- 切换目录 cd (ChangeDirectory): 从您的当前目录切换到您指定的任意目录。
- 复制文件/目录 cp (CoPy): 拷贝您指定的任意文件。cp -r 命令则可以拷贝您指定的任意目录（注：包括该目录里的文件和子目录）。
- 创建文件： touch: 创建任意文件。
- 删除文件/目录: rm (ReMove): 删除您指定的任意文件。rm -rf 命令则可以删除您指定的任意目录（注：包括该目录里的文件和子目录）。
- 重命名文件/目录: (MoVe): 重命名/移动您指定的任意文件或目录。
- 查找文件/目录： locate （文件或目录名）

[slide]
# 查看目录 ls
使用ls命令可以查看当前目录下面的所有文件信息。
```bash
$ ls -l
total 126920
-rw------- 1 liyang liyang 30822400 Apr 23 11:14 core
drwxr-xr-x 2 liyang liyang     4096 Nov  7  2017 Desktop
drwxr-xr-x 8 liyang liyang     4096 May 24 14:13 Documents
drwxr-xr-x 6 liyang liyang     4096 May 31 09:47 Downloads
drwxr-xr-x 2 liyang liyang     4096 Nov  7  2017 Public
...
```

[slide]
# 创建目录 `mkdir`
使用 `mkdir` 命令可以创建文件夹。
```bash
$ mkdir data
$ ls 
data
```

[slide]
# 删除目录 `rmdir`
使用rmdir命令可以删除文件夹。
```bash
$ rmdir data      # 删除data文件夹 
```

[slide]
# 切换目录 `cd` 
使用 `cd` 命令可以从当前目录切换到指定的任意目录。
```bash
$ cd /  # 进入根目录 
$ cd    # 进入用户的 home 目录 
$ cd -  # 进入上次访问的目录 (相当于 back) 
$ cd .. # 进入上级目录 
```


[slide]
# 复制文件/目录 `cp` 
使用 `cp` 命令可以拷贝您指定的任意文件。cp -r 命令则可以拷贝您指定的任意目录（注：包括该目录里的文件和子目录）。
```bash
$ cp /usr/home/liyang/a.md /usr/home/liyang/data/
$ cp -r       # 复制文件夹 包括子目录和文件 
```

[slide]
# 创建文件 `touch` 
使用  `touch` 命令可以创建任意文件
```bash
$ touch file.md 
```


[slide]
# 删除文件/目录 `rm` 
使用  `rm` 命令可以删除您指定的任意文件
```bash
$ rm file.md 
$ rm -rf data # 除您指定的任意目录
```

[slide]
# 重命名文件/目录 `mv` 
使用 `mv` 命令可以重命名/移动指定的任意文件或目录。
```bash
$ mv /home/data /usr/data  
```

[slide]
# 显示当前目录名称 `pwd` 
使用 `pwd` 命令可以显示当前目录; pwd = print working directory
```bash
$ mv /home/data /usr/data  
```

[slide]
# 其他命令

```bash
$ sudo su    # 切换到 root 用户
$ exit        # 退出 root 
$ man cd # 显示cd命令的 manual
```

[slide]
# 管理用户权限
使用 chmod 可以管理文件夹和文件的权限。

<img src="img/linux04.jpg" width="596">


[slide]
# 管理用户权限
<img src="img/linux03.png" width="844" style="margin-bottom: 20px">

```bash
$ chmod 444 file.md # 为file设置只读权限
$ chmod 777 file.md # 为file设置全部权限
```

[slide]
# 如何管理用户

```bash
$ sudo adduser 用户名  # 增加用户
$ sudo deluser 用户名  # 删除用户

$ passwd # 修改当前用户的密码
$ sudo passwd 用户名 # 修改用户密码
```

[slide]
# 如何安装程序
Linux有多种安装软件的方法，我们主要介绍最基本的命令行模式：

- `APT` (Advanced Package Tool) : 是最强的包管理系统，而图形化程序如 添加/删除 应用程序 和 `Synaptic` 都是建立在它的基础之上的。 `APT` 能够自动处理软件之间的依赖关系，安装所需要的软件包。
- `dpkg` (Debian Packager):  是 `Debian` 专门开发的套件管理系统，方便软件的安装、更新及移除。 本身是一个底层的工具，不能处理依赖关系。


[slide]
# 使用apt-get安装程序

```bash
# 安装软件包
$ sudo apt-get install packagename
# 删除软件包
$ sudo apt-get remove packagename
# 获取新的软件包列表
$ sudo apt-get update
# 升级有可用更新的系统
$ sudo apt-get upgrade

# 安装 .deb 文件
sudo dpkg -i packagename.deb 
# 卸载 .deb 文件
sudo dpkg -r packagename
```


[slide]
# 常用程序的安装
```bash
# 安装git
~$ sudo apt-get install git

# 安装Oh-My-Zsh
~$ sudo apt install curl
~$ sudo apt install zsh
~$ sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

# 安装Powerlevel9k
$ git clone https://github.com/bhilburn/powerlevel9k.git ~/.oh-my-zsh/custom/themes/powerlevel9k
```

[slide]
# 作业

1. 在用户的home目录建立一个data文件夹；
2. 进入data文件夹
3. 在文件夹中新建一个文本文件file.md；
4. 退出data文件夹，回到用户home目录
5. 创建一个新的目录new
6. 将file.md移动到new文件夹
7. 改变file.md的属性为所有用户只读
8. 将file文件拷贝到home目录下，并且改名为file-home.md