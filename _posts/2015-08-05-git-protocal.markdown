---
layout: post
title:  "Git Protocal"
date:   2015-08-05 11:35:57
categories: git
---

>Thoughtbot 的 git 使用建议 [Git Protocol](https://github.com/thoughtbot/guides/tree/master/protocol/git)，理解如下


### 更好的维护一个代码库我们应该
* 代码库中要避免有本地开发设备和开发过程中特有的项目非依赖文件
* 对于功能分支，要在合并之后删除掉本地和远程分支
* 应该在功能分支上来进行开发
* 开发过程中应频繁和主分支进行同步
* 通过 pull resquest 完成代码审查

[这里](http://www.ruanyifeng.com/blog/2015/08/git-use-process.html)是阮一峰消化的总结，写的更生动一些。