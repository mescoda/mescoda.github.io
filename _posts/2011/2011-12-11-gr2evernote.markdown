---
layout: post
status: publish
published: true
title: GR2Evernote — 将Google Reader的分享内容导入Evernote
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
excerpt: "Google在决定不提供Reader的分享功能后为用户<a href=\"http://www.google.com/reader/settings?display=import\"
  title=\"GR shared export\">提供了以往分享条目的导出</a>，我一直在用GR做信息的收集和整理，一共是1553篇文章，非常惊人的数目，这些通过一个个Shift+S积累起来的文字记录了这些年的成长与转变，对我来说是非常珍贵的东西。\r\n\r\n如您所见，这是个把Google提供的json文件转成一个个html帮助导入Evernote的python脚本。\r\n\r\n"
wordpress_id: 490
wordpress_url: http://mescoda.com/?p=490
date: '2011-12-11 21:19:22 +0800'
date_gmt: '2011-12-11 13:19:22 +0800'
categories:
- "稀烂的技术"
tags:
- Google
- Python
- Evernote
comments:
- id: 708
  author: wubei7231
  author_email: dyby@tom.com
  author_url: ''
  date: '2012-03-10 21:28:42 +0800'
  date_gmt: '2012-03-10 13:28:42 +0800'
  content: "请问是不是需要安装python。安装那个版本？"
- id: 709
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2012-03-10 22:02:23 +0800'
  date_gmt: '2012-03-10 14:02:23 +0800'
  content: "@wubei7231\r\n2.7就行"
- id: 735
  author: yaoyeR
  author_email: reyoay@gmail.com
  author_url: http://yaoyer.com
  date: '2012-04-14 12:08:59 +0800'
  date_gmt: '2012-04-14 04:08:59 +0800'
  content: "无比感谢，这个东西很好用。"
- id: 1001
  author: Cong ZHAO
  author_email: zhaocong.hk@gmail.com
  author_url: ''
  date: '2012-06-12 22:35:22 +0800'
  date_gmt: '2012-06-12 14:35:22 +0800'
  content: "好用个茄子，导出的html都是乱码……"
- id: 2956
  author: GRsd
  author_email: claffar@hotmail.com
  author_url: ''
  date: '2013-03-30 05:39:12 +0800'
  date_gmt: '2013-03-29 21:39:12 +0800'
  content: "总算找到了一个可用的将 Google Reader 导出数据（json）转换为可读文章内容的解决方案 ，且使用这个脚本输出的HTML最终显示效果也不错
    － 原文中的格式、内容元素等都得到了较好的保留，不过部分未设置全文输出的订阅源中的文章内容，依然是不完整的简文状态，但这样已经很好了。嗯，它对我很有帮助，非常感谢作者的努力，谢谢。"
- id: 10699
  author: Muh
  author_email: 5eaw4w9e@outlook.com
  author_url: http://www.facebook.com/profile.php?id=100003456837117
  date: '2014-07-08 18:13:38 +0800'
  date_gmt: '2014-07-08 10:13:38 +0800'
  content: I'm not quite sure how to say this; you made it exeelmtry easy for me!
---
<p>Google在决定不提供Reader的分享功能后为用户<a href="http://www.google.com/reader/settings?display=import" title="GR shared export">提供了以往分享条目的导出</a>，我一直在用GR做信息的收集和整理，一共是1553篇文章，非常惊人的数目，这些通过一个个Shift+S积累起来的文字记录了这些年的成长与转变，对我来说是非常珍贵的东西。</p>
<p>如您所见，这是个把Google提供的json文件转成一个个html帮助导入Evernote的python脚本。</p>
<p><a id="more"></a><a id="more-490"></a></p>
<p>说明：</p>
<ol style="list-style-type:hiragana">
<li>将shared-items.json与GR2Evernote.py置于相同目录下。</li>
<li>默认的保存位置是Windows的D:\gr，可以在代码第8行修改，修改时请注意格式（类似F:\Documents\gr，不要在最后加 \）。</li>
<li>运行后会在设定的文件夹内生成无数个html文件。</li>
<li>有些条目因为标题极长无法正常解析（通常为分享的tweet），会被命名为Tweets+序号。</li>
<li>导入Evernote时请使用Evernote的工具-导入文件夹。</li>
<li>缺陷是导入后无法重命。</li>
</ol>
<p>地址：<a href="https://github.com/mescoda/GR2Evernote" title="GR2Evernote">https://github.com/mescoda/GR2Evernote</a></p>
