---
title: Ice.js vs Umi.js
date: 2020-12-24 11:26:37
tags:
- 前端
- 脚手架
---

Ice.js和Umi.js都是优秀的React项目脚手架。之前一直使用的是Umi，现参照着Umi将它们进行一些简单的对比（基于目前的一些了解）。

当前版本
- `ice.js@1.12.2`
- `umi@3.2.28`

| 功能/项目 | Umi | Ice |
| ---- | ---- | ---- |
| Github Stars（截至目前） | 9.7k | 16k |
| Mock | ✔️ | ✔️ |
| 约定式路由  | ✔️ | ✔️ |
| 编码式路由  | ✔️ | ✔️ |
| 代码分割 | ✔️ | ✔️ |
| 单元测试 | ✔️ | ✔️ |
| VSCode插件 | ❌ | ✔️ |
| 日志打印 | ❌ | ✔️ |
| 权限管理 | ❌ | ✔️ |
| 状态管理 | ✔️ | ✔️ |
| 状态管理 - effects定义 | generator | async/await |
| 状态管理 - 使用方式 | connect | 创建store + 定义Provider + hooks(useXxx) |
| 状态管理 - model间交互 | 方便 | 一般。跨store的model无法通信 |
| 状态管理 - 路由变更 | subscription | ❌（替代：useHistory） |
| 配置 - build的静态资源输出 | ❌ | 可以配置输出的目录 |
| 默认组件库 | Ant Design | Fusion Design |
| 默认eslint | 适中 | 较弱（命令行中报的比较少。可以开启tsChecker，但会报.ice里的错误） |
| 文档 | 一般 | 完备 |