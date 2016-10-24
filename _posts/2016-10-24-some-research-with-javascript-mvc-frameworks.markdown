---
layout: post
title:  "关于javascript mvc framework的一些研究"
date:  Mon, 24 Oct 2016 21:26:33 +0800
tags: nodejs
---

## 关于javascript mvc framework的一些研究

### Twitter Bootstrap兼容

只有backbone可以完美兼容bootstrap,其他的ember.js, react.js都由于要操作dom会和bootstrap的jquery冲突.所以react.js和ember.js都有开源项目来复制bootstrap的功能.

长远来看,还是由bootstrap直接支持virtual dom才能彻底解决这个问题.

### Backbone dead?

backbone.js的社区已经不活跃了,本身backbone.js的也停止增加新功能了.

### Search Engine and Backbone.js

backbone.js对搜索引擎不友好,可能需要server side backbone.js来解决这个问题.
