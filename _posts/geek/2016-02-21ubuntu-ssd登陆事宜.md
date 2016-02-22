### ubuntu 运维
+ 用户管理

1. 添加用户:
		useradd -r username(用户名)
		passwd username
		useradd -g root username //将username添加到root权限组

2. 删除用户:
		userdel -r username

+ 禁用root用户通过ssh登陆
		vi /etc/ssh/ssd_config
		add this code :
	`PremitRootLogin no`
	 	service ssh restart
