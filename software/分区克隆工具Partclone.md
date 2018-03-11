Partclone 是由 Clonezilla 的开发者们开发的用于创建和克隆分区镜像的自由开源软件。实际上，Partclone 是 Clonezilla 所基于的工具之一。

它为用户提供了备份与恢复已用分区的工具，并与多个文件系统高度兼容，这要归功于它能够使用像 e2fslibs 这样的现有库来读取和写入分区，例如 ext2。

它最大的优点是支持各种格式，包括 ext2、ext3、ext4、hfs+、reiserfs、reiser4、btrfs、vmfs3、vmfs5、xfs、jfs、ufs、ntfs、fat（12/16/32）、exfat、f2fs 和 nilfs。

它还有许多的程序，包括 partclone.ext2（ext3＆ext4）、partclone.ntfs、partclone.exfat、partclone.hfsp 和 partclone.vmfs（v3和v5） 等等。

## Partclone 中的功能
#### 免费：
Partclone 免费供所有人下载和使用。   

#### 开源：
Partclone 是在 GNU GPL 许可下发布的，并在 GitHub 上公开。   * 跨平台：适用于 Linux、Windows、MAC、ESX 文件系统备份/恢复和 FreeBSD。   * 一个在线的文档页面，你可以从中查看帮助文档并跟踪其 GitHub 问题。   * 为初学者和专业人士提供的在线用户手册。   * 支持救援。   * 克隆分区成镜像文件。   * 将镜像文件恢复到分区。   * 快速复制分区。   * 支持 raw 克隆。   * 显示传输速率和持续时间。   * 支持管道。   * 支持 crc32 校验。   * 支持 ESX vmware server 的 vmfs 和 FreeBSD 的文件系统 ufs。
Partclone 中还捆绑了更多功能，你可以在这里查看其余的功能。

#### 下载地址：https://partclone.org/download/

## 如何安装和使用 Partclone

#### 在 Linux 上安装 Partclone。

##### Debian/Ubuntu：
sudo apt install partclone

##### RHEL/CentOS/Fedora：
sudo yum install partclone


#### 使用方法
##### 克隆分区为镜像。
sudo partclone.ext4 -d -c -s /dev/sda1 -o sda1.img

##### 将镜像恢复到分区。
sudo partclone.ext4 -d -r -s sda1.img -o /dev/sda1

##### 分区到分区克隆。
sudo partclone.ext4 -d -b -s /dev/sda1 -o /dev/sdb1

##### 显示镜像信息。
sudo partclone.info -s sda1.img

##### 检查镜像。
sudo partclone.chkimg -s sda1.img

## 来源
来自：https://linux.cn/article-9426-1.html
有部分改动。
