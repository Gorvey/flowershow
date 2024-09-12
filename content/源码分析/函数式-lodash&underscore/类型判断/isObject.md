---
aliases: 
tags: 
- 类型判断
- 源码分析
scope: 函数式
创建于: 2022-03-11 10:56
更新于: 2022-03-11 11:00
---

# isObject

 1. 使用[[typeof]]运算符操作
 2. type为object或function都算object,但要排除为[[null]]的情况

```js
function isObject(value) {
 const type = typeof value
 return value != null && (type === 'object' || type === 'function')
}
export default isObject
```

```js
//underscore
export default function isObject(obj) {
 var type = typeof obj;
 return type === 'function' || type === 'object' && !!obj;

}
```
