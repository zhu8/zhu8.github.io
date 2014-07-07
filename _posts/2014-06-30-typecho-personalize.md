---
title: Typecho个性化常用代码
date: 2014-06-30 20:51:49 +0800
layout: post
permalink: /blog/2014/06/typecho-personalize.html
categories:
  - 石马 | Code
tags:
  - Typecho
  - 代码
---
发觉自己真的老了，好多东西折腾不动了……一个网站模版和个性化，竟然每天就只能折腾一点点。遥想公瑾当年，一晚上不睡觉，整个网站页面就优化完毕了。

网站<a rel="nofollow" href="http://chenjun.com/oldblog/">以前</a>用<a rel="nofollow" href="http://www.movabletype.com">MT</a>，最喜欢的当然是静态化，虽然用的是3.X，但是能达到我的要求，就一直没有换。但是后来不知道为什么，反垃圾评论功能失效了……作为一个强迫症兼偏执狂，当然受不了这个，但是自己又没劲再去折腾了。于是，换到了<a rel="nofollow" href="http://www.typecho.org">Typecho</a>，因为实在是不想用大众脸的<a rel="nofollow" href="http://wordpress.org">WordPress</a>！

诚如我<a rel="nofollow" href="http://chenjun.com/2014/06/start.html">第一篇日志</a>所言，微博微信都是危险的，他让我们渐渐失去了长时间去思考的能力，适应了快餐文化，适应了随手点个赞。还是回到公开在互联网的个人网志，保存放心、安全，所有东西都归我管。当然，如果不是<a rel="nofollow" href="http://www.blogger.com">Blogger</a>被**土啬女干**了，我是愿意去那里安家的。

好久没有废话了，那废话就说到这里吧，因为Typecho的官方文档还有很多不完善的地方，自己找以及在网上琢磨，为了方便也许只有一两个人能到的这里的友人们，下面就放一些常用的Typecho的代码吧。

这里先放一个***列表***，详细的请进入**阅读全文**。

1.  <a rel="nofollow" href="#1">归档页面模板</a>
2.  <a rel="nofollow" href="#2">获取分类描述</a>
3.  <a rel="nofollow" href="#3">前后文章调用代码</a>
4.  <a rel="nofollow" href="#4">随机颜色标签云</a>
5.  <a rel="nofollow" href="#5">返回网页顶部</a>
6.  <a rel="nofollow" href="#6">段落首行缩进两字符</a>

<!--more-->

## <a name="1"></a>1、归档页面模板

（这里涉及到官方文档首段代码没有结尾，注意参考下面的第一段）

    <?php
    /**
     * 归档页面模板
     *
     * @package custom
     */; ?>
    
    <?php $this->need('header.php'); ?>
    
        <div class="col-mb-12 col-8" id="main" role="main">
            <h3 class="archive-title">日志归档</h3>
    <?php $this->widget('Widget_Contents_Post_Recent', 'pageSize=10000')->to($archives);   
        $year=0; $mon=0; $i=0; $j=0;   
        $output = '<div id="archives">';   
        while($archives->next()):   
            $year_tmp = date('Y',$archives->created);   
            $mon_tmp = date('m',$archives->created);   
            $y=$year; $m=$mon;   
            if ($mon != $mon_tmp && $mon > 0) $output .= '</ul></li>';   
            if ($year != $year_tmp && $year > 0) $output .= '</ul>';   
            if ($year != $year_tmp) {   
                $year = $year_tmp;   
                $output .= '<h3 class="al_year">'. $year .' 年</h3><ul class="al_mon_list">'; //输出年份   
            }   
            if ($mon != $mon_tmp) {   
                $mon = $mon_tmp;   
                $output .= '<li><span class="al_mon">'. $mon .' 月</span><ul class="al_post_list">'; //输出月份   
            }   
            $output .= '<li>'.date('d日: ',$archives->created).'<a href="'.$archives->permalink .'">'. $archives->title .'</a> <em>('. $archives->commentsNum.')</em></li>'; //输出文章日期和标题   
        endwhile;   
        $output .= '</ul></li></ul></div>';   
        echo $output;   
    ?> 
        </div><!-- end #main -->
    
        <?php $this->need('sidebar.php'); ?>
        <?php $this->need('footer.php'); ?>
    

## <a name="2"></a>2、获取分类描述

    <?php echo $this->getDescription(); ?>
    

*案例演示：*

    <?php $this->widget('Widget_Metas_Category_List')
    ->parse('<li><a href="{permalink}" title="{description}">{name}</a> ({count})</li>'); ?>
    

## <a name="3"></a>3、前后文章调用代码

    <?php $this->thePrev(); ?> <?php $this->theNext(); ?>
    

## <a name="4"></a>4、随机颜色标签云

    <?php $this->widget('Widget_Metas_Tag_Cloud', 'ignoreZeroCount=1&limit=30')->to($tags); ?>
    <ul class="tags-list">
    <?php while($tags->next()): ?>
        <li><a style="color: rgb(<?php echo(rand(0, 255)); ?>, <?php echo(rand(0,255)); ?>, <?php echo(rand(0, 255)); ?>)" href="<?php $tags->permalink(); ?>" title='<?php $tags->name(); ?>'><?php $tags->name(); ?></a></li>
    <?php endwhile; ?>
    </ul>
    

## <a name="5"></a>5、返回网页顶部

在footer.php页面增加如下代码（可直接下载我的第二段JS代码，将其中的图片地址改成你自己定义的）：

    <!-- Start of Go-Top Code -->
    <script type="text/javascript" src="http://ajax.googleapis.com/ajax/libs/jquery/1.7.2/jquery.min.js"></script>
    <script type="text/javascript" src="http://chenjun.com/usr/uploads/top.js"></script>
    <!-- End of Go-Top Code -->
    

## <a name="6"></a>6、段落首行缩进两字符

编辑Style.css文件，增加如下代码：

    .post-content p{ 
    text-indent: 2em; /*em是相对单位，2em即现在一个字大小的两倍*/ 
    } 
    

后续待补充，部分参考：<a rel="nofollow" href="http://docs.typecho.org">Typecho官方文档</a>以及<a rel="nofollow" href="http://typecho.me">Typecho.me</a>，一并致谢！