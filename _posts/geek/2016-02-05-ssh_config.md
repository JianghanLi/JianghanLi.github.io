---
layout: post
title:  
category: Geek
comments: true
---
### shh客户端频繁断线~
入手了一台腾讯服务器（一元每月~~着实良心了一次）安装了ubuntu14.04,在windows下使用Putty用ssh连接服务器。
> 这是一个悲伤的故事
> 正在运行sudo apt-get upgrade -y，断线了。
> nohup从此成了我的右手，相伴左右。

+ 据说ssh客服端会定时向服务器端发送数据，不过谁知道这是什么，就算了吧。
+ 更改服务器端的设置，使服务器定时向ssh客服端发送数据以确定shh客户端是否活动。

		sudo vi /etc/ssh/sshd_config
这是ssh服务配置文件添加：
		
        #间隔时间
        ClientAliveInterval 60
        #最多次数
        ClientAliveCountMax 4
最多无响应时间允许60*4=240s