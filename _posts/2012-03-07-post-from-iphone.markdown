---
layout: post
title: "从iphone上发布日志到octopress"
date: 2012-03-07 11:20
comments: true
categories: Octopress
tags: octopress,iphone
---
###昨天在被窝里的记录
在iphone上试了几个号称支持markdown并能同步到dropbox的应用，结果都不尽如人意，最后还是选择用evernote来进行移动终端的日志记录。
 
其实移动终端的记录有其一定的意义，比如我现在就是躺在被窝里单手写日志，准备明天公司里从evernote里复制到文本再发到线上博客。
 
感觉整个过程有点曲折，所以明天有必要去网上找一下能更方便的方法。
 
最好是能向iphone上的wordpress那样 ，写完直接发布就一切OK。

罗列一下明天需要做的一些事情

- 继续修改从wordpress迁移过来的日志
- 将本篇日志发出去
- 寻找更方便的移动日志发布手段 

###之后睡前的神奇发现
突然在google上看到有人说goodreader可以同步txt到dropbox，报着最后试一下不行就睡的想法试了一把，居然goodreader真的完成了这个本来是不可能完成的任务。

今天早上又重新启用了Belvedere这个小软件，用途是当dropbox内某文件夹有txt文件存在，就改后缀名为markdown，然后移动到octopress/source/_post文件夹内。目前这个功能已经测试成功，也就是说打开电脑后不多会就可直接使用命令来发布日志到octopress了，而无需手动复制内容。

接下来考虑通过执行脚本来发布文章，不过目前看来还是有点困难，因为本人不是很懂Ruby，这个需要慢慢研究了。不过至少移动端记录并同步到云端已经ok，已经减少了很多与写作无关的步骤，心情大好！