---
layout:     post
title:      torchvision中pillow出错
subtitle:   pillow版本更新引起问题
date:       2020-04-08
author:     周自横
header-img: img/post-200408.jpg
catalog: true
tags:
    - python
    - 问题解决
---

## cannot import name 'PILLOW_VERSION' from 'PIL'问题解决

​	在`torch=1.1,torchvision=0.3`中更新了`pillow`库到7.0版本之后,遇到了这个问题,在[官方的版本介绍里面可以看到](https://pillow.readthedocs.io/en/stable/releasenotes/7.0.0.html#pillow-version-constant),说这个已经被移除了改了新名字.![](https://raw.githubusercontent.com/HBaaa/saveImage/master/20200408202722.png)

​	所以解决方式是重新安装并指定`pillow=6.1`即可解决.在`colab`中我运行程序没有遇到该问题,所以在`torch=1.4,torchvision=0.5`下使用`pillow=7.0`应该也是可以的

