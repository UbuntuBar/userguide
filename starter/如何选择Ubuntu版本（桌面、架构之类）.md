# 我该如何挑选适合我的 Ubuntu 版本?
Canonical 针对不同用户开发了各种 Ubuntu 版本，按架构分，可以分为 x86 x64 arm(armel) arm64 powerpc 等等，按用途分可以分为桌面版、服务器版和嵌入式版(Ubuntu Core)，按桌面环境分可以分为 Ubuntu(曾经有段时间使用自己开发的 Unity)、Ubuntu GNOME (17.10 及之后直接称为 Ubuntu ) ，Kubuntu（KDE桌面）、Lubuntu（LXDE、LxQT 桌面）、Xubuntu（Xfce桌面）、Ubuntu Budgie (Budgie 桌面)、Ubuntu MATE（MATE桌面），还有中国定制版的 Ubuntukylin(MATE+本土化壁纸和程序）。

非官方的 Ubuntu 分支就多了去了，比如著名的 Linux Mint ，基于 FreeBSD 内核的 UbuntuBSD （目前已经 GG），macOS 风格的 elementary OS 。

## 1. 按用处分
个人 PC 当然用桌面版，不然你装 Server 和 Core 干什么？敲命令好玩？没实用价值。

服务器不用多说了，Server 可以。

我见过有人在服务器上装桌面版，这并不是一个好选择，因为桌面会耗费你的资源，造成浪费，且桌面在某些方面并没有文本模式稳定，服务器可不能开玩笑。

Core 一般适用于树莓派等嵌入式设备以及 Docker，树莓派的配置众所周知，带桌面就是找死(当然有人跑 Ubuntu 

MATE，但在生产环境中并不推荐这样做)，Server 的话，有些组件可能用不到，所以，Core 是个好选择。

## 2. 桌面
GNOME KDE Budgie Unity 这四个都是重量级的桌面环境，配置不行不建议用。

LXDE LXQT MATE Xfce 这四个算比较轻的，当然也不太好看，不过有办法可以美化。

其他桌面，i3wm 啥的，这些太小众且配置麻烦，不说。

另外，如果你习惯 Windows 操作界面的话可以试试 KDE（但若配置不行就 LXDE/LxQT）。

## 3. 架构
x86 在目前来说已经逐步退出舞台，但是对于旧机器来说，x86 是一个比较好的选择，因为占用资源相对来说比较少。

x64 在目前是一个推荐选择，如果你的机器并不是老掉牙的机器的话，请一定要安装64位。所谓“32位兼容性好64位兼容性不好”这种言论，这个在 WinXP x64 时代可以说，但在现在不可以。

arm 及 arm64 一般用于移动设备、嵌入式设备及某些服务器。arm是32位，arm64 顾名思义。
