# 让 Ubuntu 拥有全局菜单 —— GNOME Global AppMenu

17.10 及之后的版本因默认切换至 GNOME 桌面，所以没有全局菜单，这让很多 Unity 用户很不适应，不过，我们可以通过安装 GNOME Global AppMenu 插件的方式解决。


## 安装方法

1. 首先，请打开终端，输入 <code>sudo -s</code> 获取 root 权限。

2. 第二步，我们需要安装几个软件,不过在安装之前先刷新一下软件源为好。

输入 <code>sudo apt-get update</code>

3. 安装软件：<code>apt-get install git gnome-tweak-tool</code>

Git 是一款免费、开源的分布式版本控制系统，我们这里用来同步 GitHub 上的源码。GNOME Tweak Tool 是 GNOME 自带的优化工具，可以更改主题、启用或禁用插件。

4. 输入 <code>git clone https://github.com/lestcape/Gnome-Global-AppMenu.git</code> 克隆插件源码。

5. 克隆完成之后，输入 <code>nautilus</code> 以 root 权限打开 nautilus ，找到当前目录（一般是主目录），打开源码文件夹找到 gnomeGlobalAppMenu@lestcape 文件夹，将这个文件夹复制到 /usr/share/gnome-shell/extensions 文件夹下。

6. 在应用程序菜单中选择 Teaks ，进入 GNOME Tweak Tool，选择扩展，启用该扩展。

7. 启用后不会立即显示扩展，需要注销重新登录。

8. 成功后删除主文件夹下的项目文件夹，打开终端输入 <code>sudo rm -rf Gnome-Global-AppMenu</code>

———— 另外 ————

由于系统默认启用了应用程序菜单的扩展，导致样子不好看，我们需要在 Teaks 中禁用该扩展，禁用后也需要注销重新登录。