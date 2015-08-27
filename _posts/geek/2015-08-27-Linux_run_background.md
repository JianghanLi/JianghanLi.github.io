---
layout: post
title: 在linux中如何让程序在后台可靠工作
category: Geek
comments: true
---

##让进程在后台可靠运行
---
	实验条件：VPS_Centos6-x86
	实验工具：Putty
注：以下内容仅保证在centos6-x86操作系统中稳定运行。

我们经常会遇到这种情况：在命令界面下希望一个在后台运行，在主界面又可以做其他工作互不影响；或在远程登录一台服务器时，运行比较耗时的程序时，希望其不受本地网络连接的影响在后台稳定运行。

面对如此的情况**nohup**是不错的选择。首先看一下帮助文件的容：

![nohup](/images/man_nohup.PNG)

由此可以看出使用**nohup**命令是非常方便的，只需在命令面前加入**nohup**即可：
	
	运行实例：
	[root@pi~]#nohup wget http://mirror.pnl.gov/fedora/linux/releases/22/Workstation/x86_64/iso/Fedora-Live-Workstation-x86_64-22-3.iso &
	[1] 878
	[root@pi~]#nohup: 忽略输入并把输出追加到“nohup.out"
	
	注：wget为下载命令； & 代表把程序放到后台运行。
之后执行 ps aux 命令就可以看到程序运行的进程了。之后注销或关闭本地端都不会影响程序的在后台的正常运行了。
