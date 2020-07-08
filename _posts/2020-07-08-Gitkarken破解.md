---
layout:     post
title:      Gittkarken破解
subtitle:   使用pro功能
date:       2020-07-08
author:     周自横
header-img: img/post-200708.jpg
catalog: true
tags:
    - 问题解决
---

## Gitkarken在6.50之后的破解使用Pro版本

### 环境配置

需要安装`node.js`和`yarn`，其中`node.js`安装时要选择加入系统环境中，`yarn`在安装后也要手动进行添加进系统环境。

### 下载破解脚本并破解

~~~cmd
git clone https://github.com/5cr1pt/GitCracken.git
~~~

破解

~~~cmd
cd GitCracken/GitCracken
rm yarn.lock
yarn install
yarn build
# 最后一个参数是此程序安装位置下的一个文件
node dist/bin/gitcracken.js patcher --asar ~/AppData/Local/gitkraken/app-6.5.0/resources/app.asar
~~~

### 破解中遇到的问题

1. 破解最后一步使用的文件参数，若是失败的话改为自己文件的绝对位置

2. 安装`node.js`和`yarn`之后重启，使用`yarn --version`验证是否能够使用

3. 成功破解之后，是在`app.asar`做的修改，若是你之前打开了程序并且登录了`Github`其中保留的有你的信息，所以若是更换账户需要重新破解一次

4. 我在最后一步破解之后，打开一直卡在启动界面上，我把`app.asar`拷贝出来重新安装了一遍，然后替换文件`app.asar`重新打开，在右下角看到`Pro`提示，若是显示是`Free`直接点击应该会变换。

   ![image-20200708163041909](https://raw.githubusercontent.com/HBaaa/saveImage/master/20200708163042.png)
   
5.  在当前（2020.07.8）使用的7.0.1版本仍是可以破解的，但是为了之后保持能用最好不要更新。由于系统图标指向的是`Update.exe`程序，可在快捷方式中进行修改指向程序的真正位置。另外在`hosts`中加入`127.0.0.1 release.gitkraken.com`屏蔽更新。关于此程序的右键功能，在知乎有看大佬提到说需要修改注册表，我是直接将其关闭了

