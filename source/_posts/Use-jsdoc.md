---
title: 给复杂类型添加JSDoc
date: 2020-12-29 16:54:33
tags:
- 前端
- jsdoc
---

## 背景

有时候我们编写的方法，输入参数不是简单的字符串或数值，而是一个复杂的对象或对象数组。比如：

```js
const param = {
  config: {
    header: 'xxxx',
    body: 'yyyy',
    height: 100,
    width: 200,
  },
  data: [
    { dt: '20201105', type: 'static', sale: 1234 },
    { dt: '20201105', type: 'dynamic', sale: 56780 },
  ],
}
```

这种情况下，JSDoc可以如何写？

## 注释方式

### 纯JSDoc方式

![](1.png)

![提示效果](2.png)

### 使用types.d.ts

新增文件type.d.ts，使用typescript的语法进行类型定义，并导出。

```typescript
/** 输入参数 */
export interface Param {
  /** 配置参数 */
  config: ParamConfig
  /** 数据 */
  data: DataItem[]
}
 
interface ParamConfig {
  /** 头部信息 */
  header: string
  /** 内容信息 */
  body: string
  /** 高度 */
  height: number
  /** 宽度 */
  width: number
}
 
/** 数据项 */
interface DataItem {
  /** 日期 */
  dt: string
  /** 类型 */
  type: DataType
  /** 销售额 */
  sale: number
}
 
/** 数据类型 */
enum DataType {
  /** 静态 */
  static = 'static',
  /** 动态 */
  dynamic = 'dynamic',
}
```

![](3.png)

这种方式也可以引入第三方包的types定义。如：

![](4.png)

![](5.png)
