---
layout: post
title: "从Wordpress迁移到Octopress"
date: 2012-03-06 14:54
comments: true
categories: Octopress
---
既然已经建了octopress，又把公司和家里的两台电脑的环境都配置好，那就没有理由不从Wordpress迁移到Octopress。通过网络上高手给出的脚本和指导，整个过程比较顺利，现记录之。

### 导出Wordpress里的内容

我用的是Wordpress导出的xml文件，而不是数据库的备份。

### 转换xml到md文档

使用高手给出的脚本,[下载](https://github.com/odinyu/odinyu.github.com/blob/source/md.rb "下载")。

重命名Wordpress导出的文件为wordpress.xml，然后放到`～/octopress/source/_post`下，再执行下面的代码

{% codeblock %}
cd octopress/source/_post
ruby md.rb wordpress.xml
{% endcodeblock %}

可能会提示少包，可以这样安装

`gem install ya2yaml`

注意，如果是windows环境下，hpricot这个包需要这样安装，不然会一直不成功

`gem install hpricot --platform=mswin32`

### 细节处理
脚本生成的是每篇wordpress上日志的md文档，未能完全按markdown语法格式化，还需要人工调整一下。另外就是原先的图片，如果是外链的还好，对于直接上传到wordpress上的需要修改一下路径。

当然，有些日志可能不再需要，适当的再进行一些清理工作。

### 记录很重要
虽然网络上需要的资讯一般都能找到，但是每次要用的时候再找总是很麻烦，记录在自己的手边才是王道！
