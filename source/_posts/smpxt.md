---
title: 树莓派系统安装：无显示器，无网线，无键盘
date: 2019-12-16 22:21:04
tags: raspberry pi
---
## 前言
&emsp;&emsp;树莓派4b到手也一段时间了，很多小伙伴搜安装系统的教程的时候发现需要外接显示器，或许需要外接网线，或许需要外接键盘等等……我等穷学生某得钱买显示器啊，于是捣鼓出了这篇东西↓↓↓
<!-- more -->
## 一、首先下载镜像
https://www.raspberrypi.org/downloads/raspbian/
&emsp;&emsp;我们的树莓派是4GB的RAM+64GB的闪迪卡，所以我选择了带desktop的和recommended software的镜像，如果不需要可视化界面可以选择Lite。（或许你又要说了，你不是没显示器吗，为什么还要desktop？因为后面可以用VNC可视化操作……这个自行百度）
![镜像下载](1.png)
### 下载zip包，解压，会得到一个img镜像文件↓↓↓
![img镜像](2.png)
## 二、烧写镜像
https://sourceforge.net/projects/win32diskimager/
### 1、下载烧写工具，安装，打开……blablabla
![下载烧写工具](3.png)
### 2、把内存卡插到电脑上（通过读卡器或者转接套 and so on），选择我们刚刚解压得到的img镜像和我们的内存卡分区（我这里是E盘），然后点击“写入”。
![](4.png)
### “YES”，然后等待完成
![](5.png)
## 三、（有显示器的同学已经可以退场了，插上内存卡，接上显示器，启动就完事）开启ssh，现在的树莓派已经默认关闭ssh，需要手动打开：
### &emsp;&emsp;1、烧写完成后可以看到有一个boot分区![](6.png)
### &emsp;&emsp;2、打开，在里面新建一个文件，文件名叫“ssh”，不要双引号，不要后缀（具体操作：可以新建一个txt文件，重命名为ssh，把后缀名都删掉）如图↓↓↓
![](7.png)
## 四、设置WiFi自动连接
### 还是在boot分区，新建一个文件名为wpa_supplicant.conf的文件，打开，写入以下内容
```bash
country=CN
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1

network={
    ssid="你的WiFi名称"
    psk="你的WiFi密码"
    priority=1
}
```
### //上面的的ssid和psk都是要带英文双引号的
## 五、插上内存卡启动，等几分钟，打开路由器设置页面查看树莓派的ip地址，然后用finnal shell等ssh连接软件连接就可以了
## 六、码字不易，不点个赞再走吗？
![](head.jpeg)
