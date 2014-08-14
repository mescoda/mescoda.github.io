---
layout: post
status: publish
published: true
title: pixivCrawler — Pixiv排行榜图片下载器
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
excerpt: "一个用Python写的<a href=\"https://github.com/mescoda/pixivCrawler\">Pixiv排行榜图片下载器</a>，基本上有了她以后，你就能明白为什么店长的新番扫雷总是一堆高质量的配图以及为什么有些死宅的桌面总是那么触及心灵。\r\n\r\n原是好友NStal的点子，这家伙野心很大，除了实现功能以外还正在BeautifulSoup的基础上写一个类似jQuery的页面爬取器。我作为一个Python初心者，我还是安心发明轮子好了。\r\n\r\n说明：\r\n<ol
  style=\"list-style-type:hiragana\">\r\n<li>当然你需要先有Python和wget。</li>\r\n\r\n<li>然后下载<a
  href=\"http://www.crummy.com/software/BeautifulSoup/#Download\">Beautiful Soup</a>，并将BeautifulSoup.py与pixivCrawler.py置于相同目录下。</li>\r\n\r\n<li>默认的保存位置是Windows的D:\\pixiv，可以在代码第4行修改，修改时请注意格式（类似F:\\Pictures\\pixiv，不要在最后加
  \\）。</li>\r\n\r\n<li>运行后会在上面的文件夹内生成monthly、weekly、daily三个子文件夹以及这三个子文件夹内的以今天日期为名的子子文件夹，日期文件夹内为图片。</li>\r\n\r\n<li>图片的命名规则是：排行数-画师id-图片id-该图片的pixiv域名号</li>\r\n\r\n<li>如果是图集命名规则是：排行数-画师id-图片id_p图集内次序-该图片的pixiv域名号</li>\r\n\r\n<li>这样的命名规则有助于找到原地址，即http://www.pixiv.net/member_illust.php?mode=medium&illust_id=图片id
  和 http://img域名号.pixiv.net/img/画师id/图片id.格式</li>\r\n\r\n<li>默认下载前一个月、前一周、昨天的全部排行前100，如果只想下前50，可以把最后的for循环改为range(1,2)，其他类推；如果只想下monthly，可以只保留for循环内的download('monthly',str(i))，其他类推。</li>\r\n</ol>\r\n\r\n地址：<a
  href=\"https://github.com/mescoda/pixivCrawler\">https://github.com/mescoda/pixivCrawler</a>\r\n\r\n"
wordpress_id: 444
wordpress_url: http://mescoda.com/?p=444
date: '2011-11-26 20:23:25 +0800'
date_gmt: '2011-11-26 12:23:25 +0800'
categories:
- "稀烂的技术"
tags:
- Pixiv
- Python
comments:
- id: 507
  author: NStal
  author_email: nstalmail@gmail.com
  author_url: ''
  date: '2011-11-26 20:57:31 +0800'
  date_gmt: '2011-11-26 12:57:31 +0800'
  content: "不需要修改用户名和密码？"
- id: 508
  author: mescoda
  author_email: mescodasun@gmail.com
  author_url: ''
  date: '2011-11-26 21:07:10 +0800'
  date_gmt: '2011-11-26 13:07:10 +0800'
  content: "@NStal\r\n不用登录\r\n我在wget后面加上了 --referer=http://www.pixiv.net/"
- id: 509
  author: NStal
  author_email: nstalmail@gmail.com
  author_url: ''
  date: '2011-11-26 21:09:19 +0800'
  date_gmt: '2011-11-26 13:09:19 +0800'
  content: "诶？我这边如果不登录的话只下的到mode=medium的小图。登录之后才能下到大图（mode=big），否则会被重定向。而mode=manga貌似还是用的是ajax。\r\n得解析javascript...ORZ.\r\n\r\nFate金闪闪这张因为本来就不大所以mode=medium和mode=big的结果是一样的。"
- id: 510
  author: NStal
  author_email: nstalmail@gmail.com
  author_url: ''
  date: '2011-11-26 21:10:08 +0800'
  date_gmt: '2011-11-26 13:10:08 +0800'
  content: Referer是必须的，但是如果不等录mode=big会重定向。
- id: 511
  author: NStal
  author_email: nstalmail@gmail.com
  author_url: ''
  date: '2011-11-26 21:13:25 +0800'
  date_gmt: '2011-11-26 13:13:25 +0800'
  content: "你对比一下\r\nhttp://www.pixiv.net/member_illust.php?mode=medium&amp;illust_id=23257250\r\n和登录点进去之后的\r\nhttp://www.pixiv.net/member_illust.php?mode=big&amp;illust_id=23257250\r\n的大小，这个是日榜的第二名。（不能直接URL，得从前一个URL点图片进去）。"
- id: 512
  author: NStal
  author_email: nstalmail@gmail.com
  author_url: ''
  date: '2011-11-26 21:14:53 +0800'
  date_gmt: '2011-11-26 13:14:53 +0800'
  content: "http://www.pixiv.net/member_illust.php?mode=medium&amp;illust_id=23257250\r\n看看小图，然后登录点进去到\r\nhttp://www.pixiv.net/member_illust.php?mode=big&amp;illust_id=23257250\r\n\r\n这是daily的第二名。图片很大。"
- id: 513
  author: mescoda
  author_email: mescodasun@gmail.com
  author_url: ''
  date: '2011-11-26 21:29:38 +0800'
  date_gmt: '2011-11-26 13:29:38 +0800'
  content: "@NStal\r\n我是发现图片命名的规律\r\n小图就是图片id_s，medium就是_m，原图就是直接图片id\r\n\r\n所以。。\r\n比如daily第二那张\r\n在榜单的页面找到
    http://img19.pixiv.net/img/daria-chocolate/23257250_s.jpg\r\n然后替换成 http://img19.pixiv.net/img/daria-chocolate/23257250.jpg
    就是1200x1500的原图"
- id: 514
  author: NStal
  author_email: nstalmail@gmail.com
  author_url: http://www.nstal.cz.cc
  date: '2011-11-26 21:49:07 +0800'
  date_gmt: '2011-11-26 13:49:07 +0800'
  content: "原来如此！！！好巧喵阿～"
- id: 516
  author: noob
  author_email: noob@python.org
  author_url: ''
  date: '2011-11-27 14:51:08 +0800'
  date_gmt: '2011-11-27 06:51:08 +0800'
  content: "小白下了Python(for win)和wget,然后将BeautifulSoup.py与pixivCrawler.py置于相同目录下。\r\n不论点哪个py跳出错误就消失了.\r\n用python运行也是..不懂这门语言真悲剧.."
- id: 517
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2011-11-27 17:13:50 +0800'
  date_gmt: '2011-11-27 09:13:50 +0800'
  content: "@noob\r\n是在cmd里运行的吗？\r\n提示什么错误？\r\nwget有加到环境变量里吗？"
- id: 518
  author: noob
  author_email: noob@noob.org
  author_url: ''
  date: '2011-11-27 20:17:47 +0800'
  date_gmt: '2011-11-27 12:17:47 +0800'
  content: "谢天谢地谢m大..终于弄好了= =\r\n决定研究python了,不知m大有没各种基础向网址.."
- id: 519
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2011-11-27 20:34:52 +0800'
  date_gmt: '2011-11-27 12:34:52 +0800'
  content: "@noob\r\n入门书的话\r\n据说《A Byte of Python》不错 http://www.swaroopch.com/notes/Python\r\n还有
    O'Reilly的《Python学习手册》， 图灵的《Python基础教程》"
- id: 520
  author: noob
  author_email: noob@noob.org
  author_url: ''
  date: '2011-11-27 20:49:22 +0800'
  date_gmt: '2011-11-27 12:49:22 +0800'
  content: "额..下了第一张后发现停止下载.出现local variable 'img' referenced before assignment错误..用的python2.7.2
    32位版本.."
- id: 521
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2011-11-27 21:59:56 +0800'
  date_gmt: '2011-11-27 13:59:56 +0800'
  content: "是完整下了一张吗？\r\n应该是没这个问题的\r\n你再试试看"
- id: 522
  author: noob
  author_email: noob@noob.org
  author_url: ''
  date: '2011-11-27 22:07:30 +0800'
  date_gmt: '2011-11-27 14:07:30 +0800'
  content: "嗯..完整下了月排行第一张..之后就是\r\nTraceback (most recent call last):\r\n  File \"C:\\Users\\Administrator\\Desktop\\BeautifulSoup-3.2.0\\pixivCrawler.py\",
    lin\r\ne 63, in \r\n    download('monthly',str(i))\r\n  File \"C:\\Users\\Administrator\\Desktop\\BeautifulSoup-3.2.0\\pixivCrawler.py\",
    lin\r\ne 55, in download\r\n    for i in range(0,img_num):\r\nUnboundLocalError:
    local variable 'img_num' referenced before assignment"
- id: 523
  author: ract
  author_email: whiteract@gmail.com
  author_url: ''
  date: '2011-11-27 23:06:55 +0800'
  date_gmt: '2011-11-27 15:06:55 +0800'
  content: "先感谢下怎么好的东西,对咱这种懒人实在是太棒了.\r\n按照说明上的做基本没问题,不过咱是小白,有个问题就是咱想把月周日这三个部分分别下载,还有怎样能挂代理下载,因为咱这里直连速度是硬伤而且还是单线程."
- id: 526
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2011-11-28 09:42:42 +0800'
  date_gmt: '2011-11-28 01:42:42 +0800'
  content: "把55行的for i in range(0,img_num): 改成 for i in range(0,len(imgs_new)):  试试"
- id: 527
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2011-11-28 09:49:15 +0800'
  date_gmt: '2011-11-28 01:49:15 +0800'
  content: "@ract\r\n代理可以参考 http://www.satwe.com/archives/355.html 用wget的原生方法，在45行及58行的--referer=http://www.pixiv.net/
    后面加上你相应的代理设置\r\n\r\n只想下月榜就在最后的 for i in range(1,3): 里只留下 download('monthly',str(i))
    然后运行一遍\r\n想下周榜的时候就在最后的 for i in range(1,3): 里只留下 download('weekly',str(i))\r\n想下日榜的时候就在最后的
    for i in range(1,3): 里只留下 download('daily',str(i))"
- id: 528
  author: noob
  author_email: noob@noob.org
  author_url: ''
  date: '2011-11-28 11:06:31 +0800'
  date_gmt: '2011-11-28 03:06:31 +0800'
  content: "问题解决了...原来是因为我是手动复制过去的,弄错一个缩进- -..再次谢啦."
- id: 529
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2011-11-28 11:20:18 +0800'
  date_gmt: '2011-11-28 03:20:18 +0800'
  content: "不客气\r\n还有问题也请多反馈"
- id: 531
  author: ract
  author_email: whiteract@gmail.com
  author_url: ''
  date: '2011-11-28 12:50:49 +0800'
  date_gmt: '2011-11-28 04:50:49 +0800'
  content: "明白了,感谢"
- id: 628
  author: yel
  author_email: 452136412@qq.com
  author_url: ''
  date: '2012-01-31 17:07:10 +0800'
  date_gmt: '2012-01-31 09:07:10 +0800'
  content: "你好这里是完全的小白……\r\n一运行就出现Traceback (most recent call last):\r\n  File \"C:\\Documents
    and Settings\\Administrator\\桌面\\BeautifulSoup-3.2.0\\pixivCrawler.py\", line
    1, in \r\n    from BeautifulSoup import BeautifulSoup\r\n  File \"C:\\Documents
    and Settings\\Administrator\\桌面\\BeautifulSoup-3.2.0\\BeautifulSoup.py\", line
    448\r\n    raise AttributeError, \"'%s' object has no attribute '%s'\" % (self.__class__.__name__,
    attr)\r\n                        ^\r\nSyntaxError: invalid syntax\r\n这个了呢……"
- id: 633
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2012-02-01 11:14:18 +0800'
  date_gmt: '2012-02-01 03:14:18 +0800'
  content: "出错原因应该是你用的是Python 3 ，可以把3卸载装上2试试 http://python.org/ftp/python/2.7.2/python-2.7.2.msi"
- id: 634
  author: yel
  author_email: 452136412@qq.com
  author_url: ''
  date: '2012-02-01 17:02:02 +0800'
  date_gmt: '2012-02-01 09:02:02 +0800'
  content: "谢谢……！\r\n于是，新的问题出现了……\r\nTraceback (most recent call last):\r\n  File
    \"C:\\Documents and Settings\\Administrator\\桌面\\BeautifulSoup-3.2.0\\pixivCrawler.py\",
    line 63, in \r\n    download('monthly',str(i))\r\n  File \"C:\\Documents and Settings\\Administrator\\桌面\\BeautifulSoup-3.2.0\\pixivCrawler.py\",
    line 60, in download\r\n    os.remove(folder_root+'\\\\'+mode+'\\\\'+folder_time+'/'+ranknum+'-'+artistid+'-'+imgid+'-'+imghost+'.'+imgtype)\r\nWindowsError:
    [Error 2] : u'D:\\\\pixiv\\\\monthly\\\\2012-02-01/001-liberationzone-24105004-35.jpg'"
- id: 635
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2012-02-01 17:44:18 +0800'
  date_gmt: '2012-02-01 09:44:18 +0800'
  content: "呃 确定下程序第4行是 folder_root = 'D:\\pixiv' 吗？还是 folder_root = 'D:\\\\pixiv'"
- id: 637
  author: yel
  author_email: 452136412@qq.com
  author_url: ''
  date: '2012-02-01 20:50:24 +0800'
  date_gmt: '2012-02-01 12:50:24 +0800'
  content: "是folder_root = ‘D:\\pixiv’"
- id: 727
  author: vood
  author_email: vood039@gmail.com
  author_url: ''
  date: '2012-04-09 17:58:25 +0800'
  date_gmt: '2012-04-09 09:58:25 +0800'
  content: "建议写个下载器 可下载自己书签里的图= ="
- id: 898
  author: "妹子控"
  author_email: wangyitongying@qq.com
  author_url: http://www.meizico.com
  date: '2012-06-03 18:19:05 +0800'
  date_gmt: '2012-06-03 10:19:05 +0800'
  content: "哎，有点麻烦了"
- id: 10696
  author: Mudasir
  author_email: zoa4d5vg4@gmail.com
  author_url: http://www.facebook.com/profile.php?id=100003456857334
  date: '2014-07-08 17:46:16 +0800'
  date_gmt: '2014-07-08 09:46:16 +0800'
  content: A prtvacooive insight! Just what we need!
---
<p>一个用Python写的<a href="https://github.com/mescoda/pixivCrawler">Pixiv排行榜图片下载器</a>，基本上有了她以后，你就能明白为什么店长的新番扫雷总是一堆高质量的配图以及为什么有些死宅的桌面总是那么触及心灵。</p>
<p>原是好友NStal的点子，这家伙野心很大，除了实现功能以外还正在BeautifulSoup的基础上写一个类似jQuery的页面爬取器。我作为一个Python初心者，我还是安心发明轮子好了。</p>
<p>说明：</p>
<ol style="list-style-type:hiragana">
<li>当然你需要先有Python和wget。</li>
<li>然后下载<a href="http://www.crummy.com/software/BeautifulSoup/#Download">Beautiful Soup</a>，并将BeautifulSoup.py与pixivCrawler.py置于相同目录下。</li>
<li>默认的保存位置是Windows的D:\pixiv，可以在代码第4行修改，修改时请注意格式（类似F:\Pictures\pixiv，不要在最后加 \）。</li>
<li>运行后会在上面的文件夹内生成monthly、weekly、daily三个子文件夹以及这三个子文件夹内的以今天日期为名的子子文件夹，日期文件夹内为图片。</li>
<li>图片的命名规则是：排行数-画师id-图片id-该图片的pixiv域名号</li>
<li>如果是图集命名规则是：排行数-画师id-图片id_p图集内次序-该图片的pixiv域名号</li>
<li>这样的命名规则有助于找到原地址，即http://www.pixiv.net/member_illust.php?mode=medium&illust_id=图片id 和 http://img域名号.pixiv.net/img/画师id/图片id.格式</li>
<li>默认下载前一个月、前一周、昨天的全部排行前100，如果只想下前50，可以把最后的for循环改为range(1,2)，其他类推；如果只想下monthly，可以只保留for循环内的download('monthly',str(i))，其他类推。</li>
</ol>
<p>地址：<a href="https://github.com/mescoda/pixivCrawler">https://github.com/mescoda/pixivCrawler</a></p>
<p><a id="more"></a><a id="more-444"></a></p>
<p><a href="http://www.pixiv.net/member_illust.php?mode=medium&illust_id=22696418" title=""><img src="http://img01.pixiv.net/img/driftwood/22696418_p0.jpg" width="400" height="" alt=""></a></p>
<p><a href="http://www.pixiv.net/member_illust.php?mode=medium&illust_id=23253398" title=""><img src="http://img19.pixiv.net/img/shishio5431/23253398.jpg" width="500" height="" alt=""></a></p>
