---
title: 在ubuntu下安装android studio和oracle-JDK
author: Hosea Hsu
date: 2016-09-21 21:03:49
subtitle:
tags: 
    - android
    - android studio
    - Ubuntu
    - oracle-jdk

---

# 手动安装oracle-jdk


##### 第一步,下载oracle-jdk

要下载和安装 Java JDK8，请访问下载页获得最新的发行版本。根据你机器的 Ubuntu 系统的情况可以选择下载 32 位或 64 位的发行版本。[](http://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html)

　　在下载之前，您必须接受许可协议。

　　下载文件，保存。在 Ubuntu 系统中 Firefox 浏览器会默认保存到 ~/Downloads 目录下。

　　oracle-jdk8-ubuntu

##### 第二步，打开终端运行如下命令来解压下载的文件。

```
tar -xvf ~/Downloads/jdk-8-linux-x64.tar.gz
```

　　然后运行如下的命令，在 /usr/lib 目录中创建一个为保存 Java JDK 8 文件的目录。

```
sudo mkdir -p /usr/local/jvm/jdk1.8/
```
　　接下来运行如下命令把解压的 JDK 文件内容都移动到创建的目录中。

```
sudo mv jdk1.8.0/* /usr/local/jvm/jdk1.8/
```
##### 第三步，配置

运行如下命令来配置 Java

```
sudo update-alternatives --install "/usr/local/bin/java" "java" "/usr/local/jvm/jdk1.8/bin/java" 1
```

接下来，拷贝和粘贴下面这一行到终端执行，以启用 Javac 模块。

```
sudo update-alternatives --install "/usr/local/bin/javac" "javac" "/usr/local/jvm/jdk1.8/bin/javac" 1
```

最后，拷贝和粘贴下面一行到终端以完成最终的安装。

```
sudo update-alternatives --install "/usr/local/bin/javaws" "javaws" "/usr/local/jvm/jdk1.8/bin/javaws" 1
```

要验证下 Java 是否已经完全安装的话，可以运行下面的命令来测试。

　　java –version

# 安装 android studio

1. 去[android studio 中文社区](http://www.android-studio.org/index.php/download)下载android studio 的ide和sdk(可在ide的安装过程中然其自动下载sdk)

2. 将ide解压到需要安装的文件夹

3. 按照提示继续便可！

## 遇到的问题

### ide自动下载好sdk过后出现unable to run mksdcard sdk 错误

系统是ubantu 16.04 64位

原因：缺少32位lib

解决方法：

```
sudo apt-get install lib32z1 lib32ncurses5  lib32stdc++6
```

## 参考


[手动安装oracle-jdk](http://www.bitscn.com/os/linux/201405/199753.html)

[unable to run mksdcard sdk](http://www.linuxdiyf.com/linux/13124.html)

[64位Ubuntu15.04安装Android Studio教程](http://www.linuxdiyf.com/linux/12081.html)


# 看完了觉得不错？
*点击选择下面的付款方式，请我喝杯咖啡吧*
<iframe src="http://hosea.xyz/donate2me/?item=easy-select-style" style="overflow-x:hidden;overflow-y:hidden; border:0xp none #fff; min-height:240px; width:100%;"  frameborder="0" scrolling="no"></iframe>
