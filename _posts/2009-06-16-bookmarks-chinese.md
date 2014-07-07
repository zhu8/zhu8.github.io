---
title: Movable Type中文化书签插件-Bookmarks Chinese
date: 2009-06-16 20:58:44 +0800
layout: post
permalink: /blog/2009/06/bookmarks-chinese.html
categories:
  - 黑犬 | Other
tags:
  - Bookmarks
  - Plugin
  - 汉化
  - 程序
---
<font style="font-size: 1.25em;"><b>描述：</b></font>

***BookmarksChinese***是我在使用了一些如<a class="" title="AddThis" target="_blank" href="http://www.addthis.com/">addthis.com</a>的按钮之后，发现对中文支持很差，所以弄的一个中文化的书签插件如果你还需要其他的按钮，请自行参考开发即可。  
作者信息：Zhu8 (<a class="" title="Zhu8''s Web" href="http://chenjun.com/">http://www.zhu8.net</a>)  
插件地址：<a class="" title="Zhu8''s Web" href="http://chenjun.com/blog/2009/06/bookmarks-chinese.html">http://chenjun.com/blog/2009/06/bookmarks-chinese.html</a>  
插件版本：1.0 Final (2009.6.4)

<!--more-->

<font style="font-size: 1.25em;"><b>插件结构：</b></font>

> mt-static/  
> 　　　　plugins/  
> 　　　　　　　　BookmarksChinese/  
> 　　　　　　　　　　　　style.css  
> 　　　　　　　　　　　　images/  
> 　　　　　　　　　　　　　　addtoany.png  
> 　　　　　　　　　　　　　　google.png  
> 　　　　　　　　　　　　　　digg.png  
> 　　　　　　　　　　　　　　technorati.png  
> 　　　　　　　　　　　　　　delicious.png  
> 　　　　　　　　　　　　　　friendfeed.png  
> 　　　　　　　　　　　　　　twitter.png

> cgi-bin/mt/  
> 　　　　plugins/  
> 　　　　　　　　BookmarksChinese/  
> 　　　　　　　　　　　　BookmarksChinese.pl  
> 　　　　　　　　　　　　php/  
> 　　　　　　　　　　　　　　function.mtaddtoanyurl.php  
> 　　　　　　　　　　　　　　function.mtgoogleurl.php  
> 　　　　　　　　　　　　　　function.mtdiggurl.php  
> 　　　　　　　　　　　　　　function.mttechnoratiurl.php  
> 　　　　　　　　　　　　　　function.mtdeliciousurl.php  
> 　　　　　　　　　　　　　　function.mtfriendfeedurl.php  
> 　　　　　　　　　　　　　　function.mttwitterurl.php

<font style="font-size: 1.25em;"><b>模板标签：</b></font>

> <$MTAddToAnyURL$>  
> <$MTDiggURL$>  
> <$MTDeliciousURL$>  
> <$MTFriendFeedURL$>  
> <$MTGoogleURL$>  
> <$MTTechnoratiURL$>  
> <$MTTwitterURL$>

<font style="font-size: 1.25em;"><b>例子：</b></font>

<img class="yui-img" style="float: left;" alt="Bookmarks Chinese Screenshot" title="Bookmarks Chinese Screenshot" src="http://junnie.3322.org/images/zhu8.net/BookmarksChinese.png" />

<a class=&#8221;delicious&#8221; href=&#8221;<$MTDeliciousURL$>&#8221; title=&#8221;收藏到美味书签&#8221; target=&#8221;_blank&#8221;></a></p> 

<font style="font-size: 1.25em;"><b>如何使用：</b></font>

1.  下载插件：【<a class="" title="Bookmarks Chinese 下载地址" target="_blank" href="http://chenjun.com/blog/upload/BookMarksChinese.zip"><b><span style="background-color: rgb(0, 0, 0); color: rgb(160, 255, 64);">这里下载</span></b></a>】
2.  参照文件目录，上传插件。
3.  修改**Index Templates**中的**Stylesheet（Style.css）**，在最后一行加上  
    *@import url(<$mt:StaticWebPath$>plugins/BookmarksChinese/style.css);*
4.  比如小站，我修改了Template Modules中的Entry Metadata，在其中找到：*  
    *  
    在后面加上引用代码，示例：  
    ***<span class=&#8221;separator&#8221;>|</span> <a class=&#8221;delicious&#8221; href=&#8221;<$MTDeliciousURL$>&#8221; title=&#8221;收藏到Delicious&#8221; target=&#8221;_blank&#8221;></a>  
    <a class=&#8221;twitter&#8221; href=&#8221;<$MTTwitterURL$>&#8221; title=&#8221;收藏到Twitter&#8221; target=&#8221;_blank&#8221;></a>  
    <a class=&#8221;friendfeed&#8221; href=&#8221;<$MTFriendFeedURL$>&#8221; title=&#8221;收藏到FriendFeed&#8221; target=&#8221;_blank&#8221;></a>  
    <a class=&#8221;google&#8221; href=&#8221;<$MTGoogleURL$>&#8221; title=&#8221;收藏到Google Bookmarks&#8221; target=&#8221;_blank&#8221;></a>  
    <a class=&#8221;digg&#8221; href=&#8221;<$MTDiggURL$>&#8221; title=&#8221;Digg This!&#8221; target=&#8221;_blank&#8221;></a>  
    <a class=&#8221;technorati&#8221; href=&#8221;<$MTTechnoratiURL$>&#8221; title=&#8221;收藏到Technorati&#8221; target=&#8221;_blank&#8221;></a>  
    <a class=&#8221;addtoany&#8221; href=&#8221;<$MTAddToAnyURL$>&#8221; title=&#8221;更多&#8230;&#8221; target=&#8221;_blank&#8221;>More!</a>***  
    请注意，代码需在之前，以免破坏网页格式。
5.  如果你需要加入其他的社会化网络按钮，请自己研究下源代码，参数很简单 <img src="http://chenjun.com/wp/wp-includes/images/smilies/icon_smile.gif" alt=":)" class="wp-smiley" /> 

<font style="color: rgb(255, 0, 0); font-size: 1.25em;"><b>结束语：</b></font>

以上，是我在Movable Type的**最后一篇帖子**。经过和Wordpress的对比，MT在可定制性和易用性方面，在资源**特别是中文资源**方面，远远**落后**于WP，而且我从06年开始就使用WP，也有一定的感情，所以决定，今天：2009年6月16日，再次回到WordPress的怀抱，使用WordPress 2.8重新搭建站点。

不过说实话，不知道是我用的*Webhostingbuzz*很不错还是我的日志比较少的原因，没有出现过CPU超限被警告的问题。而且，说实话，我很热爱静态化的MT，在访问速度上，静态化确实很是舒爽。

唉，废话少说，准备更新数据库，换WP。

***Bye-Bye，活字印刷&#8230;&#8230;（抱歉，在十二小时之后，我又回来了&#8230;&#8230;）***