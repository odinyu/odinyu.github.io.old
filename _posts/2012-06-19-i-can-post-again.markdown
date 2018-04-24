---
layout: post
title: "终于又可以更新博客了"
date: 2012-06-19 17:59
comments: true
categories: 
- "Octopress"
---
好久没有更新我的博客了，这次的主要原因可不是我又怎么犯懒，而是公司的电脑不争气地挂了，而后我更换了一台。

而新电脑需要重新搭建octopress所需要的环境，碰巧我的vpn也不怎么地不能用了，于是耽搁到今天。

今天终于有时间来搞octopress相关的环境，在终于成功之际还是要记录一下，以备今后再用到。

	gem sources --remove http://rubygems.org/ 
	gem sources -a http://ruby.taobao.org/
	gem sources -l
	gem install bundler --pre

安装完之后，修改octopress路径下gemfile的Rubygems镜像，同样是改成http://ruby.taobao.org/。

	bundle install
	rake install
