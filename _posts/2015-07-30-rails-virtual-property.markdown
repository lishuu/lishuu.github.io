---
layout: post
title:  "Rails Model 中虚拟属性的使用"
date:   2015-07-30 10:57:45
categories: Rails
---

在用树形组件 [zTree](http://www.ztree.me/v3/main.php#_zTreeInfo) 来完成页面上 Treeview 的渲染，实现例如：单位的组织机构、市区县等有级联关系的数据显示。[zTree](http://www.ztree.me/v3/main.php#_zTreeInfo) 规定，节点“是否展开”取决于节点的属性 “*open*”，展开：open=true，不展开：open=false。

**OPEN** 这个属性完全是前端 render 的需要，基本上没有业务逻辑含义，也就没有必要作为一个物理列存储于数据表中。这里可以把 “*open*” 添加为 Model 的一个虚拟属性，这样我们就可以把 “*open*” 当做一般的属性来使用了。

例如：**Categery** 存储了类别信息，其中 **nodetype** 存储的类别类型（0,1,2,3,4...）,通过以下代码处理后，在 Controller 产生 Json 的代码中不需要做其他额外的处理

{% highlight ruby %}

class Category < ActiveRecord::Base
  has_ancestry   #用了 ancestry gem

  def open
    return [0,1,2].include?(nodetype) #类型为0,1,2三种的节点在页面显示的时候需要展开
  end

  def attributes   #合并虚拟属性
    super.merge({'open' => open})
  end
end

{% endhighlight %}