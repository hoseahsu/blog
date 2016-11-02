---
title: 在ubuntu16.04上安装有道词典
author: Hosea Hsu
date: 2016-10-11 20:00:37
subtitle:
tags:
    - 有道
    - 词典
    - ubuntu16.04

---

以前用Ubuntu 14.04 的时候，直接下载有道词典官方deb安装包，就安装好了，现在换成Ubuntu 16.04因为有些依赖问题就无法安装成功。于是Google之，成功解决，也顺便熟悉了一下dpkg的用法。

因为官方的deb包（Ubuntu版本的）依赖gstreamer0.10-plugins-ugly，但是该软件在16.04里面已经没有了。但其实没有该包，完全不影响有道词典的使用。所以我们可以去掉deb包里面对于该库的依赖。具体操作如下：

## 下载官方deb包


 <div align=center>
![image](/img/youdao-dict-download.jpg)
</div>

1. [点这里](http://cidian.youdao.com/index-linux.html)去有道官网

2. 选择 Ubuntu 版下载

ps: 下载下来的包名应该为`youdao-dict_1.1.0-0-ubuntu_amd64.deb`

## 解压deb

- 初始化

```bash
$ cd /the/path/of/youdao-dict's/deb # 去到有道词典deb包所在文件夹
$ mkdir youdao-dict # 创建youdao-dict目录
```

- 把该deb包解压到youdao-dict目录

```bash
$ dpkg -X ./youdao-dict_1.1.0-0-ubuntu_amd64.deb  youdao-dicta
```


- 解压deb包中的control信息（包的依赖就写在这个文件里面）

```bash
$ dpkg -e ./youdao-dict_1.1.0-0-ubuntu_amd64.deb youdao-dict/DEBIAN
```

## 编辑control文件

- 打开control文件

```bash
$ gedit youdao-dict/DEBIAN/control
```

- `删除Depends里面的gstreamer0.10-plugins-ugly`

- 保存文件并关闭gedit

## 重新打包/安装

- 重新打包
```bash
$ dpkg-deb -b youdao youdaobuild.deb
```

- 安装
```bash
$ sudo dpkg -i youdaobuild.deb
$ sudo apt -f install
```



# 看完了觉得不错？
*点击选择下面的付款方式，请我喝杯咖啡吧*
<iframe src="http://hosea.xyz/donate2me/?item=easy-select-style" style="overflow-x:hidden;overflow-y:hidden; border:0xp none #fff; min-height:240px; width:100%;"  frameborder="0" scrolling="no"></iframe>
