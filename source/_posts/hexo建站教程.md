---
title: hexo建站教程
tags:
  - 建站
abbrlink: 3417200a
date: 2022-03-03 23:36:02
---

一直想搭一个博客，奈何一直比较懒。这次历尽千辛万苦，终于将网站搭起来了，把心血历程记录在这儿

主要使用的方式是hexo+next+github。

**hexo**：一个基于nodeJS实现的博客框架。它的最大的作用就是能将 markdown文档自动转化成 html文档。markdown文档在格式上是比较友好的。

**next**：hexo里面一个非常流行的主题，比较美观。 

**github**：github page是一个静态网页平台。

主要流程就是，hexo把markdown文件转化为html文档，然后上传到GitHub，形成GitHub page。

## 安装hexo

* 首先安装[nodejs](https://nodejs.org/en/)，安装完成后输入`npm -v`，如果出现版本号，那说明安装成功了 

* 命令行安装hexo，如果是Windows，建议使用Git bash

```
# windows环境
npm install -g hexo-cli
# linux环境
npm install -g hexo
```

 接下来就可以用hexo来生成博客了，先创建一个文件夹，如myblog

```
cd myblog
hexo init
hexo generate
hexo server
```

执行完以后会提示访问 localhost:4000，就可以看到首页了

之后调试的时候会经常用到下面命令：

```
 hexo clean && hexo generate && hexo server 
```

如果是Windows的话，建议使用git bash，用alias设置一些[快捷操作](https://blog.csdn.net/weixin_39278265/article/details/120725973)，会方便很多。

## 安装next主题

next主题是一个比较美观流行的hexo主题，需要在博客根目录下，即myblog目录，执行以下命令：

```
git clone https://github.com/iissnan/hexo-theme-next themes/next
```

需要注意的是，next主题新版本和老版本仓库不一样，很多人建议使用新版本，因为新版本集成了很多新功能。

不过我觉得老版本的风格比较喜欢，这个看个人喜好了。

老版本：[iissnan](https://github.com/iissnan/hexo-theme-next) 最新版本是5.1.4，已经不维护了。

新版本：[theme-next](https://github.com/theme-next/hexo-theme-next)持续更新中。

## hexo next配置

主要参考以下文档：

[hexo next 主题优化](https://www.jianshu.com/p/9f0e90cc32c2)

## 关联github.io

需要建一个同名的仓库，然后在hexo配置文件里面进行设置，比如你的用户名叫 zhangsan，那仓库名就叫zhangsan.github.io，hexo关联github.io的方法参考网上教程

关联之后就可以部署了

当我们需要远程部署的时候，需要先安装*hexo-deployer-git*。

```
npm install hexo-deployer-git --save
```

安装好之后在博客目录配置文件*_config.yml*最后面添加deploy字段如下：

```
deploy:  
	type: git  
	repo: git@github.com:UserName/Blog.git  
	branch: master
```

然后执行

```
 hexo clean && hexo generate && hexo deploy 
```

就可以推送到远程仓库，等待一会儿访问zhangsan.github.io 就可以访问到了

## 关联域名

把zhangsan.github.io与域名关联起来，阿里云的域名一年只要一块钱，简直白嫖

## 遇到的一些问题

[Archieve 无法打开解决办法](https://blog.csdn.net/qq_44852901/article/details/122817214)

[Cannot GET /about/%20 解决办法](https://www.zhihu.com/question/353097489)

[目录无法跳转](https://www.cnblogs.com/Createsequence/p/14150758.html)