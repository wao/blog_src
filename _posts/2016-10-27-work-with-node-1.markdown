---
layout: post
title:  "Node经验记录1"
date:  Thu, 27 Oct 2016 22:30:16 +0800
tags: nodejs
---

## 使用browserify来打包client端js

* 使用 browserify 的 `-d` 选项生成source map,有助于调试
* 使用 watchify 来自动调用browserify, 具体命令为 `watchify -d -o target.js source.js`
* 使用 express的middleware browserify-middleware 动态自动打包js
* 根据[这篇文章](http://stackoverflow.com/questions/24827964/browserify-with-twitter-bootstrap)与bootstrap兼容的jquery打包方法是

~~~ javascript
    window.$ = window.jQuery = require('jquery');
~~~

## backbone

* collection的任意一个子model.save()都会激发collection的sync事件 
* model.save()会出PUT请求,同时要求返回更新后model的json
* BackboneView在切换parent()以后,event绑定会丢失,可以用`this.delegateEvents()`重新绑定事件.参见[这篇文章](http://blog.marionettejs.com/2015/02/12/understanding-the-event-hash/index.html)

## express 

* res.json()用于发送json
* req.params.xxx 用于获取参数
* req.body用于获取传入的值


