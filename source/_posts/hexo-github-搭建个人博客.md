---
title: hexo常用命令总结
date: 2017-12-08 12:01:56
tags: [hexo]
categories: Hexo
---
# HEXO命令总结
&emsp;&emsp;hexo是一个个人网站生成器，它基于node.js，可快速、简单、强大的生成静态博客框架。
hexo官网：[Hexo官网](https://hexo.io/zh-cn/)
1.hexo
------

```
npm install hexo -g #安装  
npm update hexo -g #升级  
hexo init #初始化

```

2.简写
----

```
hexo n "我的博客" == hexo new "我的博客" #新建文章
hexo p == hexo publish
hexo g == hexo generate#生成
hexo s == hexo server #启动服务预览
hexo d == hexo deploy#部署
```

3.服务器
-----

```
hexo server #Hexo 会监视文件变动并自动更新，您无须重启服务器。
hexo server -s #静态模式
hexo server -p 5000 #更改端口
hexo server -i 192.168.1.1 #自定义 IP

hexo clean #清除缓存 网页正常情况下可以忽略此条命令
hexo g #生成静态网页
hexo d #开始部署
```

```
$ hexo clean
清除缓存文件 (db.json) 和已生成的静态文件 (public)。
在某些情况（尤其是更换主题后），如果发现您对站点的更改无论如何也不生效，您可能需要运行该命令。
```

```
list
$ hexo list <type>
列出网站资料。
```

```
version
$ hexo version
显示 Hexo 版本。
```

4.监视文件变动
--------

```
hexo generate #使用 Hexo 生成静态文件快速而且简单
hexo generate --watch #监视文件变动
```

5.部署
----

```
两个命令的作用是相同的
hexo generate --deploy
hexo deploy --generate

hexo deploy -g
hexo server -g
```

6.草稿
----

```
hexo publish [layout] <title> ##发表草稿。
```

7.1模板
----

```
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #将.deploy目录部署到GitHub

hexo new [layout] <title>
hexo new photo "My Gallery"
hexo new "Hello World" --lang tw
```
变量     | 描述
-------- | ---
layout | 布局
title    | 标题
date     | 文件建立日期

```
title: 使用Hexo搭建个人博客
layout: post
date: 2014-03-03 19:07:43
comments: true
categories: Blog
tags: [Hexo]
keywords: Hexo, Blog
description: To be number one!
```

7.2模版（Scaffold）
---------------

```
hexo new photo "My Gallery"
```
变量     | 描述
-------- | ---
layout | 布局
title    | 标题
date     | 文件建立日期

8.设置文章摘要
--------

```
以上是文章摘要 <!--more--> 以下是余下全文
```

9.报错处理
----
<h3>**(1)找不到git部署**</h3>

> ERROR Deployer not found: git

```
#解决办法
npm install hexo-deployer-git --save
```

10.参数说明
-----

> (1)config.yml
 &emsp;&emsp;网站的 配置 信息，您可以在此配置大部分的参数。

&emsp;&emsp;
> (2)package.json:应用程序的信息。

```
package.json
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "hexo": {
    "version": ""
  },
  "dependencies": {
    "hexo": "^3.0.0",
    "hexo-generator-archive": "^0.1.0",
    "hexo-generator-category": "^0.1.0",
    "hexo-generator-index": "^0.1.0",
    "hexo-generator-tag": "^0.1.0",
    "hexo-renderer-ejs": "^0.1.0",
    "hexo-renderer-stylus": "^0.2.0",
    "hexo-renderer-marked": "^0.2.4",
    "hexo-server": "^0.1.2"
  }
}
```

> (3)scaffolds
&emsp;&emsp;模版 文件夹。当您新建文章时，Hexo 会根据 scaffold 来建立文件。

Hexo的模板是指在新建的markdown文件中默认填充的内容。例如，如果您修改scaffold/post.md中的Front-matter内容，那么每次新建一篇文章时都会包含这个修改。

> (4)source
&emsp;&emsp;资源文件夹是存放用户资源的地方。

&emsp;&emsp;
> (5)themes
&emsp;&emsp;主题文件夹。Hexo 会根据主题来生成静态页面。

