<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:10:14
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-16 16:56:55
 * @Description: CSS 溢出 overflow
-->

- [溢出](#溢出)
  - [属性](#属性)
- [场景](#场景)
  - [文字溢出出现省略号](#文字溢出出现省略号)

# 溢出

`overflow` 属性可以控制内容溢出元素框时在对应的元素区间内添加滚动条

## 属性
|值|描述|
|-|-|
|visible|[默认]内容不会被修剪，会呈现在元素框之外|
|hidden|内容会被修剪，并且其余内容是不可见的|
|scroll|内容会被修剪，但是浏览器会显示滚动条以便查看其余的内容|
|auto|如果内容被修剪，则浏览器会显示滚动条以便查看其余的内容|
|inherit|规定应该从父元素继承 overflow 属性的值|

> 注: `overflow` 属性只工作于指定高度的块元素上

# 场景

## 文字溢出出现省略号
```
<div class="content">这是一段没有完全显示的内容</div>
```
```
.content {
    width: 100px;
    height: 100px;
    border: 1px solid #000;
    overflow: hidden; /* 超出隐藏 */
    text-overflow: ellipsis; /* 省略符号来代表被修剪的文本 */
    white-space: nowrap; /* 文本不换行 */
}
```
 