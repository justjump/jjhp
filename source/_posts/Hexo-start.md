---
title: Hexo 入门
date: 2016-06-08 14:57:11
categories: 经验
tags:
---
### 大概步骤:
1. 安装node.js

2. 从nmp里面安装hexo

3. 在一个目录里init hexo

4. 然后hexo server启动本地网址

5. 可以配置_config文件,设置博客的名称.以及上传地址等信息.

6. \#上传到github之前要配置ssh,不然权限不够(后来发现git里面配置过了也可以)

7. 以下建议在git bash里面进行
8. 在网站根目录里git init等等,然后直接运行hexo命令
9. 通过hexo new 新建文章(例如缩写 hexo n "hexo安装说明等")
10. $ hexo generate生成网站(缩写 hexo g)
11. $ hexo deploy同步上传到github(在bash里运行,提示nothing to commit, working directory clean,但是已经提交啦.)(缩写 hexo d)

也可以在第8步后通过git手动同步public文件夹,效果一样.

### 新建文章

1. 很简单,用`dexo n "文章标题"`命令 或者直接在source下面的_posts下面建立MD文件即可.


### 主题安装
1. 比如minos这个主题,安装方法:直接在根目录下git clone git@github.com .....
2. 这样子,会自动在theme文件夹下面装上主题.
3. 然后修改根目录下面的_config,改主题的名字,一般主题都有安装方法的,不算很难.

##### 主题的设置
1. 打开主题目录下面的config,把名字改了,改成_config.yml,然后里面基本一目了然

### 建立分类和单页
还不是很熟,我马上先测试一下.
貌似是这样子,但是我还不确定

```tex
编辑帖子的md文件的时候,
在第三行写上类似:
categories: jingyan
这样的话,会自动生成类似127.0.0.1/categories/jingyan的伪静态,打开后可以看到这篇文章.实际上没有jingyan这个目录存在.
jingyan这里也可以写中文,比如
categories: 经验

但是这样出现的问题是url里可能出现中文
可以在根目录config里面加一个categories的map映射
类似:
category_map:
  感想: ganxiang

```

```
然后另一个发现:_source\categories这个目录里有个index.md
这个文件是控制显示网站所有分类的.
但是不同的主题,有不同的做法.比如我用的minos这个主题
必须在index.md里面添加这行才可以显示所有分类:
layout: "categories"

当然主题作者建议是直接拷贝theme目录下_source里的categories目录到根目录
```

>   ![导航和分类设置](/images/1.png)
### 研究怎么插入图片

参考这里
http://blog.wleyuan.me/2015/07/18/Hexo-AddSoundPicMovie/

其实很简单,类似
```
![导航和分类设置](/images/1.png)
```
图片是放在根目录下的source/images下面的.

### 一些需要注意的地方

1. 配置文件要注意空格,编辑md文件的时候也必须注意空格,一个正确的头部如下:
    ```
---
title: Javascript判断手机客户端是安卓还是苹果..
date: 2016-06-08 11:56:42
categories: code
tags:
---
### 我来测试一下.
    ```
2. 貌似只有修改了根目录的config,才需要hexo g和hexo s,一般修改了帖子,直接刷新就显示了,非常方便.
3. 服务器的配置,在config里面添加
```
server:
  port: 666
  log: false
  ip: 127.0.0.1
  compress: false
  header: true

```

4. 注意帖子的md文件名,如果包含中文,那么最终生成的网址里也会有中文,不太好看貌似,最好不要.(补充:后来看了一下貌似也没什么不好,至少修改的时候很直观.)
5. 建立类别,tag等等,出现错误或者多余文件的话,可以用命令`hexo clean`清除后`hexo g`重建.