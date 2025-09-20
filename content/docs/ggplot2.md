---
title: "[R]ggplot2官方文档简明指南"
date: 2025-09-19T14:03:27+08:00
lastmod: 2025-09-19T14:03:27+08:00
author: ["HaoZhong03"]
summary: ""             # 简单描述，会展示在主页，可被搜索
weight:                 # 输入1可以顶置文章
draft: false            # 是否为草稿
comments: true          # 是否开启评论
showToc: true           # 显示目录
TocOpen: true           # 自动展开目录
autonumbering: true     # 目录自动编号
hidemeta: false         # 是否隐藏文章的元信息，如发布日期、作者等
disableShare: true      # 底部不显示分享栏
searchHidden: false     # 该页面不能被搜索到
showbreadcrumbs: true   # 顶部显示当前路径
mermaid: true           # 是否开启mermaid
cover:
    image: "https://ggplot2.tidyverse.org/logo.png"           # 封面图片
    hidden: true        # 文章页面隐藏封面图片
tags:
- R
- ggplot2
- 科研绘图
- 可视化
categories:
- R
---

苯人不生产教程，只是文档的搬运工。本文是基于[ggplot2官方文档](https://ggplot2.tidyverse.org/)建立的最简明中文翻译，力图作为一个词典，适合于所有像我一样被ggplot2折磨到夜不能寐辗转反侧的人使用。

详细教程可参考[ggplot2 book](https://ggplot2-book.org/)。

## 1. ggplot2原理简介

![ex1](https://ggplot2.tidyverse.org/articles/ggplot2_files/figure-html/overview_graphic-1.png)

ggplot2绘图有7个组成部分，其中`data`、`Mapping`、`Layers`是必需的。

### 1.1 Data

顾名思义，这一层决定你绘图所需的数据来源：

```
ggplot(data = mpg)
```

`mpg`是你的数据集。

### 1.2 Mapping

这一层决定你的数据如何映射到图像的属性上。

```
ggplot(mpg, mapping = aes(x = cty, y = hwy))
```

此命令将`mpg`数据集中的`cty`和`hwy`列分别映射到x和y坐标。

### 1.3 Layers

这一层即图层，决定你的图像以何种方式被绘制。

```
ggplot(mpg, aes(cty, hwy)) +
  # 创建散点图
  geom_point() +
  # 拟合并展示趋势线
  geom_smooth(formula = y ~ x, method = "lm")
```
![ex1.3](https://ggplot2.tidyverse.org/articles/ggplot2_files/figure-html/example_layer-1.png)

### 1.4 Scales

将图上的内容赋予不同的尺度，模板为`scale_{aesthetic}_{type}()`。根据映射`{aesthetic}`中的某种属性，按照`{type}`赋予尺度。

```
ggplot(mpg, aes(cty, hwy, colour = class)) +
  geom_point() +
  scale_colour_viridis_d()
```

即根据colour，将图像按照viridis调色板赋予尺度。

![ex1.4](https://ggplot2.tidyverse.org/articles/ggplot2_files/figure-html/example_scales-1.png)

### 1.5 Facets 

拆分数据集至不同的面板。

```
ggplot(mpg, aes(cty, hwy)) +
  geom_point() +
  facet_grid(year ~ drv)
```

![ex1.5](https://ggplot2.tidyverse.org/articles/ggplot2_files/figure-html/example_facets-1.png)

### 1.6 Coordinates

指定图像的坐标。比如使用`coord_fixed()`自动设置图像横纵坐标比例。

```
ggplot(mpg, aes(cty, hwy)) +
  geom_point() +
  coord_fixed()
```

![ex3](https://ggplot2.tidyverse.org/articles/ggplot2_files/figure-html/example_coords-1.png)

### 1.7 Themes

使用内置的`theme_*()`函数或`theme()`设置你的主题。

```
ggplot(mpg, aes(cty, hwy, colour = class)) +
  geom_point() +
  theme_minimal() +
  theme(
    legend.position = "top",
    axis.line = element_line(linewidth = 0.75),
    axis.line.x.bottom = element_line(colour = "blue")
  )
```

![ex4](https://ggplot2.tidyverse.org/articles/ggplot2_files/figure-html/example_theme-1.png)

## 2. 绘图基础

所有的图都开始于`ggplot()`，它提供了数据的来源和映射的方式。随后，你才能用`+`增加更多的内容。保存图像则使用`ggsave()`。

|API|Function|
|---|---|
|`ggplot()`|创建新图|
|`aes()`|构建映射|
|`add_gg()`;`%+%`|增加组成部分|
|`ggsave()`|保存图像|
|`qplot()`;`quickplot()`|快速画图|

## 3. Layers

### 3.1 Geoms 

---

施工中

---
<script src="https://giscus.app/client.js"
        data-repo="Haozhong03/Haozhong03.github.io"
        data-repo-id="R_kgDOPutG0g"
        data-category="Announcements"
        data-category-id="DIC_kwDOPutG0s4Cvi80"
        data-mapping="pathname"
        data-strict="0"
        data-reactions-enabled="1"
        data-emit-metadata="0"
        data-input-position="bottom"
        data-theme="preferred_color_scheme"
        data-lang="zh-CN"
        crossorigin="anonymous"
        async>
</script>