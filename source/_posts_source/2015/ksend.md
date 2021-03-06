title: 命令行推送个人文档至kindle
author: 阿安
comments: true
layout: post
slug: ksend
categories: [javascript]
tags : [ksend, kindle]
date: 2015-01-03 13:24:00+00:00
---

昨天同事发了一本pdf格式的电子书，以往的方式，我都是登陆自己的qq邮箱，然后发pdf作为附件，推送到自己的kindle接收邮箱上。
突然觉得，其实nodejs应该有这样的命令行工具，可以一条命令搞定，于是在npm上搜索了一下，果然有一个叫“kindle”的包。
但是安装以后，总是推送失败，大概开了下源码，估计是作者使用的nodemailer组件做了不兼容升级导致。

于是，为了以后传文件到kindle时偷个懒，就自己动手写了一个命令行工具，名叫ksend（ <a href="https://github.com/hanan198501/ksend" target="_blank">https://github.com/hanan198501/ksend</a> ），简单好用。 O(∩_∩)O~


**使用指南**

1. 安装

        npm install ksend -g

2. 设置默认发送邮箱，格式: 邮箱地址:密码

        ksend --from yourname@qq.com:yourpassword

3. 推送，如下示例，推送 a.pdf 至 hanan@kindle.cn 这个kindle接收邮箱：

        ksend -m hanan@kindle.cn a.pdf

    以上命令，参数 -m 表示接收邮箱。自此，完成推送。

如果脚得每次都要敲 -m 接收邮箱 麻烦，可以设置默认接收邮箱：

    ksend --to hanan@kindle.cn

这样，以后只需要如下命令即可推送：

    ksend a.pdf

也可以同时推送多个文档：

    ksend a.pdf b.pdf ../img/photo.jpg /Users/hanan/book/ooxx.txt

查看帮助：

    ksend --help

ps: 记得把发送邮箱添加到您的kindle已认可的发件人电子邮箱列表哦。