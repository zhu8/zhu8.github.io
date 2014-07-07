---
title: 定制Trackback特定样式
date: 2006-12-23 12:06:50 +0800
layout: post
permalink: /blog/2006/12/style-wordpress-trackback.html
categories:
  - 石马 | Code
tags:
  - Hack
  - Trackback
  - 网站
---
首先要自我打击一下，在产生这个想法之后，本来我是**异想天开**地想编成一个插件的，但研究半天发现自己其实对PHP语言还是个大菜鸟，远没有我想的那么简单，只好用笨办法了：手动添加代码到模板中去:em11:

本来想用的来自这里：<a href="http://www.tamba2.org.uk/wordpress/commentstyling/" title="Making Comments stand out" alt="Making Comments stand out" target="_blank">WordPress &#8211; Comment styling</a>，确实是一篇不错的文章，里面不仅介绍了为Trackback和Pingback增加独特样式，也有为特定评论的与众不同的显示提供了解决方案。而且作者Podz所写的<a href="http://www.tamba2.org.uk/wordpress/" title="WordPress Help - Podz @ Tamba2" target="_blank">The Temba2 WordPress Guides</a>是一篇不错的基础教程。评论姑且不谈，我需要的是第一个。

首先是在你的Blog模版的评论页面（一般为**comments.php**）找到这句：

<textarea name="code" class="php" cols="60" rows="10"><?php foreach ($comments as $comment) : ?></textarea>

在后面加上（<span style="color: green;"><sup><strong>1*</strong></sup></span>）：

<textarea name="code" class="php" cols="60" rows="10"><br /> <?php $istback = false; if($comment->comment_type == &#8221;trackback&#8221;) { $istback = true; } ?>

<br /> <?php $ispingb = false; if($comment->comment_type == &#8221;pingback&#8221;) { $ispingb = true; } ?>

<br /> </textarea>

随后再找到这句：<textarea name="code" class="php" cols="60" rows="10"><?php comment_text() ?></textarea>

在前后加上东西之后变成这个样子（<span style="color: green;"><sup><strong>2*</strong></sup></span>）：

<textarea name="code" class="php" cols="60" rows="10"><br /> <?php if($istback ) { echo ''
<div class="tbcomment">&#8221;;} ?>

<br /> <?php if($ispingb ) { echo ''
<div class="pbcomment">&#8221;;} ?>

<br /> <?php comment_text() ?>

<br /> <?php if($istback ) { echo ''</div> 

<p>
  &#8221;;} ?><br /> <?php if($ispingb ) { echo ''</div> 
  
  <p>
    &#8221;;} ?><br /> </textarea>
  </p>
  
  <p>
    <!--more-->
  </p>
  
  <p>
    当然，为了不那么打击自己而全部照抄，我做了点小小的修改：将（<span style="color: green;"><sup><strong>1*</strong></sup></span>）更改为：
  </p>
  
  <p>
    <textarea name="code" class="php" cols="60" rows="10"><br /> <?php $istb = false; if(get_comment_type() != "comment") { $istb = true; } ?>
    
    <br /> </textarea>
  </p>
  
  <p>
    这里就是图个简单，逆向思维，不是comment的当然就是Trackback和Pingback了:em06:
  </p>
  
  <p>
    后面的（<span style="color: green;"><sup><strong>2*</strong></sup></span>）也就一起简单了。
  </p>
  
  <p>
    <textarea name="code" class="php" cols="60" rows="10"><br /> <?php if($istb ) { echo ''
<div class="tbcomment">&#8221;;} ?>
    
    <br /> <?php comment_text() ?>
    
    <br /> <?php if($istb ) { echo ''</div> 
    
    <p>
      &#8221;;} ?><br /> </textarea>
    </p>
    
    <p>
      最后，在样式表中添加这个CSS样式，就大功告成了：
    </p>
    
    <p>
      <textarea name="code" class="php" cols="60" rows="10">.tbcomment {<br /> font:italic 1em/140% Georgia,sans-serif;<br /> color:gray;<br /> }</textarea>
    </p>
    
    <p>
      勉强以此安慰下自己，还能有一小小的创新:em12:，不过我并没有彻底的将Comment和Trackback区分开来，单独显示。因为我的TB不算多，所以没有再去弄个插件影响速度，如果你有需要，可以看看这些地方，希望能对你有所帮助：
    </p>
    
    <ul>
      <li>
        <a href="http://mk.netgenes.org/wiki/Trackping_Separator" title="Trackping Separator" target="_blank">Trackping Separator</a>
      </li>
    </ul>
    
    <ul>
      <li>
        <a href="http://www.noscope.com/journal/2005/01/wp-separating-trackbacks-pingbacks" title="Noscope | Separating Trackbacks &#038; Pingbacks in WordPress 1.5 &#038; Above" target="_blank">Separating Trackbacks &#038; Pingbacks in WordPress 1.5 &#038; Above</a>
      </li>
    </ul>
    
    <ul>
      <li>
        <a href="http://jackosh.com/wpplugins/trackbacklist/" title="Trackback List Plugin" target="_blank">Trackback List Plugin</a>
      </li>
    </ul>