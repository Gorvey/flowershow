---
tags:
- 关键字
创建于: 2022-02-16 10:58
更新于: 2022-02-16 11:19
---
default[[关键字与保留字|关键字]]被用于引用默认的[[export#默认导出|导出]]
![[export#^254b7e|导出]]
```js

```

# 与定义分开
```js
function sayHi(){
	alert('hi')
}

export {sayHi as default}
```


# 模块同时有默认导出和命名导出
```js
export default function(obj) {}

export function each() {}

export { each as forEach }
```

```javascript
import _, { each, forEach } from 'lodash';
```

```javascript
import { * as lodash} from 'lodash';
let _ = lodash.default
let each = lodash.each
```

