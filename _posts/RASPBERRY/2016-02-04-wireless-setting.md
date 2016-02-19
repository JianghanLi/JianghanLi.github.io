---
layout: post
title: Raspberry之无线网络
category: RASPBERRY
comments: true
---
树莓派并不是支持所有的无线网卡，不够某宝的服务还是周到买了板子还带了无线网卡~

	Environment:Raspberry2B(debian jessie)
检查无线网卡是否工作

    lsusb
	ifconfig

编辑/etc/network/interfaces文件：

	auto lo
    iface lo inet loopback

    auto eth0
    allow-hotplug eth0
    iface eth0 inet manual

    auto wlan0
    iface wlan0 inet manual
    wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
可以看到wlan0模块是我们所需要的，从文件中可以看出设计者希望我们编辑wpa_supplicant.conf来进行无线网络的配置，不过也可以直接修改这个文件。
改成如下所示：

	(1)静态IP
    auto wlan0
    allow-hotplug wlan0(允许usb网卡热插拔)
    iface wlan0inet static
    address ***.***.***.***(IP)
    netmask 255.255.255.0
    gateway ***.***.***.***(一般为网络提供设备地址)
    dns-nameservers ***.***.***.***(DNS)
    wpa-ssid "******"(网络提供名称)
    wpa-psk "******" (password)
    (2)动态获取IP
    auto wlan0
    allow-hotplug wlan0
    iface wlan0 inet dhcp
    wpa-ssid "******"
    wpa-psk "******"

成功后执行

    sudo ifdown wlan0
    sudo ifup wlan0
	ifcongfig

可以看到wlan0已经有了IP地址,成功连接上了无限网络。
