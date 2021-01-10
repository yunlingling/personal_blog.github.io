---
layout:     post
title:      ssh连接docker
subtitle:   docker ssh
date:       2020-12-10
author:     yunlingling
header-img: img/post-bg-ios9-web.jpg
catalog: true
tags:
    - docker
    - ssh
---

<h6>一、启动docker</h6>
```
docker run -dit -p <宿主机 port>:22 <docker images ID> bash
```
<h6>二、docker内部操作</h6>

1.更新apt-get <br>
```
apt-get update
```

2.安装openssh-server
```
apt-get install openssh-server
```

3.修改ssh配置
```
vim /etc/ssh/sshd_config
```

```
# PermitRootLogin prohibit-password # 默认打开 禁止root用户使用密码登陆，需要将其注释
RSAAuthentication yes #启用 RSA 认证
PubkeyAuthentication yes #启用公钥私钥配对认证方式
PermitRootLogin yes #允许root用户使用ssh登录
```

4.启动ssh服务
```
/etc/init.d/ssh restart
```



