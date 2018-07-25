---
layout: post
title:  "升级 golang & beego"
date:   2018-07-25 09:00:00
categories: golang
---

一早看到 [beego](https://beego.me/) 发布 stable 版本 1.10.0，于是考虑升级一下 golang 和 beego，主要有如下几个步骤：


### 1. 卸载当前系统 golang 1.8.3 
找到 golang 的安装目录 (`/usr/local/go`)，将 go 目录 Move to Trash

### 2. 获取最新稳定版 
[下载](https://golang.org/dl/) 最新的 golang 稳定版(1.10.3)，并直接默认路径安装

### 3. os x 终端走代理科学上网
```shell
export http_proxy=http://127.0.0.1:6152
export https_proxy=https://127.0.0.1:6152
# 测试一下是否成功
curl ip.cn
当前 IP：***.***.***.*** 来自：美国 xxxxx
# 成功!
```
### 4. 升级 beego 1.10.0

```shell
go get -u github.com/astaxie/beego
go get -u github.com/beego/bee
```
