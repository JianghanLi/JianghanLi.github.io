树莓派是物联网的雏形
or
树莓派是阻碍迈进云服务计算时代的糟粕
著作权归作者所有。
商业转载请联系作者获得授权，非商业转载请注明出处。
作者：吴海波
链接：https://www.zhihu.com/question/26840203/answer/34294146
来源：知乎

“Big Data is like teenage sex: Everyone talks about it, nobody really knows how to do it, everyone thinks everyone else is doing it, so everyone claims they are doing it too”
+ 树莓派温度查看
 CPU:	cat /sys/class/thermal/thermal_zone0/temp


+ 树莓派2使用usb无线网卡时，有时ssh会自动断开，这种情况可能是由于启用了电源管理功能，
无线网卡在空闲时会自动关闭。
运行iwconfig，观察Power Management状态，如果为on则需要修改。
解决：
修改配置文件：
sudo nano /etc/network/interfaces
在无线网卡(一般是wlan0)中添加一句
wireless-power off
重启sudo reboot再运行一次iwconfig

+ 要想永久禁用树莓派(屏幕)休眠，我们可以在/etc/profile.d路径下新建一个file，如Screen.sh，并将下面两条命令写入该文件，即可以实现永久禁用。
xsetdpms 0 0 0
xsets off

+ How to deactivate monitor sleep in Raspbery Pi
This is my personal experience. I have installed "Raspbery Pi Wheezy" in to my raspberry pi. I used it to display some browser based dashboard and it going to sleep mode frequently. i found this solution from one of the site i couldn't' remember what it is. Following was the solution what i have used to avoid this issue. It's worked perfect.

1. Open a root terminal in raspberry Pi. Now  you need to edit your script that's starting X. In the default build with lightdm.
2. Open "lightdm.conf" file located in,

     /etc/lightdm/lightdm.conf

3. Add below line in to SeatDefault section.
[SeatDefaults]
xserver-command=X -s 0 -dpms
4. Restart your Raspberry Pi.
Now issue should be solved.
