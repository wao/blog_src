---
layout: post
title:  "nodeunit初学记"
date:   Mon, 24 Oct 2016 22:01:32 +0800
tags: nodejs
---

## Orginize Test Case

nodeunit没有suite的概念,但是有group的概念.就是说nodeunit exports可以包含一个对象,这个对象也会被认为是一个递归的测试集合.

~~~ javascript 
exports.anothertest = {
    test: function(test){
    ...
    }
}

exports.subtest = require('./subtest');
~~~

通过这个特性和require相结合就可以较好的组织测试.

## nodeunit缺省目录

`nodeunit`命令如果没有参数的话就会寻找test目录下的js文件自动执行

## Using npm test

在文件package.json的scripts中添加 "test" : "nodeunit" 即可

## nodeunit不立即退出的解决方法

nodeunit运行完全部测试后不会立即退出.根据[stackoverflow的这篇文章](http://stackoverflow.com/questions/25769825/is-there-a-way-to-know-that-nodeunit-has-finished-all-tests)可以添加一个最后执行的test来解决这个问题

~~~ javascript 
exports.anothertest = {
//Put a *LAST* test to clear all if needed:
exports.last_test = function(test){
    //do_clear_all_things_if_needed();
    setTimeout(process.exit, 500); // exit in 500 milli-seconds    
    test.done(); 
}
~~~

