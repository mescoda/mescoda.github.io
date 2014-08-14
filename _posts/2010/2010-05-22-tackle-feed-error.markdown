---
layout: post
status: publish
published: true
title: "解决博客的feed问题"
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
wordpress_id: 21
wordpress_url: http://mescoda.com/?p=21
date: '2010-05-22 22:04:08 +0800'
date_gmt: '2010-05-22 14:04:08 +0800'
categories:
- "稀烂的技术"
tags:
- RSS
- Wordpress
comments: []
---
<p>昨天被<a href="http://www.paradoxleo.com/">@Leo_wei</a> 同学发现博客的RSS有问题，情况如下：</p>
<blockquote>
<p>XML解析错误：xml处理指令不在实体的开始部分<br />位置：http://mescoda.tk/feed/&nbsp; <br />行：2，列：1：&lt;?xml version=&#8221;1.0&#8243; encoding=&#8221;UTF-8&#8243;?&gt; </p>
</blockquote>
<p>一番Google发现，原来是feed的xml第一行，多了一个空行引起的错误，<br />
解决方法如下<br />
查看wp-config.php，wp-rss2.php，wp-atom.php，functions.php<br />
三个文件是否在程序外有空行，即是查看&lt;?php…?php&gt;外有没有空行，如果有删除就好，上述操作后问题依旧存在，因为除三个文件以外，可能有的插件也会有这个问题，大家照葫芦画瓢地修正就好。<br />
以上。</p>
