---
layout:     post
title:      torchvison预训练模型位置修改
subtitle:   下载与加载位置固定为合适的位置
date:       2020-12-24
author:     周自横
header-img: img/post-201231.jpg
catalog: true
tags:
    - pytorch
---

在调用`torchvision.models`下面的预训练模型的时候，好比`resnet18`会直接开始从重新给你下载这个模型，下载位置是在当前用户文件夹的`.cache`文件夹下，这样会给下次使用造成使用的困扰，为了改变下载的位置，方便之后的使用，对其进行修改。

查看`resnet18`的定义位置，可以看到

![image-20201231152811858](https://raw.githubusercontent.com/HBaaa/saveImage/master/20201231152814.png)

调用的是`load_state_dict_from_url`，该函数来自于`utils`，查看可以看到很简单

![image-20201231152947452](https://raw.githubusercontent.com/HBaaa/saveImage/master/20201231152947.png)

调用的是`torch.hub`，转到定义查看这个函数，看到的是![image-20201231153111285](https://raw.githubusercontent.com/HBaaa/saveImage/master/20201231153111.png)

未修改的时候这里是`model_dir=None`，将其修改为你要存储的位置就可以。