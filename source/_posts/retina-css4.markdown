author: 阿安
comments: true
date: 2013-01-07 11:01:37+00:00
layout: post
slug: retina-css4
title: Retina屏幕与CSS4
wordpress_id: 699
categories:
- CSS
---

随着越来越多Retina技术的普及，越来越多的设备开始配置了Retina屏幕。w3c也在css4草案中加入了适配Retina屏幕的属性image-set，目前支持此属性的浏览器有chrome和safari。记得在今年冬天的webrebiuld交流会上，QQ的前端大湿曾经介绍过，并且在QQ.com的logo中用到了此属性。
在不支持image-set的浏览器：他会支持background-image图像，也就是说不支持image-set的浏览器下，他们解析background-image中的背景图像；
支持image-set的浏览器下：在普通显屏下，此时浏览器会选择image-set中的@1x背景图像，在Retina屏幕下，此时浏览器会选择image-set中的@2x背景图像。
写法：

    

    {
        background-image: url(default.png);
        background-image: -webkit-image-set(url(no-retina.png) 1x, url(retina.png) 2x);
    }


