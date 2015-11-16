---
layout: post
title:  "OS X ssh 登录阿里云CentOS关于locale的警告处理"
date:   2015-10-22 12:23:30
categories: Mac,CentOS,Aliyun
---
> 公司开始使用[钉钉](http://www.dingtalk.com/)作为工作中的IM，企业认证后购买阿里云有个五折码用，于是就采购了一个CentOS作为新产品的部署环境。

# Q

 Mac iTerm ssh 到服务器，输入密码成功登录后，终端出现如下提示：

```shell
warning: setlocale: LC_CTYPE: cannot change locale (UTF-8): No such file or directory
```
# A

通过修改 ssh_config 文件就可以解决

### step 1

```shell
sudo vi /etc/ssh/ssh_config
```

### step 2

```shell
#   SendEnv LANG LC_*
```
