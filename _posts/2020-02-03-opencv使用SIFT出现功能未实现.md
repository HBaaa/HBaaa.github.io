---
layout:     post
title:      opencv实现SIFT出现错误
subtitle:   提示错误为功能未实现
date:       2020-02-03
author:     周自横
header-img: img/post-190701.png
catalog: true
tags:
    - 问题解决
    - python
---

## opencv实现SIFT 提示错误

​	opencv-contrib-python编译出现错误`The function/feature is not implemented`

​	解决方法是

1. 卸载之前的`opencv-python`和`opencv-contrib-python`

2. 安装指定版本为`3.4.2.16`版本的，两个都是。

