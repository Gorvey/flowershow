---
aliases: 
tags: 基础类型
scope: TypeScript
创建于: 2022-03-04 03:08
更新于: 2022-03-04 03:40
---

# Any

用于跳过类型检查器的检查

# 与[[Object]]相比

允许调用任意的方法。

```ts
let notSure: any = 4;
notSure.ifItExists(); // okay, ifItExists might exist at runtime 
notSure.toFixed(); // okay, toFixed exists (but the compiler doesn't check) 
let prettySure: Object = 4; 
prettySure.toFixed(); // Error: Property 'toFixed' doesn't exist on type 'Object'.
```

# 在数组中

只知道一部分数据时，any也有用

```ts
let list: any[] = [1, true, "free"]; 
list[1] = 100;
```
