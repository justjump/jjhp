---
title: Github pages绑定自己的域名
date: 2016-06-08 16:32:57
categories: 经验
tags:
---

#### 非常简单
在Github项目根目录建立文件CNAME(没有后缀)
文件内容:tucao8.vip
然后在域名管理的地方添加cname解析:justjump.github.io

就可以啦!!!!!散花.


### 呵呵呵
但是上面这么做有个问题.
每次hexo提交到github后这个文件就没有啦,这样就解析不到了.
所以正确做法:
在本地网站根目录下的source目录里建立这个CNAME文件,然后hexo g;hexo d提交到github,这样很明显是每次会在public下面生成cname文件,而上传到github的是public文件夹的内容,所以当然每次都包含,不怕丢失了.

## 好了现在可以撒花了.

感谢这篇文章:
[参考](http://www.jianshu.com/p/834d7cc0668d)

