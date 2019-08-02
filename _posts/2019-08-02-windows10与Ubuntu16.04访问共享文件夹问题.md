---
layout:     post
title:      Ubuntu访问windows10共享文件
subtitle:   smba协议不同造成的无法访问
date:       2019-08-02
author:     周自横
header-img: img/post-190701.png
catalog: true
tags:
    - 小技巧
    - Ubuntu
---

## Ubuntu16访问Windows10共享文件夹

### 更改协议

WIndows10使用的SMB2协议，领先Ubuntu的协议，所以Ubuntu在访问的时候一直连接不上

1. 更改Ubuntu使它支持，在`/etc/smba/smb.conf`文件中添加内容，可以在网上搜到，但是我试了没有效果不知道是哪里的问题
2. 使Windows支持低版本协议，控制面板-程序-程序与功能-启用或关闭windows功能，里边有SMB1.0这一项选中就行，需要重启

### 连接

Ubuntu在连上之后会让你进行登录，之前其他类型的我使用微软账户也能连，但是这次不行，必须是你的用户名，也就是users下你的用户名