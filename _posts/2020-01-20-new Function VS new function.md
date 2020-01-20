---
layout: post
title: new Function VS new function
# image: /img/abc.jpg
tags: [JavaScript]
---

#### 先说结论:

`new function`利用**匿名函数**作为构造函数, 创建了一个对象.

`new Function`利用`Function`作为构造函数, 创建了一个函数.

#### 来看例子:

利用**匿名函数**作为构造函数创建对象

```javascript
const obj = new function () {
    this.name = 'QiuJH'
    this.age = 26
    this.desrcibe = function () {
        return `name: ${this.name}, age: ${this.age}`
    }
}
```

利用`Function`作为构造函数创建函数

```javascript
const sum = new Function('a', 'b', 'return a + b')
console.log(sum(1, 2))
//expected output: 3
```

#### Tips:

```javascript
// 参数和函数体都为字符串
// 函数词法环境指向全局环境
// 使用场景: 需要从服务器获取代码或者动态地按模板编译函数
const fun = new Function([args,] FunBody])
```

