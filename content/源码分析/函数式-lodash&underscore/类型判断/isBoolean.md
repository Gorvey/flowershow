---
aliases: 
tags: 
- 类型判断
- 源码分析
scope: 函数式
创建于: 2022-03-11 11:36
更新于: 2022-03-11 11:52
---

# isBoolean

检查 `value` 是否是原始 boolean 类型或者对象。

```js
import isObjectLike from "./isObjectLike";
import getTag from "../.internal/getTag"; //#1
function isBoolean(value) {
 return (
 value === true ||
 value === false ||
 (isObjectLike(value) && getTag(value) === "[object Boolean]")
 );
}
export default isBoolean;
```

1. getTag是[[Object.prototype.toString | toString]]的别名
