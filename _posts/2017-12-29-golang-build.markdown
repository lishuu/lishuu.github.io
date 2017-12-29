---
layout: post
title:  "Golang 交叉编译"
date:   2017-12-29 09:00:00
categories: golang
---

Golang 编译时候只需要指定两个参数：`GOOS` 和 `GOARCH` 即可。

## 示例

### 编译到 windows 64bit
```shell
# 编译到 windows 64bit
$ GOOS=windows GOARCH=amd64 go build

$ GOOS=windows GOARCH=amd64 go build -o appname.exe src/main.go
```

### 编译到 windows 32bit
```shell
# 编译到 windows 32bit
$ GOOS=windows GOARCH=386 go build

# 编译到 Mac OS X 64bit
$ GOOS=darwin GOARCH=amd64 go build
```


### 编译到 linux 64bit

```shell
$ GOOS=linux GOARCH=amd64 go build
# 或者可以使用 -o 选项指定生成二进制文件名字
$ GOOS=linux GOARCH=amd64 go build -o app.linux
```

### 编译到 linux 32bit
```shell
$ GOOS=linux GOARCH=386 go build
```

