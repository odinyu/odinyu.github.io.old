---
layout: post
title: "linux上自动重启tomcat的脚本"
date: 2013-01-21 10:15
comments: true
categories: work
---
这两天正在做的一个项目，tomcat老是会无故自己停掉，而且没有报错信息所以也无从修复。无奈之下，只能想是不是可以用定时脚本去监测tomcat是不是还在运行，然后重启tomcat。

经过网上搜索别人博客上贴出的脚本，根据自己服务的情况进行了一下修改，下面贴出脚本：

	echo ========================================
	date
	cd /root/script
	rm -f index.html
	wget -T 10 -t 3 -q http://127.0.0.1:8080/
	if [ ! -e index.html ]; then
	export JAVA_HOME=/usr/java/jdk1.6.0_38
	export CLASSPATH=.:$JAVA_HOME/lib/tools.jar
	export CATALINA_HOME=/usr/local/tomcat
	export PATH=$JAVA_HOME/bin:$PATH

	echo "restart tomcat."
	${CATALINA_HOME}/bin/shutdown.sh
	sleep 150
	kill -9 `ps aux|grep java|grep -v grep|awk '{print $2}'`
	sleep 5
	${CATALINA_HOME}/bin/startup.sh
	sleep 5
	else
	echo "checked."
	fi


经过本人的测试，应该是没什么问题，也总算是暂时解决了这个问题。