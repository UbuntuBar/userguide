# 使用 Ubuntu Server 建立一个属于自己的个人网站(A+P+M+W)

我用的是 Ubuntu Server 16.04 进行演示的，其实 Ubuntu Server 都差不多，没有必要过分追究版本。
Ubuntu Server 相对 Debian Stable 来说组件比较新（因为Ubuntu是基于 Debian Testing 的，当然肯定修复了 Debian Testing 里的bug），Debian Testing 是不太适合生产环境的。
当然，也没说 Debian Stable 不好，Debian Stable 还是不错的。

废话不多说。


## 第一步 选择提供商
挑选一个你比较中意的提供商，选一个你比较中意的VPS，系统选择 Ubuntu Server。

## 第二步 登陆VPS。
分平台：
Windows：PuTTY、Xshell、WSL 里面的 SSH 命令。
GNU/Linux、OSX、及其他：使用ssh命令，ssh <vps的IP>

![1](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/1.png)

## 第三步 基本的设置。
### 3.1 更新源。
输入 apt-get update 进行更新
![2](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/2.png)

## 第四步 安装必备的服务器组件。
### 4.1 安装Apache2
我这里用的是Apache2，当然你也可以选择Nginx之类的工具。
![3](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/3.png)

### 4.2 安装数据库
apt-get install mysql-server
新版本的 Ubuntu 改成了 mariadb-server 其实是一样的。

这时，系统会提示输入MySQL密码，自己输入一个比较复杂的密码即可（当然你需要记住）

![4](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/4.png)

### 4.3 安装PHP
16.04默认用的是php7，这里演示用的也是php7，14.04是php5（搭博客基本上看不出有什么区别，当然肯定是有区别的）
apt-get install php7.0 （14.04是apt-get install php5）

### 4.4 安装两个模块
1.是php的apache模块，没有这个无法运行运行index.php
apt-get install libapache2-mod-php

2.安装php-mysql
apt-get install php-mysql

## 第五步 安装wordpress
### 5.1 首先要更改apache设置
nano /etc/apache2/sites-available/000-default.conf
把方框里的/var/www/html改成/var/www，然后按Ctrl+X保存退出
![5](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/5.png)

### 5.2 重新启动Apache
service apache2 restart

然后 wget wordpress 链接（在putty中按右键可以粘贴）。

### 5.3 解压
#### 5.3.1 安装Unzip
某些vps提供商会帮你装好，如果没有 apt-get install unzip


#### 5.3.2 解压
unzip <下载的文件名>
系统会把解压后的文件放到当前目录/wordpress文件夹里。

### 5.3.4 复制
cp -r ./wordpress/* /var/www/

### 5.3.5 修改/var/www的权限
chmod -R 777 /var/www

### 5.3.6 建立数据库。
mysql -u root -p
(mariadb 可能不一样)

然后输入 create database wordpress; （注意分号！）
然后输入exit

#### 5.3.7 访问网站。
在浏览器里输入你的vps ip地址，点击下一步。

输入相应信息。
![6](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/6.png)

#### 5.3.8 进一步设置
![7](https://raw.githubusercontent.com/UbuntuBar/userguide/master/image/使用UbuntuServer建立一个属于自己的个人网站(A+P+M+W)/7.png)

### 5.3.9 OK
现在你的网站就搭建好了，现在就可以用了。
