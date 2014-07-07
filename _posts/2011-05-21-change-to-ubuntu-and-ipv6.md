---
title: 转移到Ubuntu同时开启ipv6
date: 2011-05-21 00:46:07 +0800
layout: post
permalink: /blog/2011/05/change-to-ubuntu-and-ipv6.html
categories:
  - 石马 | Code
  - 言吾 | Talk
tags:
  - ipv6
  - Ubuntu
---
转眼又大半年过去了，曾经的火炉南京也烧到了35度的高温，风就像蒸汽一样的薰人。不过晚上的凉风仍然让人感觉到夏天还没有正在到来。生活依然平淡的在继续，“要加薪”没有成功，但是也没有胜利者，就如同在法院外放鞭炮的人一样，他们也仅仅是在那一刹那得到了一些病态的慰籍。如同在微博上“狂欢”的人们一样，生活并没有因此也改变，生存环境也不会因此而宽大，铁屋子似乎越来越密封。一如南京中午13：00的空气。

闲得无事，终于想去折腾Linux，选择自然是我在06还是07年索取过的漂洋过海来到中国的<a href="http://www.ubuntu.com" rel="external" title="Ubuntu">Ubuntu</a>。不料冲动坏事，在格式化的时候把我的1TB硬盘全部格掉，更始料未及的是两天前冲动的那个我用Recovery软件恢复的时候，把原来要恢复的扇区给覆盖了，导致近一年的相片无存，如同我的生命少了一年。

今天在Hi-PDA的水与空气的D版，再次翻回两天前看到的IPV6的帖子，以及关于“方校长”和“白名单”的种种讨论和逆袭，干脆“破罐破摔”，系统就装了Ubuntu 11.04，反正不得已用Windows的时候，我那1000块收回来的IBM Thinkpad X41上面的Win7可以派上用场。于是终于第一次完整的体验了Linux，用起了命令行，穿越了IPV6，很好很强大——不得不说。虽然固有的10多年的Windows想法时时作崇，影响使用，但是如今的系统的人性化已经让我很受用，特别是强大的命令行，不再需要找网站，下软件，安装到哪哪，注意有没有恶意插件，只需要简单的几行命令。这让我觉得我以前可浪费了多么宝贵的生命！

***IPV6完成后的截图：***  
<a href="http://web.chenjun.com/images/ubuntu/screenshot.png" rel="external"><img src="http://web.chenjun.com/images/ubuntu/screenshot.png" width="400" alt="Ubuntu Screenshot" title="Ubuntu Screenshot" class="center" /></a>  
**  
### 具体步骤：

</strong>  
<!--more-->

> Ctrl+Alt+T 打开终端，输入如下命令：  
> `$sudo apt-get install miredo<br />
$ifconfig`  
> 在结果中应该能看见一个叫 teredo 的虚拟网卡。
> 
> `$ ping6 ipv6.google.com`  
> *PING ipv6.google.com(2404:6800:8003::93) 56 data bytes  
> 64 bytes from 2404:6800:8003::93: icmp_seq=2 ttl=57 time=910 ms..*  
> 现在您的浏览器应该可以访问 <a href="https://ipv6.google.com" rel="external">https://ipv6.google.com</a> 了。
> 
> `$sudo gedit /etc/hosts`  
> 把host列表拷贝进去,  
> hosts列表发布地址：<a href="http://docs.google.com/View?id=dfkdmxnt_61d9ck9ffq" rel="external">http://docs.google.com/View?id=dfkdmxnt_61d9ck9ffq</a>  
> 现在应该可以正常访问：<a href="http://www.youtube.com/" rel="external">http://www.youtube.com/</a>
> 
> 修改下防火墙设置：  
> `$sudo gedit /etc/default/ufw`  
> 把*IPV6=no* 改成 **yes**  
> 最后禁用/启用防火墙来使刚刚的改动生效：  
> `$ sudo ufw disable<br />
$ sudo ufw enable`
> 
> Via：<a href="http://www.lirui.name/post/206.html" rel="external">http://www.lirui.name/post/206.html</a>

废话很多，也许没人看，多年后自己来翻，也许记得，也许已遗忘，一如我翻看2004年的文字一样；一如我电脑中被清空的那一年的照片一样；一如，我们看到不知真假的哆啦A梦结局（Via<a href="http://zh.wikipedia.org/wiki/%E5%93%86%E5%95%A6A%E5%A4%A2%E6%9C%80%E7%B5%82%E5%9B%9E" rel="external" title="哆啦A梦最终回">【1】</a>、<a href="http://www.douban.com/group/topic/1398105/" rel="external" title="自闭症版">【2】</a>），痛苦的如同死去一样。

*——星期六, 五月 21, 12:44 上午【The End】*