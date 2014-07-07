---
title: 看图说话：绑定Godaddy域名到Blogger
date: 2009-01-16 17:05:32 +0800
layout: post
permalink: /blog/2009/01/google-blogger-custom-domain-godaddy.html
categories:
  - 石马 | Code
tags:
  - Blogger
  - Domain
  - Godaddy
---
<p style='text-indent: 2em;'>
  为了用上已强大的Blogger，同时不闲置自己的域名，觉得绑定到Blogger上来，但是<b>万恶的土啬作祟</b>，拼命封我们的ghs.google.com，没有办法，只好曲线救国。 废话少说，以我的域名Zhu8.Net为例，域名位于同样被频繁<b>土啬</b>的Godaddy。相信很多域名位于天朝管理之外的朋友都有这样的问题，经过万能的Google和自己的摸索，总结如下：
</p>

<p style='text-indent: 2em;'>
  <b>第一步：</b>绑定域名，在Blogger里很好设置，这里就不赘述了。我使用<a href='http://chenjun.com/'>http://chenjun.com/</a> 绑定了我的Blogger，故而在Godaddy里面如下设置：
</p>

<img src='http://junnie.3322.org/images/zhu8.net/godaddy-11.png' style='margin: 0px auto 10px; display: block; width: 360px; height: 355px; text-align: center;' /> <p style='text-indent: 2em;'>
  请列位看官自行看图说话，如何创造自己的ghs.xxx.com。实在看不懂请留言。ghs.google.com的IP有<a href='http://out.zhu8.net/ghs'>这个地方</a>查很不错
</p>

<!--more-->

<p style='text-indent: 2em;'>
  <b>第二步：</b>解决www和non-www制定不同的问题。 由于Google只能绑定子域名（www亦是一种特殊格式的子域名），故我们要让根域名也指向到这里，<strike>如果你是Host domain在Godaddy，只要使用Forward就可以了。</strike>（<b style='background-color: rgb(255, 0, 0);'>经反复测试，此方法没有用，只有使用.htaccess解决，详见：<a href='#htaccess' id='h_xz' title='.htaccess'>注释</a> </b>）如下：
</p>

<img src='http://junnie.3322.org/images/zhu8.net/godaddy-8.png' style='margin: 0px auto 10px; display: block; width: 400px; height: 108px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-9.png' style='margin: 0px auto 10px; display: block; width: 400px; height: 172px; text-align: center;' /> <p style='text-indent: 2em;'>
  这样本来就算完了，但是因为无孔不入的<b>土啬</b>又来了。封掉了不知道多少Godaddy的IP，所以如果你不幸如果，域名的IP被封了，那你就需要换IP了。Godaddy的域名自带有免费空间，我们可以通过切换域名空间的IP。网上有很多教程，但是目前来说Godaddy把它藏的深了一点，不再是Switch Operating System，换成了<b>Upgrade/Downgrade Hosting Account</b>。图解如下：
</p>

<img src='http://junnie.3322.org/images/zhu8.net/godaddy-1.png' style='margin: 0px auto 10px; display: block; width: 400px; height: 239px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-2.png' style='margin: 0px auto 10px; display: block; width: 400px; height: 130px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-3.png' style='margin: 0px auto 10px; display: block; width: 259px; height: 334px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-4.png' style='margin: 0px auto 10px; display: block; width: 258px; height: 285px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-5.png' style='margin: 0px auto 10px; display: block; width: 264px; height: 242px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-6.png' style='margin: 0px auto 10px; display: block; width: 257px; height: 231px; text-align: center;' /><img src='http://junnie.3322.org/images/zhu8.net/godaddy-7.png' style='margin: 0px auto 10px; display: block; width: 260px; height: 319px; text-align: center;' /> <p style='text-indent: 2em;'>
  等待不过十几分钟，虽然Account Details里面的Status还是Pending Account Change，但是IP地址已经换了，Total DNS Control Panel里面的A Records已经变成了新的IP，等待……生效，一切OK！
</p>

<p style='text-indent: 2em;'>
  <b><span style='font-size: 130%;'>P.S:</span></b><i>Google Apps</i>等所有<b><i>Google Custom Domain</i></b>都适用此法。有问题，请留言！
</p>

<p id='htaccess' style='text-indent: 2em;'>
  注释：使用编辑器，如EditPlus新建UTF-8的新文件，内容为：
</p>

> RewriteEngine On  
> RewriteCond %{HTTP_HOST} ^zhu8.net  
> RewriteRule (.*) http://chenjun.com/$1 [R=301,L]

<p style='text-indent: 2em;'>
  请自行更改域名为你的域名即可，将文件保存为<span style='font-weight: bold;'>.htaccess</span>。使用<span style='font-weight: bold;'>ASCII</span>格式上传到你的Godaddy免费空间根目录，文件属性<span style='font-weight: bold;'>644</span>。至此全部完成。请测试：<a title='Zhu8.Net' href='http://zhu8.net/'>http://zhu8.net</a>
</p>

*<font color='#666666'>Technorati 标签: <a rel='tag' href='http://technorati.com/tag/Blogger' class='performancingtags'>Blogger</a>, <a rel='tag' href='http://technorati.com/tag/Godaddy' class='performancingtags'>Godaddy</a></font>*