---
layout: post
title:  "关于级联选择的问题"
date:   2015-10-22 12:23:30
categories: rails
---

>一个相对实现比优雅的基于 ajax 的级联选择 [Cascading selects](http://railsguides.net/cascading-selects-with-ajax-in-rails/)

#问题
* 源代码 clone 本地，虽然数据能正常保存，但是提交数据后，系统会报错
`
ArgumentError in EventsController#create
`

* 控制台显示如下信息

```shell
Completed 500 Internal Server Error in 13ms

ArgumentError (wrong number of arguments (2 for 1)):
  app/controllers/events_controller.rb:24:in `block (2 levels) in create'
  app/controllers/events_controller.rb:22:in `create'
```
#解决

经过一番折腾，原来是由于

* Gemfile 中包含的 Turbolinks 版本太低，要解决这个问题，只要升级 Turbolinks 为较新的版本即可

```shell
gem 'turbolinks', '~> 2.5.3'
```