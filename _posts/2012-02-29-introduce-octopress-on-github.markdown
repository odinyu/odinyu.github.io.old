---
layout: post
title: "在github上用octopress搭建博客过程纪要"
date: 2012-02-29 01:25
comments: true
categories: octopress
---

几个小时之前刚在github pages上使用octopress搭建了一个博客副本。本来基于本人一贯拖延的作风，是想过几天再记录整个过程的，但是正好在通宵工作但又暂时无事可干中，所以还是趁记忆还比较清晰的时候来搞定它。

在开始写过程之前先要交待一下我为什么要去做这件事，又或者说是这么做有什么好处：

- 首先这么做需要那么一点点伪技术，所以看上去就会比较geek一点。
- 其次这整个服务的搭建是完全免费的，可能对于比较穷困的专业挨踢的我来说会是一个开源节流的渠道。
- 然后用octopress来写博客，最后发布的动作很cool。
{% codeblock 个人感觉很帅气 %}
rake generate
rake preview
rake deploy
{% endcodeblock %}
- 最后则是离线写博客很舒服，拥有纯文本markdown，良好的html支持，不使用数据库，完美的版本控制，静态页面生成等诸多优点。

好了，现在开始整个服务搭建过程记录，可能比较长：

### 安装Git并进行配置
- 先注册一个github账号。
- 下载并安装Git。
- 到Git的安装目录找到Git Bash.lnk并打开。
- 执行`ssh-keygen -t rsa -C "your_email@youremail.com"`，回车。
- 然后输入两遍密码。
- 到c:\Users\用户名\.ssh\目录找到id_rsa.pub，并用文本软件打开复制全部。
- 到github网站选择“Account Settings”>>“SSH Public Keys”>>“Add another public key”，将刚才复制的内容粘贴到key文本框内。

### 建立github pages
- 创建一个新的Repository。这里需要注意的是，如果想要博客的首页是http://yourname.github.com，则Repository的project name就必须是yourname.github.com。
- 根据github给出的指导进行一些命令的键入，即可完成pages的建立。

### 安装Ruby

- 这里要指出一点的是，因为我是在windows里安装，所以采用了[RubyInstaller](http://rubyinstaller.org/)的方式，下载这个软件需要翻墙。
- 另外别忘记在同一个网站上下载[DevKit](http://rubyinstaller.org/add-ons/devkit/)，必须安装。

### 安装octopress
- 获取octopress，执行`git clone git://github.com/imathis/octopress.git myblog`。
- gem install bundler（记得翻墙）
- bundle install（还是要翻墙）
- rake install

到了这一步基本上可以开始写日志了，不过这里要给出两个小的tips。

### 修改配置
- 将octopress的目录内的_config.yml的编码改成UTF-8。
- 到Ruby的安装目录\lib\ruby\gems\1.9.1\gems\jekyll-0.11.0\lib\jekyll\找到convertible.rb这个文件，修改`self.content = File.read(File.join(base, name))`为`self.content = File.read(File.join(base, name), :encoding => "utf-8")`。
- 修改配置文件_config.yml，修改url、title、subtitle、author等等。

### 总算到了激动人心的一步了，开始写日志
- 执行`rake new_post["my first blog"]`，这样会在octopress的/source/_post下生成一个markdown文件，可以用文本软件进行编辑
- 完成编辑后执行`rake generate`，生成。
- 执行`rake preview`地，可以在浏览器内以[这个地址](http://127.0.0.1:4000)进行预览。
- 最后执行`rake deploy`，将日志提交到github上，完美收工！

### 补充一点
最后的但并不最不重要的，我们需要将修改的日志同步到github上，因此下面的3个命令也是必须的。
{% codeblock %}
git add .
git commit -m 'your message'
git push origin source
{% endcodeblock %}

















