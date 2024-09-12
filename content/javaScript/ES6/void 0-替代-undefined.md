---
aliases: 
tags: 
scope:
创建于: 2022-02-17 02:41
更新于: 2022-02-17 02:47
---

# undefined不好的地方

[[undefined]]不是一个[[关键字与保留字|保留字]],只是全局对象的一个属性，在局部作用域中可能会被改写

# void关键字的作用

![[void#^3a755a]]

最重要的是void是[[关键字与保留字 | 关键字]],无法被重写，`void 0`可以生成干净的[[undefined]]，并且比[[undefined]]更短，许多压缩工具都使用`void 0`替代[[undefined]]

