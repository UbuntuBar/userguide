# 更改 Ubuntu 内核参数

很多用户在使用 Ubuntu 时会需要用到特殊功能或因为硬件问题无法进入系统而需要修改内核参数。那么如何修改内核参数，这里做一个介绍。

## 一、在当前系统下修改内核参数。
### 1.临时修改
有的时候你只是想临时改一下，那么可以通过一下步骤进行。
打开终端，输入 sudo -s 获取 root 权限。
![1](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/1.png)

输入 nano /boot/grub/grub.cfg，找到 menuentry ‘Ubuntu’ 这一行。
![2](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/2.png)

再定位到 linux /boot/vmlinuz ... 这一行，文件名后面就是内核参数，请根据需要进行修改。然后保存退出。
![3](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/3.png)

### 2.永久修改
有的时候需要进行永久修改，那么前面的方法是不行的，因为一旦更新GRUB，你之前的修改将会付诸东流，那么可以通过修改 GRUB 默认配置来达到永久修改内核参数之目的，这样，更新 GRUB 也不怕。
1.终端获取 root 权限
2.输入 nano /etc/default/grub
![4](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/4.png)

3.找到 GRUB_CMDLINE_LINUX_DEFAULT 那一行，修改内核参数。（下面那个其实也算，不过修改 DEFAULT 那一行就行了）
![5](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/5.png)

4.保存退出，输入 update-grub 更新 GRUB 配置，你的 /boot/grub/grub.cfg 会被自动更改。

## 二、在 LiveCD 下修改内核参数。
有的时候内核参数会导致系统启动异常，那么就无法在当前系统下更改了。那么我们就可以在 LiveCD 下修改内核参数。

### 1.临时修改
在文件管理器中选中你的系统分区，如果划分了单独的 /boot 就选择 boot 分区
![6](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/6.png)

右键打开终端，
![7](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/7.png)

输入 sudo -s 获取 root 权限

如果单独划分了 boot ，那么请输入 nano grub/grub.cfg （看好了！）进行编辑。
如果没有，输入 nano boot/grub/grub.cfg （不是 /boot/grub/grub.cfg！）
![8](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/更改Ubuntu内核参数/8.png)

具体更改方法看前面。

### 2.永久修改
文件管理器中选择系统分区，单独划分 /boot 的也选择系统分区。
按右键打开终端，sudo -s 获得权限。
输入 nano etc/default/grub （不是 /etc/default/grub），修改之。

修改完成之后不要输入 update-grub 。
然后再按照临时修改的方式修改一次参数。

有人会说你这样不是麻烦嘛，chroot 然后 update-grub 就是。
其实不然，chroot 之后 update-grub 对于双系统用户来说会出现 GRUB 无法识别双系统的情况，还不如这样，然后进入本机系统之后再 update-grub。


修改完成后，重启进入本机系统。
打开终端，输入 sudo update-grub 即可。
