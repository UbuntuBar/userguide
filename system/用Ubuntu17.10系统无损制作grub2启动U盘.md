# 用 Ubuntu 17.10 系统无损制作 grub2 启动U盘
先介绍一下 GRUB2 启动U盘的作用：

它可以用来修复系统或引导各种发行版（如Ubuntu）的 iso 文件，对于维护者来说，是一个必不可少的好工具。

下面介绍一下具体方法。

# 一、制作 syslinux 启动U盘
## 第一步：安装syslinux
<code>sudo apt-get install syslinux</code>

## 第二步：制作启动U盘

先用fdisk给U盘分区，简单起见，只分1个分区，格式化为fat32格式。假定U盘设备文件是：/dev/sdb。


输入：<code>sudo fdisk /dev/sdb</code>

m -- 帮助

n -- 新建分区


分区好后：
a -- 激活分区

w -- 写入分区表

拔掉，重新插入。

格式化：<code>sudo mkfs.vfat -F 32 /dev/sdb1</code>

使用syslinux制作启动盘：（如果自动挂载了，请先卸载U盘）

<code>syslinux -i /dev/sdb1
dd sudo dd conv=notrunc bs=440 count=1 if=/usr/lib/SYSLINUX/mbr.bin of=/dev/sdb</code>

上面的 mbr.bin 包含在 syslinux 软件中。此时这个U盘只需要一个 syslinux.cfg 配置文件就可以启动系统了。

# 二、在 Ubuntu 17.10 系统下定制 g2ldr
注意：下面的命令必须在 grub-pc 环境下运行，grub-efi 是不行的。因此如果你用的是 efi 启动系统，请先安装 grub-pc。

输入 <code>sudo apt-get install grub-pc</code>

完成工作后可以切换回efi系统：

<code>sudo apt-get install grub-efi</code>

## 生成 g2ldr：

新建 bootcfg.cfg 文件，编辑内容:

search.file /boot/grub/grub.cfg root

set prefix=($root)/boot/grub/


生成 core.img:
<code>sudo grub-mkimage -d /usr/lib/grub/i386-pc -p /boot/grub/ -c bootcfg.cfg -o core.img -O i386-pc biosdisk part_msdos fat exfat ntfs ext2 iso9660 udf configfile search help font linux chain</code>

生成 g2ldr:

<code>cat /usr/lib/grub/i386-pc/lnxboot.img core.img >g2ldr</code>

# 三、使用 syslinux 引导 g2ldr

1、 把 g2ldr 复制到U盘下的 boot/grub/ 目录中

2、 把 /boot/grub/ 中的文件、文件夹都复制到U盘下的 boot/grub/ 目录中

3、 在U盘中创建 syslinux.cfg ，编辑内容

DEFAULT grub

TIMEOUT 100

PROMPT 1

LABEL grub

KERNEL boot/grub/g2ldr

保存，即可完成。
