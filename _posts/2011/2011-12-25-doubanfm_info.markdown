---
layout: post
status: publish
published: true
title: doubanFM_info —— 豆瓣FM歌曲列表
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
wordpress_id: 500
wordpress_url: http://mescoda.com/?p=500
date: '2011-12-25 21:39:42 +0800'
date_gmt: '2011-12-25 13:39:42 +0800'
categories:
- "稀烂的技术"
tags:
- Douban
- Python
comments: []
---
<p>导出豆瓣FM的歌曲列表(csv)</p>
<p>说明：</p>
<ol style="list-style-type:hiragana">
<li>根据各频道的id不同，修改第10行，可以导出不同频道，具体参照代码5-8行</li>
<li>打开csv文件若出现乱码，请用记事本打开并保存为utf-8格式</li>
<li>理论上循环足够次可以得到豆瓣电台所有歌曲的列表，有兴趣的同学可以将53行的200修改成足够大的数字</li>
<li>导出的文件中包含歌曲名，歌手，歌曲id，专辑排名，专辑名，专辑地址，MP3地址</li>
</ol>
<p>看了下动漫频道的数据，EVA和吉卜力无悬念地占据前列，真不愧是豆瓣，另外还有Cowboy Bebop。</p>
<p>地址：<a href="https://github.com/mescoda/doubanFM_info">https://github.com/mescoda/doubanFM_info</a></p>
