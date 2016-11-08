---
layout: post
title: Ubuntu下编译opencv各版本
date: 2016-08-26 15:52:44
header-img: /img/opencv-logo.png
tags: 
    - ubuntu
    - opencv

---


# OpenCV for linux


<!-- more -->

## 一、编译安装

### 1. CMAKE

#### 第一步是复制文件

文件都在 下载链接: [百度云](https://pan.baidu.com/s/1hs2TH3Y) `密码: deih`里


#### OpenCV 2.4.11 / 2.4.13


##### 0. 需要复制的文件

`opencv-3.1.0.zip
ocv_contrib-3.1.0.zip
ippicv_linux_20151201.tgz
`

##### 1. 解压文件

将`opencv-2.4.1*.zip`解压出来

##### 2. 在opencv-2.4.1*文件夹里

```
$ mkdir build
$ cd build

$cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D WITH_TBB=ON \
-D BUILD_EXAMPLES=ON ..
```

#### OpenCV 3.0.0

##### 0. 需要复制的文件
`opencv-3.0.0.zip
ocv_contrib-3.0.0.zip
ippicv_linux_20141027.tgz
`

##### 1. 解压文件

将`opencv-3.0.0.zip`和`opencv_contrib-3.0.0.zip`解压出来

##### 2. 在opencv-3.0.0文件夹里

```
$ mkdir build
$ cd build

$cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D WITH_TBB=ON \
-D OPENCV_EXTRA_MODULES_PATH=<change to opencv_contrib_modules> \
-D BUILD_EXAMPLES=ON ..
```
##### 3. 按Ctrl-C停止

执行完上面的命令，在看到正在下载`ippicv_linux_20141027.tgz`的时候按`Ctrl-C`停止cmake，将`ippicv_linux_20141027.tgz`替换`opencv-3.0.0/3rdparty/ippicv/downloads/linux-********/ippicv_linux_20141027.tgz`(ps:`********`代表一串十六进制数，这个数是随机的，但是应该只有一个这个文件夹)

##### 4. 继续CMAKE

```
$cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D WITH_TBB=ON \
-D OPENCV_EXTRA_MODULES_PATH=<change to opencv_contrib_modules> \
-D BUILD_EXAMPLES=ON ..
```

#### OpenCV 3.1.0

##### 0. 需要复制的文件

`opencv-3.1.0.zip
ocv_contrib-3.1.0.zip
ippicv_linux_20151201.tgz
`

##### 1. 解压文件

将`opencv-3.1.0.zip`和`ocv_contrib-3.1.0.zip`解压出来

##### 2. 在opencv-3.1.0文件夹里

```
$ mkdir build
$ cd build

$cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D WITH_TBB=ON \
-D OPENCV_EXTRA_MODULES_PATH=`<change to opencv_contrib_modules>` \
-D BUILD_EXAMPLES=OFF ..
```
##### 3. 按Ctrl-C停止

执行完上面的命令，在看到正在下载`ippicv_linux_20151201.tgz`的时候按`Ctrl-C`停止cmake，将`ippicv_linux_20151201.tgz`替换`opencv-3.1.0/3rdparty/ippicv/downloads/linux-********/ippicv_linux_20151201.tgz`(ps:`********`代表一串十六进制数，这个数是随机的，但是应该只有一个这个文件夹)

##### 4. 继续CMAKE

```
$cmake -D CMAKE_BUILD_TYPE=RELEASE \
-D CMAKE_INSTALL_PREFIX=/usr/local \
-D INSTALL_C_EXAMPLES=ON \
-D INSTALL_PYTHON_EXAMPLES=ON \
-D WITH_TBB=ON \
-D OPENCV_EXTRA_MODULES_PATH=`<change to opencv_contrib_modules>` \
-D BUILD_EXAMPLES=OFF ..
```


### 2. 安装


```
$make -j4 # 跟核心数一样最好
$sudo make install
```

## 二、 下载链接

### 国内快速下载

[opencv on git.oschina.net](https://git.oschina.net/hoseahsu/opencv.git)

```
https://git.oschina.net/hoseahsu/opencv.git
```

[opencv_contrib on git.oschina.net](https://git.oschina.net/hoseahsu/opencv_contrib.git)

```
https://git.oschina.net/hoseahsu/opencv_contrib.git
```

### 官方github链接

[opencv on github](https://github.com/opencv/opencv.git)

```
https://github.com/opencv/opencv.git
```

[opencv_contrib on github](https://github.com/opencv/opencv_contrib.git)

```
https://github.com/opencv/opencv_contrib.git
```


## 看完了觉得不错？
*点击选择下面的付款方式，请我喝杯咖啡吧*
<iframe src="http://hoseahsu.oschina.io/donate2me/?item=easy-select-style" style="overflow-x:hidden;overflow-y:hidden; border:0xp none #fff; min-height:240px; width:100%;"  frameborder="0" scrolling="no"></iframe>
