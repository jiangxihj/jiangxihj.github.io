---
layout: post
title: "ubuntu下jekyll安装"
description: "google得到的大部分文章已经过时，有必要写一篇科普下最新的jekyll安装方法"
category: "jekyll"
tags: [jekyll, 安装]
---

Jekyll是一个简洁的、特别针对博客平台的静态网站生成器。它是[GitHub Pages](https://pages.github.com/),也就是本博客使用的服务，在后台所运行的引擎。

其实使用github page的服务并不需要在本地安装Jekyll，写好的文档就像程序文件一样commit到repositorty中就可以自动更新。但是，如果博客文件中有错误或者笔误，你就需要多次上传并刷新网站才可以看到文章的显示效果。Jekyll的作用就是让你在本地预览整个博客，在确定没有错误以后再把完整版上传到给git目录下，无疑会大大提高效率。下面就来介绍它在ubuntu中的安装方法：

其实Jekyll官网上有完整的安装指导，可是我之前没有看到，google了一堆教程,发现都已经过时或有错误，所以把最新的方法写到这里，避免后来人走弯路。

1. 安装[ruby](https://www.ruby-lang.org/en/downloads/)

	大家可能会想到采用apt-get的方法安装：

	> sudo apt-get install ruby

	但这是一个大坑，默认安装的ruby版本只有1.8.7。而Jekyll要求ruby的最低版本是1.9.3,正确的做法是先安装[RVM](http://rvm.io/)
	安装RVM的时候需要用到curl，所以先安装curl：

	> sudo apt-get install curl

	安装完成后，使用curl下载RVM：

	> \curl -sSL https://get.rvm.io | bash -s stable

	RVM安装完成后，利用RVM安装新版本的ruby:

	> rvm install 2.0.0

	安装好以后，查看ruby版本：

	> ruby --version

	在1.9.3以上即可


2. 安装[rubygems](http://rubygems.org/pages/download)

	直接用apt-get即可

	> sudo apt-get install rubygems


3. 安装[NodeJS](http://nodejs.org/)或其他JavaScript runtime

	推荐装nodejs(可选[therubyracer](https://rubygems.org/gems/therubyracer)),直接用apt-get

	> sudo apt-get install nodejs


4. 安装[Jekyll](jekyllrb.com/)

	> gem install jekyll


5. 启动Jehyll服务

	在博客文件夹中启动终端，输入

	> jekyll serve

	就可以启动服务，在浏览器中输入0.0.0.0:4000就可以预览到网站的全部内容

----
#### 参考链接

* [Jekyll安装官方指导](http://jekyllrb.com/docs/installation/)
* [先装RVM再安装ruby和rubygems](http://g2ex.blogspot.com/2013/12/Setup-Jekyll-Environment-on-Linux.html)