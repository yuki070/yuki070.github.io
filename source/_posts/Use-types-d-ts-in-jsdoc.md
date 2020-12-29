---
title: 在js文件中使用jsdoc引用types.d.ts
date: 2020-12-29 16:47:09
tags:
- 前端
- jsdoc
---

## 类型定义

假设有文件@/util/types.d.ts，内容如下：
```typescript
/**
 * 命名空间
 */
export namespace ns {
  /**
   * 导出普通对象定义
   */
  export type User = {
    id: string
    age?: number
  }
 
  /**
   * 注册
   */
  export type register = (comp: IComponent) => void
 
  /**
   * 组件
   */
  export interface IComponent {
    /**
     * 名称
     */
    name: string
    /**
     * 类型
     */
    type?: number
    /**
     * 渲染函数
     */
    render: (data: number) => string
  }
 
  export interface IHoc extends IComponent {
    init: () => void
  }
}
```

## 应用类型

![使用普通对象的定义](1.png)

![使用函数的定义](2.png)

![使用继承后的类型](3.png)