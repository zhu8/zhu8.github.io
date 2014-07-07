---
title: 关闭WordPress的Revision功能
date: 2009-03-03 23:25:55 +0800
layout: post
permalink: /blog/2009/03/disable-wordpress-revision.html
categories:
  - 黑犬 | Other
tags:
  - Hack
  - Revision
  - 网站
---
还是使用 [WordPress][1] 吧！。因为它的2.7实在是太诱人了。我从WP1.3开始用到现在，实在是太习惯和依赖了。虽然他有讨厌的Revision……

如何关闭Revision？我试用了几种方法：

*   **第一种**：在*wp-config.php*中加入如下代码：  
    <textarea name="code" class="php" cols="60" rows="10">define(&#8216;WP_POST_REVISIONS&#8217;, 0 );<br /> define(&#8216;AUTOSAVE_INTERVAL&#8217;, 72000 );</textarea>  
    经测试，新建文章没有问题，似乎是可以关掉，但当你在修改已经发布的文章的时候，仍然在其作用。——**放弃**。
*   **第二种**：使用插件：[No Revisions][2]，经测试可以使用。看了一下他的代码，很纯粹：  
    <textarea name="code" class="php" cols="60" rows="10"><?php @remove_action ( 'pre_post_update', 'wp_save_post_revision' ); ?></textarea>——
    
    **使用**。
*   **第三种**：如果你不想使用插件，可以参考这位老兄的[修改方法][3]。他说Comment掉第二条插件所使用的命令之后还要再加一句，但我测试，**单纯用上面那个插件是没有问题的**。

关于如何**回收利用在你还没来得及关闭Revision功能之前就产生的Revisions**？对我这个完美主义来说，我是不能容忍一堆无用的数据在我的Mysql里面，所以你可以去你的数据库进行编辑一番：找到 *post_type = “revision”* 的文章，将其数值修改为你即将要张贴的文章，其中几个要点：将 *post_status* 从 *inherit* 改成 **publish** ，将 *post_type* 从 **revision** 改成 **post**，其它例如： *post_name* *post_date* 这些自己改好就行啦！然后你就可以在你的文章列表中看到咯！

 [1]: http://wordpress.org
 [2]: http://www.hostscope.com/wordpress-plugins/norevisions-wordpress-plugin/ "The No Revisions WordPress Plugin"
 [3]: http://programmingnote.com/blog/?p=35