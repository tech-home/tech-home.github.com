---
layout: post
title: "几个常用的ADB命令"
date: 2017-01-30 02:06:09 +0800
comments: true
categories: android
---
  ADB全称Android Debug Bridge,在android开发中基本算得上是家喻户晓，我们经常会使用这个sdk中的工具来管理我们连接到电脑上的android设备。熟悉、掌握一些基本的adb命令，不仅可以提高我们的逼格，还可以提升我们的开发效率，在这，我总结一下本人在开发中会用到的一些adb命令。   
<!--more-->
####查看连接设备
> ***adb devices***

这个命令可以查看当前连接的所有android设备、包括模拟器。
####安装软件
> ***adb install -option path***   
> * -r  保存数据缓存    
> * -s  安装到sd卡


将指定的apk文件安装到设备上
####卸载软件
> ***adb uninstall -option < packagename >***   
> * -k  保存配置和缓存文件    


根据指定包名，卸载设备上的软件。

####查看软件包名
> ***adb shell pm list packages -option***   
> * -s  获取系统级别的软件包名    
> * -3  获取非系统级别的第三方软件包名    

列出设备上已安装的程序包名。
####查看软件详情
> ***adb shell dumpsys package < packagename >***   

根据指定包名，查看设备上某个包的具体信息。
####清除软件缓存
> ***adb shell pm clear < packagename >***   

清空指定软件的应用缓存。

####获取设备序列号
> ***adb get-serialno***   

####获取屏幕分辨率
> ***adb shell wm size***   

####获取屏幕密度
> ***adb shell wm density***   

####查看当前打开activity的名字
> ***adb shell dumpsys activity | grep "mFocusedActivity"***   

####推送文件到设备
> ***adb push <本地路径-电脑> <远程路径－设备>***   

####拉取设备上的文件
> ***adb pull <远程路径> <本地路径>***  

####重启设备
> ***adb reboot [bootloader | recovery]***   
> * null 什么都不加直接重启   
> * bootloader 重启到bootloader引导模式 等同于：adb reboot-bootloader   
> * recovery 重启到recovery刷机模式











