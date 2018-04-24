---
layout: post
title: "用mklink把octopress直接放到dropbox同步文件夹内"
date: 2012-03-19 15:53
comments: true
categories: 
- "Octopress"
---
之前准备把博客迁移到octopress在google上找参考的时候，就看到有人说将octopress直接放到dropbox同步文件夹里，这样方便在多个环境内修改日志，而避免用git去pull再push的麻烦。不过那么大神没有给出解决文案，不过至少也给了一个好的思路。

很久以前曾经看到过dropbox的使用技巧里如何将多个文件夹都能同步，在win7环境下使用mklink就能解决。然后我再次上google进行了一番查询，下面给出我自己所使用的代码。

--------

	mklink /d "d:\Program Files\Git\octopress\" d:\dropbox\Dropbox\octopress\

这里需要注意三点：

- 双引号只是针对windows系统下带空格的文件夹，不加双引号会报错
- 双引号内的octopress文件夹必须是不存在的
- dropbox内的octopress文件夹需要先建立好

### 后记
今天突然发现两个也用octopress的博客的主题和我用的是一样的，这个让人感觉有点郁闷，就像开开心心地穿了件新衣服出去却发现满街都是和你穿得一样的人那种感觉。

所以，等有空的时候必须要改一下主题，虽然我并不擅长css。

