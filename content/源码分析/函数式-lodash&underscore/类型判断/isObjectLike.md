---
aliases: 
tags: 
- 类型判断
- 源码分析
scope: 函数式
创建于: 2022-03-11 11:03
更新于: 2022-03-11 11:09
---

# isObjectLike

检查 `value` 是否是 类对象。 如果一个值是类对象，那么它不应该是 [[null]]，而且 `typeof` 后的结果是 "object"。

```js
function isObjectLike(value) {
 return typeof value === "object" && value !== null;
}
```
