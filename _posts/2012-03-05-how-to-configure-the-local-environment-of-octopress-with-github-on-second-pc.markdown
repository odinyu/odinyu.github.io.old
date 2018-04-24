---
layout: post
title: "在第二台电脑上配置github octopress的本地环境"
date: 2012-03-05 23:18
comments: true
categories: Octopress
---
本来倒是没想在家里的本本上也进行配置，不过一颗geek的心却始终骚动着，最终还是google了出来具体的方法，当然也是综合了多方建议，所以有必要在还没有忘记之时记录一下。

###安装Ruby
- 还是通过[http://rubyinstaller.org/](http://rubyinstaller.org/ "RubyInstraller")的方式，不过好像我在家却不用翻墙居然也能下，上天有眼？
- 同样还是不要忘记安装[http://rubyinstaller.org/add-ons/devkit/](http://rubyinstaller.org/add-ons/devkit/ "Devkit").

###从github上获取自己的octopress内容
{% codeblock 从github上获取自己的octopress内容 %}
git clone -b source git@github.com:username/username.github.com.git octopress
cd octopress
git clone git@github.com:username/username.github.com.git _deploy
{% endcodeblock %}

###安装依赖gems
{% codeblock 安装依赖gems %}
gem install bundler --pre 
bundle install
rake install
{% endcodeblock %}

这里在我具体安装的时候有点小曲折，不过都还是用google解决了。

- `gem install bundler`可能会比较慢，所以改用`gem install bundler --pre`
- `rake install`的时候报错，好像是说我用的gem版本太新什么的，google后的解决方法是`bundle update`，然后再`rake install`。

###修改配置
- 到Ruby的安装目录\lib\ruby\gems\1.9.1\gems\jekyll-0.11.0\lib\jekyll\找到convertible.rb这个文件，修改`self.content = File.read(File.join(base, name))`为`self.content = File.read(File.join(base, name), :encoding => "utf-8")`。

###从github上更新source内容的命令
{% codeblock 从github上更新source内容的命令 %}
cd _deploy
git pull origin master
cd ..
git pull origin source
{% endcodeblock %}

至此大功告成！总耗时1小时左右，还算顺利。

###另外补充一下windows下安装Devkit的方法，免得下次还要找。
{% codeblock windows下安装Devkit的方法 %}
cd <DEVKIT_INSTALL_DIR>
ruby dk.rb init
ruby dk.rb install
#检验是否成功
gem install rdiscount --platform=ruby
{% endcodeblock %}




