---
title: GitHub Page
date: 2020-05-21 21:58:05
categories: [博客]
tags:
---

简介
<!--more-->

## 创建 GitHub Page 网站
1. 注册 GitHub 账号
2. 创建与账号同名的 Repository

    例如账号名称为 zjw，则创建的 Repository 名称为 zjw.github.io  
    可以使用 https://zjw.github.io 访问网站

## 使用自有域名访问 GitHub Page
1. 在自有域名所属网站配置域名解析规则

    例如在**阿里云**注册的域名，可以使用 cname 方式将自有域名映射为 GitHub Page 的域名

2. 在 GitHub 配置使用自有域名访问 GitHub Page

    Repository 的 setting 页面，在 custom domain 中设置自有域名，并且去除勾选 Force Https 选项。因为阿里云的域名如果只支持 http 协议的话，则会使用 http://zjw.github.io 访问网站，而不是 https://zjw.github.io
