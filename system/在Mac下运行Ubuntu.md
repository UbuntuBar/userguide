# 在 Mac 计算机下运行 Ubuntu

## 写在前面
如果您只是为了一套 Unix 环境进行你的工作而选择在 Mac 下运行  Ubuntu 的话，私以为这不是一个好的选择。因为 Mac 本身就提供了一套完整的 Unix 环境 —— macOS (Mac OS X)，而且 macOS 在 Mac 电脑上的兼容性肯定要比 Ubuntu 要好，因此基于这个原因在 Mac 上运行 Ubuntu 的完全没有必要的。

如果您是其他原因需要在 Mac 上运行 Ubuntu，请阅读下面的安装方法和注意事项。

## 安装 Ubuntu

### 准备
如果您用的是 MacBook 且机器型号较新请外接键盘鼠标，因为新款 MacBook 的键盘和 Touchpad 完全无法在 Ubuntu 下运行。（截止至目前（2018.06）已知 2016 款和 2017 款无法运行，15 款不知道）。

在 macOS 磁盘工具中压缩一部分空间用作 Ubuntu 系统。如果准备单系统的话这一步跳过。

### 写入 Ubuntu 镜像到 U 盘
如果您准备在 macOS 下将 Ubuntu ISO 镜像写入到 Ubuntu，请安装后名为 <code>Etcher</code> 的应用，然后按照指示将 Ubuntu 镜像写入优盘。

### 安装系统
插入 U 盘，重启机器，在苹果 logo 显示之前按 Option 键，选择 EFI Boot。
按照常规安装方法安装 Ubuntu。

## 注意事项
1. 请备份好重要数据！

2. 正如我之前所说，一些 MacBook 硬件不兼容于 Ubuntu，比如内置键盘、触摸板和 Touch Bar，请考虑别的方法。
不过可以通过别的方式使用这些硬件，但是有点折腾。请点击[这里](https://github.com/Dunedan/mbp-2016-linux)，此外，这个页面还提供了一些其他的解决方案。但是这个方案还不够完美.




