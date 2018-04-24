---
layout: post
title: "android开发环境上的小问题"
date: 2012-05-25 17:48
comments: true
categories: android
---
昨天休息了一天，今天打开eclipse然后顺手点开Android SDK Manager并升级了一下，结果就出问题了。

首先是eclipse提示我当前的ADT版本太低，需要升级到17或以上。貌似之前也遇到过这个问题，所以也有点准备。直接eclipse里install new software，然后add一个并从本地选择从网上下载回来的ADT升级压缩包，再一路安装。

本来以为安装成功后就没问题了，可是一运行虚拟机却又报了一个错。

	The connection to adb is down, and a severe error has occured

还好有万能的google，总算找来下面的两个命令，然后重启eclipse，搞定！

	adb kill-server
	adb start-server

自己记录一下，免得以后再找麻烦。