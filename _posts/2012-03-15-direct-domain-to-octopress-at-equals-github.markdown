---
layout: post
title: "将我的域名指向到github上的octopress"
date: 2012-03-15 17:58
comments: true
categories: 
- "Octopress"
---
经过了一周时间不断加班的摧残，今天终于有空来折腾octopress了。

想着将disqus换成友言的，希望更适合中文环境。将评论导入的过程比较麻烦，先是想在wordpress装上友言的插件，然后导出所有评论，以为这样可能会比较好导入。可是打开一看，日志的url不正确，不是我需要的那种。

换种方法，从之前导入好评论的disqus里导出，然后写代码生成友言格式的xml文件。使用dom4j，还蛮简单的，1个多小时搞定。

可惜导入成功后，无法与现有的日志进行匹配，自动化程序远不及disqus。

所以最后还是回归disqus，并且顺便把域名也指向github，以示今后就在octopress上折腾的决心。

### 记录一下将域名指向github的过程

需要在octopress的根目录里增加一个文件

`echo 'fancyoung.com' >> source/CNAME`

到godaddy上修改cname

`@ => odinyu.github.com`

并修改A

`@ => 207.97.227.245`

#### 今天游戏上线还算比较平稳，所以终于不用加班到很晚，抚额庆幸