---
title: "{{ replace .TranslationBaseName "-" " " | title }}"
subtitle: ""  # 文章副标题
date: {{ .Date }}  # 创建文章时间
draft: false  # 如果为true，这篇文章将不会被构建渲染
author: "HaoZhong"  # 设置文章作者
authorLink: "https://github.com/HaoZhong03"  # 设置文章作者链接
authorEmail: ""             # 设置文章作者邮箱
description: ""             # 文章内容的描述
keywords: ""                # 文章内容的关键词
license: ""                 # 设置文章特殊的许可
comment: false              # 设置文章是否开启评论系统 (https://artalk.js.org/)
weight: 0                   # 排序，数字越小该文章排序越前
   
categories:                 # 设置文章分类
- blogs

hiddenFromHomePage: false   # 如果设为 true, 这篇文章将不会显示在主页上
hiddenFromSearch: false     # 如果设为 true, 这篇文章将不会显示在搜索结果中

summary: ""                 # 设置该文章摘要 
resources:                  # 设置本地资源引用，会在resources目录下寻找
- name: featured-image      # 固定参数名称
  src: featured-image.jpg   # 图片名称,需要与文章同级目录下
- name: featured-image-preview
  src: featured-image-preview.jpg

toc:                        # 设置目录
  enable: true                
math:                       # 设置行内定界符
  enable: false
lightgallery: false         # 如果设为 true, 文章中的图片将可以按照画廊形式呈现
seo:                        # 页面seo配置，
  images: []                # 图片url

repost:                     # 设置为false，关闭转载            
  enable: false  
  url: ""

# See details front matter: https://fixit.lruihao.cn/theme-documentation-content/#front-matter
---

<!--more-->