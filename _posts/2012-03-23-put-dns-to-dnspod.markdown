---
layout: post
title: "将DNS解析到dnspod上"
date: 2012-03-23 16:21
comments: true
categories: 
- "about blog"
---
昨天晚上无意间发现域名被墙，然后再一查，原来是godaddy又被墙了，害我也受牵连。

之前早就想过要把dns解析到dnspod上去，但一直懒得动，不过这次终于决定要动一下了。

## 具体过程

先注册dnspod，取得两个dns解析的地址

<img src="http://pcly6g.bay.livefilestore.com/y1pSOJncjLGuVLZuotvVKNqUy7tzyM3hQbdqdPOthwf4ZzI5js0yPdzAFQEG4Y5htV-1VAFEOCjXUk18qAMxF8Ba0l_hnlNgpHj/ScreenShot_2012-03-23_155217%201.jpg" width="300" alt="dns解析地址" orihref="http://public.bay.livefilestore.com/y1pcOWa97XSVygnCfwMVgwdhOwD4bNjkN99XXSJ2b61KNw5m-QssfQzwn6-36yiZOM_pXFvBIW2jhDRAv7km4HPiQ/ScreenShot_2012-03-23_155217.jpg"/>

到godaddy上改成新的地址

再到dnspod上添加A记录，如下图所示

<img src="http://pcly6g.bay.livefilestore.com/y1pLASrgBYeH_VTKqthvzWgFzMYPl-kI_-lA17TkUzU4BfvrF8MLwEREIEtUtuvtEoDqNq2-pCv41wm1ia31qu2Lda7HTuHE-s3/ScreenShot_2012-03-23_155253%201.jpg" width="300" alt="A记录" orihref="http://public.bay.livefilestore.com/y1pNkYMMZT7cFIalK-S7XPHqXAEJM90kiwhViGBK_NXsFusU9KD3IUDShCrcuZjQ85GR9sSTYhM5XDPLBtNLngJ8w/ScreenShot_2012-03-23_155253.jpg"/>

继续添加CNAME

<img src="http://pcly6g.bay.livefilestore.com/y1pSOJncjLGuVIho6E017E8r7qlLnOHJSdIYEkGbh3qcLLzeO0ljLaU0UeO1VYLRCVq49JGsKDJrMKfLb1Lsmh3KHU972V7xTKD/ScreenShot_2012-03-23_155305%201.jpg" width="300" alt="CNAME" orihref="http://public.bay.livefilestore.com/y1pWwvZbClwynCufLVnQqLB7TZjYjOLDFl2ufIWJ6kRL1PnmPvBj6oD4VKF99UuYA47uTjeicABw0vbrGDAakNRzA/ScreenShot_2012-03-23_155305.jpg"/>

好像过个10分钟左右，dns解析就会生效，感觉还不错。在天朝就要这样地折腾，唉！