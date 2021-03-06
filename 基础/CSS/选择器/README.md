<!--
 * @Author: shenxh
 * @Date: 2021-12-13 16:50:36
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-16 09:43:53
 * @Description: CSS 选择器
-->

- [标签选择器](#标签选择器)
- [class 选择器 (类选择器)](#class-选择器-类选择器)
- [id 选择器 (唯一性)](#id-选择器-唯一性)
- [后代选择器](#后代选择器)
- [子元素选择器](#子元素选择器)
- [交集选择器](#交集选择器)
- [并集选择器](#并集选择器)
- [通配符](#通配符)
- [伪类选择器](#伪类选择器)
  - [示例](#示例)
  - [常用伪类选择器总结](#常用伪类选择器总结)

# 标签选择器
直接使用标签名来设定样式

比如: `div` `span` `h1` `p` `a` `img` 等等

缺点: 只能进行**共性**的操作，无法**个性**操作
```
div {
    width: 100%;
    height: 100%;
}
p {
    font-size: 24px;
    color: #000;
}
```

# class 选择器 (类选择器)
+ class 选择器用于描述**一组**元素的样式
+ 同一个元素可以设置多个 class 名
+ 同一个页面的元素可以设置多个相同的 class 名
+ class 选择器在 HTML 中以 class 属性表示, 在 CSS 中，类选择器以 `.` 显示

以下示例中, 三个元素利用 class 选择器统一设置了字号, 分别设置了字色
```
<div class="item item1">示例1</div>
<div class="item item2">示例2</div>
<div class="item item3">示例3</div>
```
```
.item {
    font-size: 28px; /* 字号 */
}
.item1 {
    color: #f00; /* 红色 */
}
.item2 {
    color: #0f0; /* 绿色 */
}
.item3 {
    color: #00f; /* 蓝色 */
}
```

# id 选择器 (唯一性)
+ id 选择器用于描述**一个**元素的样式
+ 同一个元素只能设置一个 id 名
+ 同一个页面的元素不允许出现相同的 id 名
+ id 选择器在 HTML 中以 id 属性表示, 在 CSS 中，id 选择器以 `#` 显示

以下示例中, 使用 id 选择器设置了目标元素的字号及字色
```
<div id="item">示例</div>
```
```
#item {
    font-size: 28px;
    color: #000;
}
```

> 注: 在真正的开发过程中, 主要用 class 来设置样式, 用 id 来获取元素

# 后代选择器
后代选择器用于选取某元素的后代元素

以下示例中, 插入到 div 元素中的所有 span 元素的样式都会被修改
```
<div>
    <!-- 该标签样式会被修改 -->
    <span>示例1</span>
    <p>
        <!-- 该标签样式会被修改 -->
        <span>示例2</span>
    </p>
</div>
```
```
div span {
    font-size: 28px;
}
```

# 子元素选择器
子元素选择器只能选择某元素内部的第一层元素

以下示例中, 只有 div 元素内部的第一层 span 元素样式被修改, 第二层的 span 元素样式不会改变

```
<div>
    <!-- 该标签样式会被修改 -->
    <span>示例1</span>
    <p>
        <!-- 该标签样式不会被修改 -->
        <span>示例2</span>
    </p>
</div>
```
```
div > span {
    font-size: 28px;
}
```

# 交集选择器
精确选择想要修改的元素

```
<div class="item1">示例1</div>
<div id="item2">示例2</div>
```
```
/* 修改 div 标签中 class 为 item1 的元素 */
div.item1 {
    color: #f00;
}
/* 修改 div 标签中 id 为 item2 的元素 */
div#item2 {
    color: #0f0;
}
```

> 注: 标签名与 `.` 或 `#` 之间不要有空格

# 并集选择器
同时修改多个标签的样式, 用 `,` 关联

```
<div class="item1">示例1</div>
<div id="item2">示例2</div>
<span>示例3</span>
```
```
.item1, #item2, span {
    font-size: 28px;
}
```

# 通配符
通配符用 `*` 表示, 它会影响当前页面中的**所有**样式, 一般用于公共样式的配置

```
* {
    font-size: 28px;
    margin: 0;
}
```

# 伪类选择器

## 示例
`:first-child` 选择父元素的第一个子元素


```
<!-- 只有 "示例1" 的样式改变 -->
<div>示例1</div>
<div>示例2</div>
<div>示例3</div>
```
```
div:first-child {
    font-size: 28px;
}
```

## 常用伪类选择器总结
| 选择器               | 示例                  | 说明                                       |
| -------------------- | --------------------- | ------------------------------------------ |
| :first-child         | p:first-child         | 选择所有 p 元素的第一个子元素              |
| :last-child          | p:last-child          | 选择所有 p 元素的最后一个子元素            |
| :first-of-type       | p:first-of-type       | 选择的每个 p 元素是其父元素的第一个 p 元素 |
| :last-of-type        | p:last-of-type        | 选择每个p元素是其母元素的最后一个p元素     |
| :not(selector)       | :not(p)               | 选择所有p以外的元素                        |
| :nth-child(n)        | p:nth-child(2)        | 选择所有 p 元素的父元素的第二个子元素      |
| :nth-last-child(n)   | p:nth-last-child(2)   | 选择所有p元素倒数的第二个子元素            |
| :nth-last-of-type(n) | p:nth-last-of-type(2) | 选择所有p元素倒数的第二个为p的子元素       |
| :nth-of-type(n)      | p:nth-of-type(2)      | 选择所有p元素第二个为p的子元素             |
