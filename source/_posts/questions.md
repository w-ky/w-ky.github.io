---
title: 面试题汇总
cover: https://source.unsplash.com/random
---
..
<!--more-->
> #### 找出给定字符串中重复次数为多的字符，并输出次数
```javascript
    function findMaxLengthStr(str) {
        let strObj = {};
        for(let i = 0; i < str.length; i ++) {
          let charStr = str.charAt(i);
          if(strObj[charStr]) {
            strObj[charStr] ++;
          }else {
            strObj[charStr] = 1;
          }
        }
        let max = 0;
        for(let prop in strObj) {
          if(max < strObj[prop]) {
            max = strObj[prop];
          }
        }

        for(let key in strObj) {
          if(max == strObj[key]) {
            console.log('最大次数为：'+ max);
            console.log('最大的字符为：'+ key);
          }
        }
      }

      let str = 'ccbce';
      findMaxLengthStr(str);
```
> #### 网络状态码301、302的区别

官方的比较简洁的说明：
    301 redirect: 301 代表永久性转移(Permanently Moved)
    302 redirect: 302 代表暂时性转移(Temporarily Moved )
    ps:这里也顺带记住了两个比较相近的英语单词（permanently、temporarily），嘻哈！
    详细来说，301和302状态码都表示重定向，就是说浏览器在拿到服务器返回的这个状态码后会自动跳转到一个新的URL地址，这个地址可以从响应的Location首部中获取（用户看到的效果就是他输入的地址A瞬间变成了另一个地址B）——这是它们的共同点。他们的不同在于。301表示旧地址A的资源已经被永久地移除了（这个资源不可访问了），搜索引擎在抓取新内容的同时也将旧的网址交换为重定向之后的网址；302表示旧地址A的资源还在（仍然可以访问），这个重定向只是临时地从旧地址A跳转到地址B，搜索引擎会抓取新的内容而保存旧的网址。