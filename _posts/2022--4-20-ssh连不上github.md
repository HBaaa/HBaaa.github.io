---
layout:     post
title:      ssh连接github出错
subtitle:   权限拒绝-ssh错误-ssh-add
date:       2022-04-20
author:     周自横
header-img: img/post-220420.jpg
catalog: true
tags:
    - 问题解决
---

## ssh连接github出现权限问题

使用ssh创建密钥对之后，将公钥上传github，然后clone项目提示

~~~shell
git@github.com: Permission denied (publickey).
fatal: Could not read from remote repository.
~~~

出现这个原因在网上查找解决办法得到的大部分认为是公钥错误导致，我重新生成密钥对，上传发现该问题没有解决，然后使用命令`ssh -vT git@github.com`得到的提示是

~~~shell
debug1: identity file C:\\Users\\aaa/.ssh/id_rsa type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_rsa-cert type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_dsa type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_dsa-cert type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_ecdsa type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_ecdsa-cert type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_ed25519 type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_ed25519-cert type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_xmss type -1
debug1: identity file C:\\Users\\aaa/.ssh/id_xmss-cert type -1
~~~

对此，在github给出的故障排除中写的是

~~~
在该示例中，我们没有任何密钥供 SSH 使用。 "identity file" 行末的 "-1" 表示 SSH 找不到可使用的文件。 后面的 "Trying private key" 行也表示未找到文件。 如果文件存在，这些行将分别是 "1" 和 "Offering public key"：
~~~

所以使用`ssh-add path/to/key`添加密钥，因为只有默认密钥是自动添加到SSH身份验证中的，得到提示是

~~~shell
Could not open a connection to your authentication agent.
~~~

无法打开与身份验证的链接，这个是使用ssh问题，需要启动ssh代理程序，`ssh-agent bash`然后再执行。

最后发现完全按照github给出的问题解决步骤就可以。