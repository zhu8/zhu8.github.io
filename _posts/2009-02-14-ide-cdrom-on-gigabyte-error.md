---
title: 技嘉主板安装IDE光驱和硬盘跳线问题(赠：Beyond-情人)
date: 2009-02-14 01:31:38 +0800
layout: post
permalink: /blog/2009/02/ide-cdrom-on-gigabyte-error.html
categories:
  - 黑犬 | Other
tags:
  - Beyond
  - IDE
  - Music
  - 主板
  - 技嘉
  - 音乐
---
原来的板子坏了，新买了一块技嘉的板子（GA-M61PME-S2），因为我原来的硬盘和DVD-ROM都是IDE接口的，但是接上去之后系统要么启动很慢，要么在见到欢迎页面前就死掉。【启动&#8221;Detecting IDE Drives&#8230;&#8221;处非常慢，然后就是到&#8221;Verifying DMI Pool Data&#8230;&#8221;，一样巨慢，然后无法从硬盘启动&#8230;&#8230;】而我原来的大板子悍马HA01-GT没有这个问题，只是被我刷BIOS刷爆了。不高兴去修了。反正技嘉那块板子才300多点，就买回来。前两天装系统，今天启动就老是不行。开始还怀疑是电源不够，我的是航嘉冷静王2.0钻石版300W的。后来检查跳线，因为我的跳线没有动过，Benq光驱还是在Slave上，而我的日立硬盘还是在Master上面；BIOS中的M/S设置也是对的。

去网上查了一下，有位哥们跟我情况比较相似：

> 急啊,高后帮下忙啊!!! 入手的技嘉GA-MA78GM-S2H 1.1版（BIOS版本是F5），用的是双IDE（光驱和硬盘），硬盘是希捷80G,光驱是原来dvd的，挂光驱硬盘开机检测查找IDE设备都要2分多钟，光驱是从盘,硬盘为主盘,用的一根IDE线,设置从CDROM第1启动盘,HDD第2可以安装好系统番茄花园SP3,装完重起电脑后进系统就找不到硬盘了,这个时候,不管我把光驱还是硬盘设为第一启动设备都是这样，是不是BIOS里有什么设置的问题？？？？？有什么办法不啊? 配置:内存2G一根. CPU4800+. 电源全汉200W额定, 硬盘80G IDE,光驱DVD IDE</p>
这位兄弟的解答，也解决了我的问题：<span style="font-weight:bold;">硬盘跳线设为 MASTER.光驱跳线设为slave或为无，<span class="Apple-style-span" style="color: rgb(255, 0, 0);">ide线长端（好像蓝色）接主板IDE口，另一端（好像黑色）接硬盘，中间接光驱，硬盘与光驱距离连接短，注意硬盘光驱安装位置</span>。我昨天用了2小时终于搞定。</span>

延伸阅读：跳线<img style="float:right; margin:0 0 10px 10px;cursor:pointer; cursor:hand;width: 320px; height: 240px;" src="http://junnie.3322.org/images/zhu8.net/jumper.jpg" border="0" alt="跳线（Jumper）" title="跳线（Jumper）" />

跳线（英文Jumper）是控制线路板上电流流动的小开关。它的作用是调整设备上不同电信号的通断关系，并以此调节设备的工作状态，如确定主板电压、驱动器的主从关系等。跳线基本上由两个部分组成，一部分是固定在主板、硬盘等设备上的，由两根或两根以上金属跳针组成（如图1）；另一部分是跳线帽（如图2），这是一个可以活动的部件，外层是绝缘塑料，内层是导电材料，可以插在跳线针上面，将两根跳线针连接起来。[<span style="font-weight:bold;font-style:italic;">更多&#8230;&#8230;</span>][1]

<!--more-->

哦！今天是<span style="font-weight:bold;">情人节</span>了哈！我这么晚还没有睡觉，老婆要打了&#8230;&#8230;晚安！今晚特约演出：Beyond-情人

歌手： Beyond  
专辑： 海阔天空 精选  
公司： 滚石唱片公司

<span style="font-weight:bold;">Beyond：情人</span>

盼望你没有为我又再度暗中淌泪  
我不想留底 你的心空虚  
盼望你别再让我象背负太深的罪  
我的心如水 你不必痴醉

Woo&#8230; 你可知谁甘心归去  
你与我之间有谁

是缘是情是童真 还是意外  
有泪有罪有付出 还有忍耐  
是人是墙是寒冬 藏在眼内  
有日有夜有幻想 无法等待

盼望我别去后会共你在远方相聚  
每一天望海 每一天相对

盼望你现已没有让我别去的恐惧  
我即使离开 你的天空里

Woo&#8230; 你可知谁甘心归去  
你与我之间有谁

是缘是情是童真 还是意外  
有泪有罪有付出 还有忍耐  
是人是墙是寒冬 藏在眼内  
有日有夜有幻想 无法等待

多少春秋风雨改  
多少崎岖不变爱  
多少唏嘘的你在人海

是缘是情是童真 还是意外  
有泪有罪有付出 还有忍耐  
是人是墙是寒冬 藏在眼内  
有日有夜有幻想 无法等待

<span style="font-weight:bold;font-style:italic;font-size:x-large;color: rgb(51, 102, 255);">Download：</span>[SkyDrive][2]。

 [1]: http://www.cfanclub.net/article.php?itemid-3866-type-news.html
 [2]: http://cid-bd7009cfadcc1c1d.skydrive.live.com/browse.aspx/Music "Zhu8's Skydrive"