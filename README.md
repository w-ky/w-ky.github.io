# 基本使用

1、git clone 拉取代码

2、jekyll serve 开启本地服务

> 注意：本地调试支持latex语法需要主题文件中添加mathwjax 脚本文件

1、查找本地主题文件夹位置 运行命令

`bundle show 主题名字`

2、在_cludes文件夹下head.html文件中添加如下脚本

```
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
      tex2jax: {
      skipTags: ['script', 'noscript', 'style', 'textarea', 'pre'],
      inlineMath: [['$','$']]
      }
  });
</script>
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
```
