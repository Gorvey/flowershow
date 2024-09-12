---
aliases: 
tags: 
- 类型判断
- 源码分析
scope: 函数式
创建于: 2022-03-11 11:09
更新于: 2022-03-11 11:27
---

# isPlainObject

检查 `value` 是否是普通对象。 也就是说该对象由 `Object` 构造函数创建，或者 `[[Prototype]]` 为 null 。

```js
function isPlainObject(value) {
 // #1
 if (!isObjectLike(value) || getTag(value) != "[object Object]") return false;
 // #2
 if (Object.getPrototypeOf(value) === null) {
 return true;
 }
 let proto = value;
 // #3
 while (Object.getPrototypeOf(proto) !== null) {
 proto = Object.getPrototypeOf(proto);
 }

 return Object.getPrototypeOf(value) === proto;

}
```

1. 首先判断value是否是对象
2. 如果value的上一级`[[Prototype]]`为null，直接返回true
3. 所有的对象的原型链最后都是null，而null前一级都是Object.prototype (特殊构造除外)
	1. 如果是普通对象，obj.prototype === Object.prototype
	2. 如果是构造函数生成的，例如Array
	3. [].prototype === Array.prototype
