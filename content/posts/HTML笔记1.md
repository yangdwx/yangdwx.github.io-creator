---
title: "HTML笔记1"
date: 2021-01-08T23:01:13+08:00
draft: true
---

# HTML 

## W3C

万维网联盟（World Wide Web Consortium W3C），又称 W3C 理事会，是万维网的主要国际标准组织。

Tim Berners-Lee ：万维网的发明人，目前是万维网联盟的主任，也是HTML 的发明者。

## MDN

Mozilla Developer Network（简称 [MDN](https://developer.mozilla.org/zh-CN/)）

## HTML

超文本标记语言（HyperText Markup Language）

1. HTML 版本 （由 W3C 组织制定）
2. DOCTYPE：用来选择文档类型。`<!DOCTYPE html>`（! + TAB）
3. 常见标签
   - 章节标签（语义结构）
     - 标题：`<h1>`~`<h6>`
     - 章节：`<section>`
     - 文章：`<article>`
     - 头部：`<header>`
     - 脚部：`<footer>`
     - 主要内容：`<main>`
     - 旁支内容：`<aside>`
     - 导航：`<nav>`
     - 多级标题：`<hgroup>`
   - 常用文本标签
     - 段落：`<p>`
     - 划分：`<div>`
     - 行内：`<span>`
     - 换行：`<br>` `<wbr>`
     - 分隔线：`<hr>`
     - 保留样式：`<pre>`
     - 强调：`<em>` `<strong>`
     - 上标：`<sup>`
     - 下标：`<sub>`
     - 代码 or 变量：`<var>`
     - 删除线：`<s>`
     - 引用：`<blockquote>` `<q>`
     - 计算机代码（等宽显示）：`<code>`
     - 按键（等宽显示）：`<kbd>`
     - 计算机输出（等宽显示）：`<samp>`
     - 行内标记文本（黄色高亮）：`<mark>`
     - 注音：`<ruby>`
   - 列表标签
     - 有序列表：`<ol>` + `<li>` 
     - 无序列表：`<ul>` + `<li>`  
     - `<dl>` + `<dt>` + `<dd>`  
4. 全局属性（global attributes）是所有元素都可以使用的属性。
   - `id` 属性是元素在网页内的唯一标识符。
     - 属性的值必须是全局唯一，同一页面不能有两个相通的`id`属性。
     - 属性的值不得包含空格。
     - 可以在属性值前面加上`#`作为锚点，定位该元素在网页的位置。
   - `class`属性同来对网页元素进行分类。
   - `title`属性用来为元素添加附加说明。大多数浏览器中，鼠标悬浮在元素上面时，会将`title`属性值作为浮动提示，显示出来。
   - `tabindex`属性用来使用 Tab 键，遍历网页元素。
     - `tabindex` 可以是正数，不必是连续的。
     - `tabindex` 可以是 0，表示最后才被 tab 访问。
     - `tabindex` 可以是 -1，表示不可被 tab 访问。
   - `accesskey`属性指定网页元素获得焦点的快捷键，该属性的值必须是单个的可打印字符。只要按下快捷键，该元素就会得到焦点。
     - Windows 和 Linux：`Alt + 字符键`
     - MAC：`Ctrl + Alt + 字符键`
   - `style`属性是标签的内联 CSS 样式。
   - `hidden`隐藏页面上的元素（优先级地域 CSS 可见性设置）
   - `contenteditable`属性允许用户修改内容。

