---
layout: post
title: Linux and Windows are good friends
category: Geek
comments: true
---
### 为什么说基于Linux内核的操作系统和Windows是好盆友呢？
+	程序管理


据说在公元前姬发创建了分封制，将各个地方交个诸侯去管理；秦朝商鞅开创了中央集权制。这Linux就如分封制一样，各个程序分散管理，不到一定程度不必通知周天子(就把周天子权当linux的大管家吧)。Windows(应该听说过注册表吧)将管理集中在了注册表中，尝试打开注册表(运行regedit即可)，第一反应是：这尼玛是给人看的。是否有过这样的经历：无意间点到了程序文件夹下的某个文件，碰巧的是用记事本打开了，难道外星人入侵我的电脑了吗这这...怎么从来没见过这种字。而大多Windows配置文件都是这样的(要在双击点开这个程序后出来图形框框里的选项才能修改配置文件)不能像直接修改word一样直接修改配置文件。而在LInux中每个程序也都有与之对应的配置文件，为了方便管理这些配置文件大多放在一个文件夹下(/etc/);尝试打开一个吧，前面是一段介绍，每个功能均有注释，不管懂不懂怎么弄，还好是人类可读啦。一个分散，一个集中；分散中有集中，集中中有分散。

+	文件管理


姬发和嬴政单靠个人力量是不行的，在用人方面又是各有各的方法。(以下对历史人物的叙写纯属虚构)姬发想姜叔考验了我这么久，这在用人方面一定要谨慎，可是大势所趋现在是急需用人啊，最后决定有一段试用期考验合格就任用。而秦始皇则不同，情况很是严峻各个诸侯国逼得太紧了，这人才急缺，怎么办呢；嗯给他们归归类吧，A商鞅（秦国做贡献的人），B尉缭（背地说秦国坏话的高人），C高渐离(从他国叛逃的将领有些是间谍）；这三类人嬴政都选择了任用，这无疑为他创立秦国打下了一份基础。然而这也给他的人身安全造成了威胁。言归正传，这每个人就相当于系统中的每个文件，在Linux中不是先分类再读取或执行文件，而是根据每个文件内容中开头的信息（试用期）来识别是哪一类文件。与之不同的是Windows采用扩展名的方式（扩展名指.doc .xls .txt之类）来分类识别文件，我们都知道.exe是可执行文件。在Windows下双击qq.exe就会自动安装了（很是人性化，然而有时是不是不知不觉电脑多了好多垃圾软件甚至中病毒），Linux根据文件头如果识别为一个可执行文件是不可以自动执行的，需要管理员管理员赋予执行权限（chmod +x qq.sh)，所以可以防止许多病毒哦。

+	应用范围

基本上我们的电脑装的都是Windows操作系统，可能程序员员会将Linux作为唯一的系统，还有一些人装有windows和linux的双系统。我们用Windows其实也是非常方便的一切事情交个系统来管理自己只需享受这漂亮的界面，还有一致化的美感体验。用Linux可以尝试自己个性化一切事情，甚至自己可以把自己删除（rm -rf /)，不信你就在Windows下格式化C盘试试。还有一件重要的是：打游戏在Windows下我们可以愉悦流畅的玩大型游戏，然而在Linux虽然也有3D效果，然而并没有什么卵用。打游戏是大多使用的是NVIDIA的独立显卡，因其对Linux的支持问题（远远比不上Intel的核心显卡在驱动上的开源程度），Linux内核开发社区领导者linus Torvalds有着一段有趣的言论（仅供娱乐）。
![linus-torvalsd](/images/Linus-Torvalds-Fuck-You-Nvidia.jpg)
[videos](https://r2---sn-a5m7ln7z.googlevideo.com/videoplayback?lmt=1440387692166097&dur=16.764&key=yt5&mime=video%2Fmp4&sparams=dur%2Cid%2Cinitcwndbps%2Cip%2Cipbits%2Citag%2Clmt%2Cmime%2Cmm%2Cmn%2Cms%2Cmv%2Cpl%2Cratebypass%2Crequiressl%2Csource%2Cupn%2Cexpire&expire=1440858094&fexp=9407116%2C9407700%2C9407992%2C9408496%2C9408710%2C9409069%2C9415365%2C9415485%2C9415837%2C9416023%2C9416126%2C9416611%2C9416729%2C9417298%2C9417707%2C9417843%2C9418059%2C9418153%2C9418199%2C9418235%2C9418448%2C9418479%2C9419219%2C9419250%2C9420023%2C9420052&sver=3&requiressl=yes&itag=22&source=youtube&ratebypass=yes&pl=22&upn=SmVmC337piw&ipbits=0&mn=sn-a5m7ln7z&mm=31&id=o-AAp4vXmaGN5B0ELGxSYNxFTPUoCUdTsp4Cfl-1VwBu0n&initcwndbps=3313750&signature=CF02FAE10F9BFABC30BD4CD861885336CBD96B11.4115BD4D98B497D89DB44F75B621E75D0C35E580&ip=162.211.225.18&mv=m&mt=1440836416&ms=au)

###	据说喜欢研究Linux的少年们更加具有创造力。




