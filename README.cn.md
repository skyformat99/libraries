# LightWeight Libraries

[English](README.md) | 简体中文

[![Build](https://travis-ci.org/gozfree/libraries.svg?branch=master)](https://travis-ci.org/gozfree/libraries)
[![Release](https://img.shields.io/github/release/gozfree/libraries.svg)](https://github.com/gozfree/libraries/releases)
[![License](https://img.shields.io/github/license/gozfree/libraries.svg)](https://github.com/gozfree/libraries/blob/master/LICENSE.LGPL)

这是一组通用的Ｃ基础库
* 全部用POSIX C实现，目标是为了跨平台兼容x86, arm, android, ios.
* 每个库都是一个独立工程，使用时，只需要把真正用到的库加入你的项目中即可，无需导入整个工程
* 适用于嵌入式，以及网络服务开发等场景

|类型|名称|
|----|----|
|基础数据结构|dict hash ringbuffer queue rbtree sort vector macro
|网络库|rtsp skt p2p rpc ipc
|异步|gevent workq thread
|I/O解析|base64 config log file filewatcher strex cmd
|多媒体|uvc jpeg-ex mp4parser
|其他|debug hal plugin time

## 编译方法
推荐 Ubuntu14.04 gcc-4.8.4+ 及以上版本

  * linux 平台 (32/64 bit)  
   `$ cd libraries`  
   `$ ./build.sh`  
   `$ sudo ./build.sh install`

  * host(linux) target(rasberrypi)  
    (you need download [toolchain of rasberrypi](https://github.com/raspberrypi/tools.git))  
   `$ ./build.sh all pi`

  * host(rasberrypi board)  
   `$ ./build.sh`  
   `$ sudo ./build.sh install`  

  * android arm 交叉编译  
   (需要下载 [android-ndk-r9-linux-x86_64.tar.bz2](http://dl.google.com/android/ndk/android-ndk-r9-linux-x86_64.tar.bz2))  
   `$ ./build.sh all android`  

  * android 原生开发  
    also need ndk tools  
   `$ cd android_jni_libs`  
   `$ ndk-build`  

   After install, the libxxx.xx will be installed in /usr/local/lib/.  
   libxxx.h, libxxx.so or libxxx.a of libraries are also in ./output/$(ARCH)  

## 自动生成代码
   如果要加入你自己的开发库，只需要执行如下命令，即可自动生成代码和编译框架  
  `$ ./autogen_lib.sh libfoo`

## License
LGPL/GPLv3. Please refer to the LICENSE file for detailed information.

* 一般的开源项目如nginx/ffmpeg/redis等，都有各自的基础库，且实现较为相近，取各库的优点，实现较为通用的库，且库的命名不带特定工程前缀，在实现自己的工程时，方便代码的快速集成。
* 当库完成度和稳定性高时，会release 到ubuntu launchpad.net PPA供下载安装

* liblog 已提供ubuntu 16.04 64bit下载

## apt-get获取

  $ `sudo add-apt-repository ppa:gozfree/ppa`  
  $ `sudo apt-get update`  
  $ `sudo apt-get install liblog`


## 作者与贡献者
非常欢迎参与开发维护这套基础库

|                                               |                                               |
|-----------------------------------------------|-----------------------------------------------|
| [CMShuyuhui](https://github.com/CMShuyuhui)   | [core1011](https://github.com/core1011)       |
| [elfring](https://github.com/elfring)         | [ktsaou](https://github.com/ktsaou)           |
| [zh794390558](https://github.com/zh794390558) | [gozfree](https://github.com/gozfree)         |
