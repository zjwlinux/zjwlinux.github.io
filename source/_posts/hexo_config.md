---
title: Hexo 配置文件
date: 2020-05-21 16:47:32
categories: [博客, Hexo]
tags:
-   Hexo
---

简介
<!--more-->

## Writing
### post_asset_folder

    value: true, false

是否在使用 `hexo new` 创建文章时创建同名的文件夹，该文件夹用来保存对应的文章中使用的资源，如图片等。值为 `true` 时表示创建

## Search
    Search:
      path: search.xml
      field: post
      format: html
      limit: 10000

使 hexo 支持搜索功能
Layout folder. This folder contains the theme’s template files, which define the appearance of your website.