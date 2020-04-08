---
layout:     post
title:      vs code运行jupyter notebook文件找不到环境
subtitle:   jupyter相关依赖库更新解决
date:       2020-04-07
author:     周自横
header-img: img/post-200407.jpg
catalog: true
tags:
    - 问题解决
    - python
---

## vs code无法运行juputer文件

​	可能之前还在用，重新打开之后就无法运行jupyter，会告诉你环境找不到，贴心的提示你`数据科学找不到这个xxxx环境，需要你安装`，但这这个环境你在`vs code`中运行`.py`文件,在浏览器中开启本地服务也可以运行.

​	解决的办法是将你该虚拟环境中的有关`jupyter`的所有库都进行更新.然后重启`vs code`就可以了.

