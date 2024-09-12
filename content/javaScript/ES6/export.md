---
aliases: [导出]
tags:
- 关键字
创建于: 2022-02-16 10:31
更新于: 2022-02-16 11:27
---
export 命令规定了[[模块]]对外的接口

export 除了可以输出变量，还可以输出函数和类
# 声明前导出
在声明之前放置export标记任意声明为导出
```js
export const PIE = 3.14
export let bar = '123'
```
# 与声明分开
先声明，再导出,与声明前导出等价
```js
function sayHi() {}
function sayBye() {}

export {sayHi, sayBye}
```
# 默认导出
在使用import时，必须知道要加载的变量或函数命名。为了方便使用者，使用`export default`命令为模块指定默认输出

`export default` 本质就是导出了一个名为`default`的变量，或方法。并且允许重命名 ^254b7e
```js
export default class User {

}
import User from './user.js' //#2

-------------------------------------
export default  [a,b,c] // #3
export [a,b,c] // Error

```
1. 每个模块只能有一个`export default`
2. import默认导出不需要花括号
3. 因为只能有一个默认导出，不用命名也是可以的


# 重新导出/Re-export
- 当前模块转发了`sayHi`和`User`，无法使用，因为没有被导入到当前模块
```js
export {sayHi} from './say.js' //重新导出 命名导出

export {default as User} from './user.js' //重新导出 default
```
# 重新导出默认导出
```js
// user.js
export default class User {

}
```
如果要重新导出上面的模块
```js
export User from './user.js' //会报Error
export * from './user.js' //只导出了命名导出，默认导出被忽略了
------------------------
//需要一起使用
export * from './user.js'; // 重新导出命名的导出 
export {default} from './user.js'; // 重新导出默认的导出
```