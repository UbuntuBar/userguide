# 关于 GNOME 美化和折腾（适用于 Ubuntu 18.04）

## 写在前面
GNOME 其实很好用，虽然默认的 GNOME 比较简陋，但是可以通过安装各种扩展来丰富它的功能。对了，据说 GNOME 还有内存泄露的bug，不过只要不是超长时间不关机应该问题不大（编者注：已经修复）

## 安装优化工具
At first，安装 tweaks（中文叫优化），商店里有，或者<code>sudo apt install gnome-tweak-tool</code>，这东西可以改字体，设置主题，设置并启用扩展等
如何安装主题，字体等。

## 美化网站
[gnome-look](http://gnome-look.org) 网站了解一下，里面有 gtk 主题，gnome-shell 主题（需要 user themes 扩展，扩展安装方法在下面），图标主题，鼠标光标主题等（还有grub 主题，但是和gnome没关系）。安装gtk主题，光标主题和 gnome-shell 主题都只需要把主题包解压下来，把文件夹移动到 ~/.local/share/themes（或者/usr/share/themes 或者~/.themes），图标主题移动到~/.local/share/icons（或者。。。懒得打字），字体可以移动到。。。（懒得打字，找规律吧），或者在 nautilus（文件管理器）里双击打开字体文件然后安装。设置字体和主题用 tweaks

## 安装扩展
没用过 gnome shell extensions 就不要说自己用过 GNOME 了。GNOME 扩展安装十分简单（部分扩展比较麻烦），可以直接去商店下载（附加软件，shell扩展）或者apt安装（两者等效），如果觉得商店扩展不够多，可以去[extensions.gnome.org](http://extensions.gnome.org) 安装，此时建议安装一个好东西（sudo apt install chrome-gnome-shell），安装这个之后就可以直接在web页面用鼠标点一点安装扩展。顺便说一下， Ubuntu  18.04左边那个dock栏，其实是扩展 dash-to-dock 的阉割版，如果需要更多功能，可以安装dash-to-dock 的原版。然后推荐几个不错的扩展：dash-to-panel（不喜欢dock的可以试试这个），no title bar（名字可能少了连接符或者多了空格，作用是窗口最大化不会两个额头）。卸载扩展可以在 web 上点叉叉卸载，或者去 <code>~/.local/share/gnome-shell/extensions</code> 下面删文件夹（或者找规律）。部分扩展安装时还需要安装另外的包，注意看扩展的描述。

## 另外
有些吧友曾经提到的问题：控制按钮（口一X）怎么移到左边，答曰：tweaks；topbar怎么一下透明一下不透明，答曰：主题决定的，不服换主题/改主题

## 作者
原作者：xuheng_yeah

修改：njlyf2011 （神楽坂四夕）

