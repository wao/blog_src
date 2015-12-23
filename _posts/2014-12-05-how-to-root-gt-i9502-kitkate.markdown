---
layout: post
title: 如何在ubuntu 14.10下root GT-I9502 Samsung Galaxy S4 4.4.2 联通双卡版本
tags: GT-I9502
---

最近,把自己的Galaxy S4升级到4.4.2，安装了Google Play Store和系统服务,系统环境是ubuntu 14.10.下面就是步骤.

下载GT-I9502 Kitkate 4.4.2的原厂升级包:可以从sammobile上下载

下载驱动:可以从samsung的官网下载kies,里面就有驱动.

下载chainfire的CF-AUTO-ROOT包.里面有为GT-I9502 4.4.2编译的版本.解开压缩文件,内含samsung的刷机程序odin

安装ADB工具

打开virtual box,使用xp的虚拟机,记住要选中usb下的EHCI. 可能需要安装virtualbox的extension包.

启动虚拟机,安装KIES

安装成功以后,发送CTRL-ALT-DEL给虚拟机,在task manager中关闭kietrayagent.exe这个程序,否则odin检测不到手机.

将原厂升级包和CF-AUTO-ROOT包还有odin都拷入虚拟机的桌面.这一步很重要,否则odin会报一个韩文的错.

启动odin,点击pda,选择原厂升级包，等待,直到odin有输出.

将手机进入烧机模式( 关机后,同时按 volumn down + home + power,然后再按volumn up),插入usb线,odin就会发现一个串口.如果没有发现,在virtualbox中选择usb设备中的samsung.
点击odin中的start按扭,就可以了.

手机从新启动后,再烧入CF-AUTO-ROOT包,手机重启两次后,开机就可以看到supersu这个程序,root就成功了.

下面是安装gms程序:

从手机system目录下删除不用的程序,释放空间来安装gms包

下载gapps或pa_gapps包,然后将压缩包展开,将framework, priv-app, app, lib, etc相关目录中的东西手工拷贝到手机上的相关目录就可以了.







