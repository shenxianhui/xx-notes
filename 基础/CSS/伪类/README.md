<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:19:11
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:52:40
 * @Description: CSS 伪类
-->

- [伪类](#伪类)
  - [链接](#链接)
  - [焦点](#焦点)
  - [其他](#其他)
- [伪元素](#伪元素)
  - [`::first-line`](#first-line)
  - [`::first-letter`](#first-letter)
  - [`::before`](#before)
  - [`::after`](#after)
  - [`::selection`](#selection)

# 伪类
CSS伪类是用来添加一些选择器的特殊效果, 前缀用 `:` 表示

## 链接
|选择器|示例|说明|
|-|-|-|
|:link|a:link|选择所有未访问链接|
|:visited|a:visited|选择所有访问过的链接|
|:hover|a:hover|把鼠标放在链接上的状态|
|:active|a:active|选择正在活动链接|

## 焦点
|选择器|示例|说明|
|-|-|-|
|:focus|input:focus|选择聚焦状态时的元素|

## 其他
|选择器|示例|说明|
|-|-|-|
|:first-child|p:first-child|选择所有 p 元素的第一个子元素|
|:last-child|p:last-child|选择所有 p 元素的最后一个子元素|
|:first-of-type|p:first-of-type|选择的每个 p 元素是其父元素的第一个 p 元素|
|:last-of-type|p:last-of-type|选择每个p元素是其母元素的最后一个p元素|
|:not(selector)|:not(p)|选择所有p以外的元素|
|:nth-child(n)|p:nth-child(2)|选择所有 p 元素的父元素的第二个子元素|
|:nth-last-child(n)|p:nth-last-child(2)|选择所有p元素倒数的第二个子元素|
|:nth-last-of-type(n)|p:nth-last-of-type(2)|选择所有p元素倒数的第二个为p的子元素|
|:nth-of-type(n)|p:nth-of-type(2)|选择所有p元素第二个为p的子元素|

# 伪元素
CSS 伪元素用于设置元素指定部分的样式, 前缀用 `::` 表示

它可用于：
+ 设置元素的首字母、首行的样式
+ 在元素的内容之前或之后插入内容

## `::first-line`
用于向文本的**首行**添加特殊样式

> 注：`::first-line` 伪元素只能应用于块级元素

```
<div class="wrap">
    <p class="content">
        首行样式会被修改首行样式会被修改首行样式会被修改
    </p>
</div>
```
```
.wrap {
    width: 200px;
    height: 100px;
    margin: 100px auto;
    border: 1px solid #000;
}
.content::first-line {
    color: #f00;
    background-color: #ff0;
    font-size: 30px;
    font-weight: bold;
}
```

## `::first-letter`
用于向文本的**首字符**添加特殊样式

```
<div class="wrap">
    <p class="content">
        首个字符的样式会被修改
    </p>
</div>
```
```
.wrap {
    width: 200px;
    height: 100px;
    margin: 100px auto;
    border: 1px solid #000;
}
.content::first-letter {
    color: #f00;
    background-color: #ff0;
    font-size: 30px;
    font-weight: bold;
}
```

## `::before`
用于在元素内容之前插入一些内容

```
<div class="content">测试</div>
```
```
.content::before {
    content: '这里是 before 的内容';
    font-size: 24px;
    color: #f00;
    background: #ff0;
}
```

## `::after`
用于在元素内容之后插入一些内容

```
<div class="content">测试</div>
```
```
.content::after {
    content: '这里是 after 的内容';
    font-size: 24px;
    color: #f00;
    background: #ff0;
}
```

## `::selection`
匹配用户选择的元素部分

```
<div class="content">这里是测试的内容</div>
```
```
.content::selection {
    color: #f00;
    background: #ff0;
}
```
