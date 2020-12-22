---
title: Hexo configuration
comments: true
date: 2020-12-22 11:09:15
updated: 2020-12-22 11:09:15
categories:
- 学习
tags:
- Hexo
---

## 如何替换landscape的banner

### 方法1

Hexo默认内置了landscape主题，如需要修改主题的默认设置，则需要先在themes目录下获取该主题的配置，然后修改其`_config.yml`。

```bash
cd themes

git clone --depth 1 https://github.com/hexojs/hexo-theme-landscape landscape

# 进入themes/landscape
cd landscape
```

打开`_config.yml`，做如下修改

```patch
- banner: 'images/banner.png'
+ banner: 'images/[your-banner]'
```

其中，`images`目录所对应的位置是`/themes/landscape/source/css/images`，将需要替换的图片放进去即可。

### 方法2

内置的landscape主题提供了一个`_config.landscape.yml`配置文件，打开该文件，添加如下配置

```yml
banner: 'images/[your-banner]'
```

但此时的`images`目录指的是哪呢？

这时，需要打开`_config.yml`文件，修改如下的配置

```patch
- post_asset_folder: false
+ post_asset_folder: true
```

将`post_asset_folder`设为`true`后，在`source`目录下创建如下结构，并将文件放进去即可。

```
- source
  - css
    - images
      - [your-banner]
```

## TODO

- 如何添加评论？
- 如何调整布局？