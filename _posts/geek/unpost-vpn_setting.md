---
layout: post
title:  虚拟专用网络
category: Geek
comments: true
---
## Centos **pptp**建立虚拟专用网络
实验条件：

	vps服务器（采用OpenVZ/KiwiVM)
    系统：centos7_x86-64
实验步骤：

+	检查服务器的**PPP**服务是否开启



	[root@localhost ~]# cat /dev/ppp
	cat: /dev/ppp: 没有那个设备或地址
显示状态是这样，则代表开启成功可以继续，否则请联系检查服务器的**PPP**服务
+	安装必要组件


	1. [root@localhost ~]# yum clean all
	2. [root@localhost ~]# yum update
	3. [root@localhost ~]# yum install iptables ppp pptpd

注：1.2为了防止yum源出现错误，进行更新。3是安装建立虚拟专用网络的必要组件，如果提示没有**pptp**软件包，则应安装**epel**源扩展软件包。

+	配置**pptp**


	1.[root@localhost ~]# vi /etc/pptpd.conf
 添加
 >	localip 192.168.1.1(VPS服务器的IP)
		remoteip 19.16.0.8-19.16.0.24(给使用虚拟专用网络分配的IP)
	
    2.[root@localhost ~]# vi /etc/ppp/options.pptpd
配置DNS，添加
>	ms-dns 8.8.8.8 
>	ms-dns 114.114.114.114

	3.[root@localhost ~]# vi /etc/ppp/chap-secrets
设置用户名密码分配IP地址
>	格式为：client	server	sercet	IP Addresses
>	例如: username	pptpd	username	*

则用户名为username，服务为pptpd，密码为username,** * **代表IP地址自由分配。

+	修改内核参数


	1.[root@localhost ~]# vi /etc/sysctl.conf
在末尾加上
>	net.ipv4.ip_forward=1

	2.[root@localhost ~]# sysctl -p
使内核修改生效，如无回显表明设置成功，如报错需执行以下命令后再次执行”sysctl -p”：

>    rm -f /sbin/sysctl
    ln -s /bin/true /sbin/sysctl

+	添加**iptables**转发规则


	[root@localhost ~]# iptables -t nat -A POSTROUTING -s 19.16.0.0/24 -j SNAT --to-source VPS服务器IP
    
为防止转发规则重启后失效，需将规则写入文件，使其开机自动生效

	[root@localhost ~]# vi /etc/rc.d/rc.local
将上述转发规则写入文件末尾

	[root@localhost ~]# chmod +x /etc/rc.d/rc.local
赋予该文件执行权限

+	启动**pptp**服务并设置开机启动


	[root@localhost ~]# pptpd start
    [root@localhost ~]# chkconfig pptpd on
---
经过以上配置服务器端的配置完成，只需在主机端设置**pptp**服务即可连接到虚拟专用网络了。




