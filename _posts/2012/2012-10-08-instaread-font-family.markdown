---
layout: post
status: publish
published: true
title: Instaread 的中文字体选择
author:
  display_name: mescoda
  login: mescoda
  email: mescodasun@gmail.com
  url: ''
author_login: mescoda
author_email: mescodasun@gmail.com
excerpt: "最近在做的 Instaread 是个在线阅读风格的东西。\r\n\r\n[caption id=\"\" align=\"alignnone\"
  width=\"500\" caption=\"Instaread\"]<a href=\"http://lh4.googleusercontent.com/-PDj1SHCcEvQ/UHLIc_R2ntI/AAAAAAAAAU4/7mMArhgNHs0/s912/Instaread.png\"
  title=\"\"><img src=\"http://lh4.googleusercontent.com/-PDj1SHCcEvQ/UHLIc_R2ntI/AAAAAAAAAU4/7mMArhgNHs0/s912/Instaread.png\"
  width=\"500\" alt=\"\"></a>[/caption]\r\n\r\nInstaread 的正文文字 CSS 是这样的：\r\n\r\n<pre><code>\r\ncolor:
  #333;\r\nfont: 18px/1.7 \"Helvetica Neue\",Helvetica,Arial,\"Hiragino Sans GB\",\"WenQuanYi
  Micro Hei\",\"Microsoft YaHei\",sans-serif;\r\nletter-spacing: 0.5px;\r\ntext-align:
  justify;\r\nword-wrap: break-word;\r\n\r\n</code></pre>\r\n\r\n此外还提供了宋 / 黑体转换，简
  / 繁转换和夜晚阅读模式的键盘快捷键。\r\n\r\n"
wordpress_id: 585
wordpress_url: http://mescoda.com/?p=585
date: '2012-10-08 21:10:38 +0800'
date_gmt: '2012-10-08 13:10:38 +0800'
categories:
- "稀烂的技术"
tags:
- Instaread
comments:
- id: 2221
  author: Jialu
  author_email: jialuli0508@gmail.com
  author_url: ''
  date: '2012-12-07 14:49:27 +0800'
  date_gmt: '2012-12-07 06:49:27 +0800'
  content: "虽然完全没有看懂你在写什么，但是感觉几年不见你已经牛哄哄的了。今天清邮箱的时候偶然发现了我刚来美国的时候在你blog里面的留下脚印的邮件，进而点了进来，两年多就这么默默的过去了，感觉大家都成长了好多，感觉自己还有点原地踏步。"
- id: 2223
  author: Mescoda
  author_email: mescodasun@gmail.com
  author_url: http://mescoda.com/
  date: '2012-12-07 16:21:51 +0800'
  date_gmt: '2012-12-07 08:21:51 +0800'
  content: "@Jialu\r\n人肉翻墙什么的直接完爆我们这些好吧，接着好好读完商科然后拿个投行 offer，然后 H1B，然后绿卡。。"
- id: 2275
  author: Jialu
  author_email: jialuli0508@gmail.com
  author_url: ''
  date: '2012-12-12 11:07:14 +0800'
  date_gmt: '2012-12-12 03:07:14 +0800'
  content: "谈何容易啊..."
---
<p>最近在做的 Instaread 是个在线阅读风格的东西。</p>
<p><a href="http://lh4.googleusercontent.com/-PDj1SHCcEvQ/UHLIc_R2ntI/AAAAAAAAAU4/7mMArhgNHs0/s912/Instaread.png" title=""><img src="http://lh4.googleusercontent.com/-PDj1SHCcEvQ/UHLIc_R2ntI/AAAAAAAAAU4/7mMArhgNHs0/s912/Instaread.png" width="500" alt=""></a></p>
<p>Instaread 的正文文字 CSS 是这样的：</p>
<pre><code>
color: #333;
font: 18px/1.7 "Helvetica Neue",Helvetica,Arial,"Hiragino Sans GB","WenQuanYi Micro Hei","Microsoft YaHei",sans-serif;
letter-spacing: 0.5px;
text-align: justify;
word-wrap: break-word;

</code></pre>
<p>此外还提供了宋 / 黑体转换，简 / 繁转换和夜晚阅读模式的键盘快捷键。</p>
<p><a id="more"></a><a id="more-585"></a></p>
<p>以前看过很多理论资料说衬线比非衬线字体在阅读上效果更好，因为衬线本身可以使字体的特征更加突出，有时候即使文字的上 / 下部分模糊，仍然可以被识别。我个人在阅读长篇英文上的经验也告诉自己：“大段文字的阅读还是用衬线保险，Helvetica 这种一眼看上去棒极了，逐字读的时候就不一定好了”。</p>
<p>但是除了字体上的衬线和非衬线以外，阅读体验还与颜色、字号、行距、PPI、排版、屏幕种类、分辨率、系统渲染等其他许多因素有关。而且汉字区别与使用罗马字母的印欧语系，仅仅使用衬线和非衬线作为区分是简单甚至有些不负责任的（Windows 下其实也没有实际上的衬线中文简体，所谓的中易宋体只是点阵字体而已）。 根据自己在 Windows 和 Linux 下的实际体验，Instaread 默认采用大字号的黑体系列，同时也为看惯了 Windows 下中易宋体的同学提供了切换工具。</p>
<p>中易宋体（SimSun，就是 font-family 设为<span class="inlinecode">宋体</span> 或 <span class="inlinecode">\5b8b\4f53</span> 或 <span class="inlinecode">simsun</span> 时 Windows 对应的字体）是 Windows 下长久以来唯一能作为正文阅读的字体，它的一个特点是在 18px 以下是点阵，18px 及以上是轮廓，只有 18px 及以上的中易宋体才能触发 Windows 的 Cleartype，渲染为亚像素的平滑状态，尽量还原衬线字体的风格，不然大字号的中易宋体根本没法看。（ XP 默认没有开启 Cleartype，对于 Windows 用户来说，想要字体上的更好体验除了装 Mactype 之外其实就是开启 Cleartype 了）</p>
<p>简中黑体系列在各平台都有不同的字体：</p>
<p>Windows：Microsoft YaHei（微软雅黑）。是微软从 Vista 开始以 100刀 / 字的价格做了针对 ClearType 的 hinting 开发出来的字体。算是 Windows 下最好的简体字体了，也是 Instaread 的 Windows 默认字体。但是大段文字的排版下很有压迫感，需要增加字符间距。</p>
<p>Mac：从 OS X 10.6 开始携带了 Hiragino Sans GB（冬青黑体简体中文）。此外还有 STXihei（华文细黑）、STHeiti（华文黑体）和据说质量很差的 Hei。冬青黑体是是大日本 Screen 和北京汉仪合作开发的简体中文字体，衍生于日文字体 Hiragino Kaku Gothic 。比之前 Mac 下默认的华文黑体系列好很多，据说也是目前最好的简体中文字体 。10.6 之前一些果粉网页的 font-family 甚至会指定用 Hiragino Kaku Gothic Pro 或者 Hiragino Kaku Gothic 这些日文字体（尽管简体字不全，且汉字是日本标准）来提升体验。</p>
<p>Linux：WenQuanYi Zen Hei（文泉驿正黑）和 WenQuanYi Micro Hei（文泉驿微米黑）。均缘起于<a href="http://www.wenq.org/">文泉驿项目</a>，文泉驿微米黑据说是 Linux 下最好的简体中文字体。</p>
<p>以上是考虑兼容性的廉价解决方案，土豪们可以直接去<a href="http://www.justfont.com/">justfont</a>买信黑体用。</p>
<p>字体之外，颜色上使用了 #333，相对 #000 更加柔和。</p>
<p>字号上继承了我的大号趣味，也保证在中易宋体模式下触发轮廓字体还原衬线风格。</p>
