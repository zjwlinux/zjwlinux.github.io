---
title: next 主题入门
date: 2020-05-21 20:31:21
categories: [博客, 主题]
tags: [Next]
---

简介
<!--more-->

## 安装 Next 主题
    
## 文章分类和标签
### 在文章中添加分类和标签信息
        
    title: <文章标题>
    categories: [父类, 子类]
    tags: [标签1, 标签2]
    
或者

    title: <文章标题>
    categories: 
    -   父类
    -   子类
    tags:
    -   标签1
    -   标签2

分类按照顺序有层级关系，标签的顺序随意

### 修改配置文件
        
    menu:
        tags: /tags/ || fa fa-tags
        categories: /categories/ || fa fa-th

### 创建显示分类信息的页面

    $ hexo new page categories

categories 页面的内容

    ---
    title: 分类
    date: 2020-05-21 20:52:51
    type: "categories"
    ---

### 创建显示标签信息的页面

    $ hexo new page tags

tags 页面的内容

    ---
    title: 标签
    date: 2020-05-21 20:52:51
    type: "tags"
    ---

## 修改字体
### 修改默认字体
#### 方法一
1. 进入文件 themes/next/source/css/_variables/base.styl
2. 找到 $font-size-base，修改字体大小从 1em 到 0.8em

#### 方法二
1. 进入主题配置文件 themes/next/_config.yml
2. 找到 font 配置项，修改下列配置项
        
        enable: true
        global:
            size: 0.8em

## 主页中显示文章的简介
### 方法一
1. 进入主题配置文件 themes/next/_config.yml
2. 添加配置项

    auto_excerpt:
        enable: true
        length: 150

### 方法二

在文章中需要在主页中显示的部分下面加上

    <!--more-->