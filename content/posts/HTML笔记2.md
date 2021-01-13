---
title: "HTML笔记2"
date: 2021-01-11T15:29:12+08:00
draft: true
---

# HTML 标签

## `<a>`标签

**`<a>`标签定义超链接，用于从一个页面链接到另一个页面**

1. href 属性

   i. 网址

   - `<a href="google.com>google</a>"` 相对路径，会在当前目录下查找 "google.com"。
   - `<a href="http://goolge.com">google</a>` 跳转链接表明 HTTP 或 HTTPS 协议。
   - `<a href="/goolge.com">google</a> `浏览器根据当前协议，补全无协议链接。

   ii. 锚点

   - `<a href="#xxx">google</a>` 跳转到 `id=xxx `的页面位置。

   iii. 路径

   - /a/b/c 以及 a/b/c
   - Index.html 以及./index.html

   iiii. 伪协议

   - `<a href="javascript: alert();">google</a>` **伪协议，点击会直接执行js语句。**

      `<a href="javascript:;">google</a>` 可以完美实现点击链接无事发生。

   - `<a href="mailto:yangdwx@163.com">email</a> ` 点击发起邮件，一般拉起邮箱客户端。

   - `<a href="tell:13xxxxxxxxx">tell</a>` 点击拨打电话。

2. target 属性

   - `<a href="http://www.google.com" target="_blank">google</a> ` 在新的窗口打开页面。
   - `<a href="http://www.google.com" target="_self">google</a> ` 在当前窗口打开新页面。
   - `<a href="http://www.google.com" target="_parent">google</a> ` 在父级窗口打开新页面。
   - `<a href="http://www.google.com" target="_top">google</a> ` 在顶级窗口打开新页面。
   - `<a href="http://www.google.com" target="xxx">google</a>` 在 name=xxx 的窗口打开页面。

3. download 属性

   - `<a herf="http://google.com" download>下载</a>` 下载链接所指的页面。

     > 不是所有浏览器都会支持，尤其是手机浏览器。

## `<iframe>`标签

**HTML内联框架元素，它能够将另一个HTML页面嵌入到当前页面中。**

`<src>`的值确定被嵌套的页面的 URL 地址，CSS 的 `height` 和 `width` 属性可以调整被嵌套属性的窗口大小。

![](/images/iframe.png)

## `<table>` 标签

****

**`<table> ` 标签定义 HTML 表格**，含有 3 个主要标签：

1. `<thead> ` 表格头。
2. `<tbody>`表格主体。
3. `<tfoot>` 表格脚。

> 这 3 个主要标签与代码先后顺序无关，浏览器会自动调整为表头、表格体、表格脚的顺序，如果不写主要标签，浏览器则会自动补充`<tbody>`标签并将内容填入。

主要标签里含有 3 个次级标签：

1. `<tr>` table row，定义HTML表格中的一行单元格，成对出现，一个 `<tr>` 元素包含一个或多个 `<th>` 或 `<td>` 元素。
2. `<th>` 表示HTML表格的表头部分，该标签中的内容会以粗体显示并居中。

3. `<td>` 定义 HTML 表格中的标准单元格，表示表格中的数据，通常是普通的左对齐文本。

可以用 CSS 控制表格相关的样式

1. `table-layout`：`auto` 值是根据内容确定表格宽度，`fixed` 保证每个列都是等宽（内容超出长度会引起换行，增加单元格高度）。

2. `border-spacing`: 设置单元格之间的间距。

3. `border-collapse`: 去除单元格之间的间距。

   ![](/images/table1.png)![](/images/table2.png)

## `<img>` 标签

**`<img>` 标签一般用于发起`get` 请求，将一份图像嵌入文档。**

1. 常用属性
   - `src` 属性是**必须的**，它包含了你想嵌入的图片的文件路径。
   - `alt` 属性包含一条对图像的文本描述，如果图像未被正确加载，则会在图片位置显示该属性的值。
   - `width` 与 `height` 用来设置图片在页面的尺寸，只写宽度，高度自适应，只写宽度，高度自适应，**设置该属性的时候一定要避免图像变形失真**。
   - `max-width`: 响应式，图片会根据视窗大小进行自适应。

2. 事件

   - `onload`：加成功时执行

   - `onerror`：加载失败时执行

     > 两个事件可以合并使用，加载成功和失败时进行提示，并在加载失败时进行纠错：
     >
     > ```javascript
     > <img id="pic1" src="1.png" alt="">
     > <script>
     > 	pic1.onload = function (){
     > 	console.log(`加载成功`);
     > 	}
     > 	pic1.onerror = function (){
     > 	console.log(`加载失败`);
     > 	pic.src = '/new-pic.png'
     >   }
     > <script>
     > ```
     >
     > 

## `<form>` 标签

**`<form>`标签用于为用户输入创建 HTML 表单，用于向服务器传输数据，一般发送 `GET` 或者 `POST` 请求。**

1. `action` 属性：指定请求路径。

2. `method`属性：默认为`GET`，一般设置为`POST`。

3. `autocomplete`：设置为`'on'`，可以开启建议填充内容。

4. `target`与 `<a>` 标签的 `target` 属性完全一致。

5. `onsubmit`：监听用户提交事件。

   > `<form>` 必须有有一个 含有`type=”submit“` 属性的标签的用于提交。

   ```HTML
   <form action="users" method="POST">
     <input type="text" name="username">
     <input type="password" name="password">
     <input type="submit" value="提交">
   </form>
   ```

## `<input>` 标签

**`<input>` 标签规定了用户可以在其中输入数据的输入字段。在 `<form>` 标签中使用，用来声明允许用户输入数据的 input 控件。输入字段可通过多种方式改变，取决于 type 属性。**

1. `type` 属性
   - `button` ：如果一个 `<form>` 里面只有一个 `<button>` 按钮，且没有设置 `type` 属性，则会自动升级为当前标签的 `submit` 按钮。这种情况下: `<button>button</button>` 等价于 `<input type = "submit" value="提交">`。
   - `text`：单行文本框。
   - `textarea`：多行文本框，可以用 CSS 控制输入区域大小。
   - `password`：输入内容不可见，以*表示。
   - `radio`：单选框，多个含有 `type=ration` 的元素可以设置 `name` 为同一个字符串实现单选。
   - `checkbox`： 复选框，可以用相通的`name`值实现分组。
   - `file`：选择单个文件，添加`multiple` 实现文件多选
   - `hidden`：隐藏输入框，一般用于使用 js 自动获取并填入值。
   - `label`：可以使用 `<label>` 元素来定义 `<input>` 元素的标注。
   - `select`：用来创建下来列表，配合`<option>`标签实现不用功能：
     - `name` 属性：定义下拉列表的名称。
     - `multiple` 属性：当该属性为` true` 时，可选择多个选项。
     - `size` 属性：规定下拉列表中可见选项的数目。
     - `required`：规定用户在提交表单前必须选择一个下拉列表中的选项（验证器）。
     - `disabled`：当该属性为 `true` 时，会禁用下拉列表。
     - `autofocus`：规定在页面加载时下拉列表自动获得焦点。
     - `<option>` 可以设置 `disabled` 属性和 `selected ` 属性，分别该选项不可选和默认已选择选项。

2. 事件

   - `onchange`：改变时监听
   - onfocus：获得焦点时监听
   - onblur：失去焦点时监听

   >注意事项：
   >
   >- 一般不监听 `input` 的 `click` 事件
   >- `form` 里面的 `input` 要有 `name` 属性
   >- `form` 里面要放一个 `type=submit `才能触发 `submit` 事件。（或者没有设置`type`的`<button>`标签。

