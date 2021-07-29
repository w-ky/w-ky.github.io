---
title: 简单实现forEach、filter等原生数组方法
cover: https://source.unsplash.com/random
---

> ###  forEach
```javascript
    let arr = [13,234,33,34];
    Array.prototype.myForEach = function(fn) {
        if(typeof fn!='function'){
            throw new TypeError('fn is not a function')
        }
        for(let i = 0,len = this.length; i < len; i ++) {
            fn(this[i],i,this);
        }
    }

    arr.myForEach((item,index,arr) => {
        console.log(item,index,arr);
    })
```
<!--more-->


