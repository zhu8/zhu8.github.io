---
title: 从wordpress到textpattern
date: 2008-04-16 22:29:04 +0800
layout: post
permalink: /blog/2008/04/from-wordpress-to-textpattern.html
categories:
  - 石马 | Code
tags:
  - Hack
  - Textpattern
  - 乱码
  - 网站
---
其实<img class="right" title="Textpattern" style="FLOAT: right" alt="Textpattern" src="http://junnie.3322.org/images/zhu8.net/txp.gif" />很久以前就试用了 [<span class="caps">TXP</span>][1] ，但是一直是一头雾水，今天终于 <sup>其实昨天</sup> 就已经弄好了。不过一直wordpress导入有点小问题，所以一直没有换过来。现在折腾好了，做一下小 **记录：**

*   **解决乱码问题** 打开 *import_wp.php* ，找到下面这行：

<textarea name="code" class="php" cols="60" rows="10">mysql_select_db($b2db, $b2link);<br /> </textarea>在后面加上： <textarea name="code" class="php" cols="60" rows="10">mysql_query(&#8220;SET NAMES &#8216;utf8&#8242;&#8221;, $b2link);<br /> </textarea>

*   **增加 Excerpt 部分** 找到下面这行：

<textarea name="code" class="php" cols="60" rows="10">p.post_content as Body,<br /> </textarea>在后面加上： <textarea name="code" class="php" cols="60" rows="10">p.post_excerpt as Excerpt,<br /> </textarea>同样的，找到这行： <textarea name="code" class="php" cols="60" rows="10">Body_html = &#8216;&#8221;.doSlash($Body_html).&#8221;&#8216;,<br /> </textarea>在后面加上： <textarea name="code" class="php" cols="60" rows="10">Excerpt = &#8216;&#8221;.doSlash($Excerpt).&#8221;&#8216;,<br /> Excerpt_html = &#8216;&#8221;.doSlash($Excerpt).&#8221;&#8216;,<br /> </textarea>

*   **不导入附件生成的页面** 找到下面这行：

<textarea name="code" class="php" cols="60" rows="10">&#8220;.$wpdbprefix.&#8221;users as u on u.ID = p.post_author<br /> </textarea>在后面加上： <textarea name="code" class="php" cols="60" rows="10">WHERE p.post_status != &#8216;attachment&#8217;<br /> </textarea>差不多就这些了，在懒懒喵的 [旧文][2] 中提到的留言关闭问题已经在Textpattern · 4.0.6中得到了解决。 **但是我本人的一个问题，Tag问题还没有搞定，导入会变成Category，我是用的笨办法：直接在WP数据库中先删除它，哈哈！** 还有一个小问题，导入user错误，不过如果是单用户的Blog，大可不必去管这个问题。

*   放出修改后的 <del>import_wp.php</del>

*   *P.S* 初次使用 [Textile][3] ，感觉还要适应好段时间，不过用起来确实是种不同的体验。

 [1]: http://textpattern.com/
 [2]: http://blog.nahoya.com/archives/2006_09/129
 [3]: http://textile.thresholdstate.com/