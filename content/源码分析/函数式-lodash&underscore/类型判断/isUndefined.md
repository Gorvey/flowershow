---
aliases: 
tags: 
- 类型判断
- 源码分析
scope:
创建于: 2022-03-11 11:31
更新于: 2022-03-11 11:33
---

# isUndefined

检查 `value` 是否是 undefined

```js
 function isUndefined(obj) {
 return obj === void 0;
}
```
