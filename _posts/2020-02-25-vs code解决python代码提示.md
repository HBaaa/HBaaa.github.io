---
layout:     post
title:      vs code 中python代码提示
subtitle:   不需要插件，修改文件名即可
date:       2020-02-25
author:     周自横
header-img: img/post-200225.jpg
catalog: true
tags:
    - python
    - 问题解决
---

### 解决vs code代码没有补全提示

​	参照了[知乎中only回复中Atlas](https://www.zhihu.com/question/54395822)的办法，在`C:\Users\[用户名]\.vscode\extensions\ms-python.python-2020.2.64397\pythonFiles\lib\python\parso\python`下有文件`grammar3x.txt`，`3x`是python版本号，将对应的改为`3.x`就可以

