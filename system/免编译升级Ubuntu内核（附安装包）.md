很多 Ubuntu 用户都会碰到内核需要升级的情况，比如需要尝鲜，需要升级内核以支持新硬件/新特性 之类。
然而又不想花时间从源码编译配置内核，那怎么办？

好在官方有现成的内核 DEB 包，这样就可以省去很多事。
地址在此：http://kernel.ubuntu.com/~kernel-ppa/mainline/


如果速度太慢的话，我这里将一些常见版本上传到了百度云盘，这样或许能快一些。
云盘地址：https://pan.baidu.com/s/1kWuP9DP

## 使用方法：
首先，找到内核安装包下载页面之后，选择你的架构。
这个请自己判断，当初装了什么架构的 Ubuntu 各位应该知道。


### 下载内核：
在大多数情况下，我建议各位下载 headers headers-generic image-generic 三个软件包，这个适用于大多数计算机。（image 是内核本身，headers* 是头文件，驱动安装和运行一些应用时需要用到头文件，最好装上）
如果有特殊需求需要下载 low-latency 的话，下载 headers headers-lowlatency generic。

### 安装内核：
安装很简单，打开终端：
sudo dpkg -i 软件包名就行。


一般情况下不需要补充依赖，如果需要补充依赖的话
sudo apt-get -f install 就行。

此外友情提醒：升级内核是一件大事，请升级内核之前妥善备份好您的数据。
如果升级内核之后无法开机，请在启动菜单中选择“高级选项（Advanced）”，然后选择旧内核启动。
