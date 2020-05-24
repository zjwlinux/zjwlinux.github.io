---
title: Hexo 入门
date: 2020-05-20 16:30:05
categories:
-    博客
-    Hexo
tags:
-    Hexo
---

简介
<!--more-->

## 功能
使用 Markdown 来创建页面的内容，Hexo 自动将 Markdown 文件转换为静态的网页，并且使用漂亮的主题来对网页进行装饰

## Hexo 安装
### 安装 git 和 node.js
### 安装 Hexo
    $ npm install -g hexo-cli
### 安装 Hexo Server
    $ npm install hexo-server --save

hexo server 启动后，会自动监控项目的变化，并更新，从而修改项目后不需要重新启动 server。启动 hexo server 的方法是

    $ hexo server

hexo server 默认的端口是 4000

hexo server 可以启动多个实例，只需要制定不同的端口即可

    $ hexo server -p 5000

### 初始化 Hexo 项目

```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
初始化完成后，项目文件夹中至少包含下列内容
* _config.yml   // Hexo 的配置文件
* package.json
* scaffolds
* sources
    * _drafts   // 草稿，默认不显示
    * _posts    // 网页内容
* themes

### 配置

#### 指定自定义配置文件
自定义的配置文件会替换默认的 _config.yml。多个自定义配置文件中，如果有相同的配置，后面的会替换前面的。多个自定义配置文件会被保存到一个新的配置文件中 _multiconfig.yml

    $ hexo server --config <custom.yml>
    $ hexo server --config <custom.json>
    $ hexo server --config <custom.yml>, <custom.json>

#### 主题配置文件
* 主题有自己的配置文件 _config.yml
* 对 theme 配置也可以放到 Hexo 的配置文件 _config.yml 中

### 指令
#### init
    $ hexo init [folder]

初始化网站，如果没有指定文件夹，那么对当前的文件进行初始化

#### new 
    $ hexo new [layout] <title>

创建一个新文章

#### generate
    $ hexo generate

生成静态文件

#### publish
    $ hexo publish [layout] <filename>
发布草稿文章

#### server
    $ hexo server
启动一个本地服务器

#### deploy
    $ hexo deploy
部署网站

#### render
    $ hexo render

    option:
        -o, --output 输出路径
编译文章

#### migrate
    $ hexo migrate <type>

从其他博客系统整合内容

#### clean
    $ hexo clean
清除缓存文件（db.json）和生成的文件（public）

#### list
    $ hexo list <type>

    type:
        page, post, tag, route or category
列出网站的信息

#### version
    $ hexo version
显示 hexo 的版本信息

## 功能
### 增加搜索功能
1. 安装插件

        $ npm install hexo-generator-searchdb --save

2. 修改站点的配置文件 _config.yml，增加 `search` 配置，见 `hexo_config` 文章

        search:
            path: search.xml
            field: post
            format: html
            limit: 10000

3. 修改主题的配置文件 _config.yml
        
        local_search:
            enable: true
