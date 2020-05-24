---
title: css 字体
date: 2020-05-24 09:04:52
categories: [网站]
tags: [css]
---

1. 字体单位，包括 px，em，rem
<!-- more -->

## 字体家族（font-family）

## 字体尺寸（font-size）
### 字体单位
1. px
    
    绝对单位  

    早期 css 的 px 与物理像素是一致的，即 1个 px 对应一个物理像素  
    后来由于该分辨率屏幕的出现，引入了设备像素比例的概念（设备像素比例 = 物理像素数/独立像素数），即 1 个独立像素使用多个物理像素表示，css 的 px 对应于独立像素。

2. em

    相对单位

    相对当前元素的字体的大小，例如当前字体大小是 10 px，则 1em 表示 10 px。

    浏览器默认的字体大小是 16 px，因此 1em 默认表示 16 px。

    子元素的字体大小相对与父元素字体大小的百分比，即如果父元素字体大小为 16 px，子元素的字体大小为 0.5 em，则子元素的字体大小等于 0.5 * 16 = 8 px。

3. rem

    相对单位，永远相对与 html 元素的字体大小



