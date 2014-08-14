---
layout: post
status: publish
published: true
title: kindleSpliter — 提取My Clippings.txt
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
excerpt: "又一个Python写的小工具，帮助导出Kindle的My Clippings.txt，自动按书名提取笔记和书摘。\r\n\r\n说明：\r\n<ol
  style=\"list-style-type:hiragana\">\r\n<li>将My Clippings.txt与kindleSpliter.py置于相同文件夹</li>\r\n<li>运行kindleSpliter.py，生成output文件夹</li>\r\n<li>output文件夹中有以书名命名的txt文件以及\"
  ! titleAll.txt\"</li>\r\n<li>\" ! titleAll.txt\"包含所有做过笔记书摘的书名列表</li>\r\n<li>有新的书摘时，更新My
  Clippings.txt并再次运行kindleSpliter.py，所有导出的txt会自动更新</li>\r\n</ol>\r\n\r\n"
wordpress_id: 471
wordpress_url: http://mescoda.com/?p=471
date: '2011-12-02 18:35:28 +0800'
date_gmt: '2011-12-02 10:35:28 +0800'
categories:
- "稀烂的技术"
tags:
- Kindle
- Python
comments:
- id: 540
  author: tonie
  author_email: tonyxly@sina.com
  author_url: ''
  date: '2011-12-02 19:01:48 +0800'
  date_gmt: '2011-12-02 11:01:48 +0800'
  content: "不知道能否为nook2写个类似的工具。。。呃。。"
- id: 541
  author: mescoda
  author_email: mescodasun@gmail.com
  author_url: ''
  date: '2011-12-02 22:08:13 +0800'
  date_gmt: '2011-12-02 14:08:13 +0800'
  content: "我没有nook2啊。。"
- id: 2493
  author: kris
  author_email: yu_xue@me.com
  author_url: http://blog.jishunv.info
  date: '2013-01-09 16:23:19 +0800'
  date_gmt: '2013-01-09 08:23:19 +0800'
  content: "在我的Mac上测试失败，虽然生成了文件，但是内容是空的，求助！"
- id: 2497
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2013-01-10 09:54:13 +0800'
  date_gmt: '2013-01-10 01:54:13 +0800'
  content: "@kris\r\n可能有这样几个原因：\r\n我用的 python 版本是2.x，3.x 或许有问题；\r\n我用的 kindle 版本是
    kindle3，不知道其他版本生成的 My Clippings.txt 格式是不是一样。"
- id: 2722
  author: kris
  author_email: yu_xue@me.com
  author_url: http://blog.jishunv.info
  date: '2013-02-18 22:31:29 +0800'
  date_gmt: '2013-02-18 14:31:29 +0800'
  content: "！！！！我找到原因了，因为我用的是Mac.\r\n\r\n对于同样的一个My Clippings.txt，Mac/Unix读的换行是 '\\r\\n'\r\n而Windows读的换行符是'\\n'\r\n把第十四行的'\\n'
    换成 '\\r\\n'即可\r\n\r\n参见 “http://javaeye-mao.iteye.com/blog/211354”"
- id: 10692
  author: Sandro
  author_email: kyygran2w@mail.com
  author_url: http://www.facebook.com/profile.php?id=100003456716696
  date: '2014-07-08 16:58:02 +0800'
  date_gmt: '2014-07-08 08:58:02 +0800'
  content: Good to see real expertise on display. Your coturibntion is most welcome.
- id: 12529
  author: questionable personal
  author_email: yuxsdghk4@outlook.com
  author_url: http://buyviagraviagra.com
  date: '2014-08-06 18:37:18 +0800'
  date_gmt: '2014-08-06 10:37:18 +0800'
  content: That's a smart way of looking at the world.
---
<p>又一个Python写的小工具，帮助导出Kindle的My Clippings.txt，自动按书名提取笔记和书摘。</p>
<p>说明：</p>
<ol style="list-style-type:hiragana">
<li>将My Clippings.txt与kindleSpliter.py置于相同文件夹</li>
<li>运行kindleSpliter.py，生成output文件夹</li>
<li>output文件夹中有以书名命名的txt文件以及" ! titleAll.txt"</li>
<li>" ! titleAll.txt"包含所有做过笔记书摘的书名列表</li>
<li>有新的书摘时，更新My Clippings.txt并再次运行kindleSpliter.py，所有导出的txt会自动更新</li>
</ol>
<p><a id="more"></a><a id="more-471"></a></p>
<p>地址：<a href="https://github.com/mescoda/kindleSpliter">https://github.com/mescoda/kindleSpliter</a></p>
