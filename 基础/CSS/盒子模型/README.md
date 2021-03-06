<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:08:53
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-16 09:46:08
 * @Description: CSS 盒子模型
-->

- [CSS 盒子模型](#css-盒子模型)
  - [外边距 `margin`](#外边距-margin)
    - [单边属性](#单边属性)
    - [简写属性](#简写属性)
    - [`auto`](#auto)
  - [内边距 `padding`](#内边距-padding)
    - [单边属性](#单边属性-1)
    - [简写属性](#简写属性-1)
  - [边框 `border`](#边框-border)
    - [边框宽度](#边框宽度)
    - [边框样式](#边框样式)
    - [边框颜色](#边框颜色)
    - [单边属性](#单边属性-2)
    - [简写属性](#简写属性-2)
- [元素尺寸计算](#元素尺寸计算)
  - [`content-box` 与 `border-box` 区别](#content-box-与-border-box-区别)
    - [`content-box` [默认值]](#content-box-默认值)
    - [`border-box`](#border-box)

# CSS 盒子模型
CSS盒模型本质上是一个盒子，封装周围的HTML元素，它包括：边距，边框，填充，和实际内容

+ Margin(外边距) - 清除边框外的区域，外边距是透明的
+ Border(边框) - 围绕在内边距和内容外的边框
+ Padding(内边距) - 清除内容周围的区域，内边距是透明的
+ Content(内容) - 盒子的内容，显示文本和图像

![](./images/1639557943900.png)

## 外边距 `margin`
CSS `margin` (外边距) 属性定义元素周围的空间

`margin` 没有背景颜色，是完全透明的

### 单边属性
```
div {
    margin-top: 25px; /* 上边距 */
    margin-bottom: 25px; /* 下边距 */
    margin-right: 50px; /* 右边距 */
    margin-left: 50px; /* 左边距 */
}
```

### 简写属性
为了缩短代码, 允许在一个属性中指定的所有填充属性, 用 `margin`
表示

`margin` 属性可以有 1-4 个值
+ `margin: 上 右 下 左;`
```
div {
    /* 上边距: 25px; 右边距: 50px; 下边距: 75px; 左边距: 100px */
    margin: 25px 50px 75px 100px;
}
```
+ `margin: 上 左右 下;`
```
div {
    /* 上边距: 25px; 左右边距: 50px; 下边距: 75px */
    margin: 25px 50px 75px;
}
```
+ `margin: 上下 左右;`
```
div {
    /* 上下边距: 25px; 左右边距: 50px */
    margin: 25px 50px;
}
```
+ `margin: 上下左右;`
```
div {
    /* 上下左右边距: 25px */
    margin: 25px;
}
```

### `auto`
`margin` 还有一个常用的值: `auto`

它可以自动分配可用空间, 利用 `margin: auto;` 可实现**块元素**水平居中

## 内边距 `padding`
CSS `padding` (内边距) 是一个简写属性，定义元素边框与元素内容之间的空间，即上下左右的内边距

### 单边属性
```
div {
    padding-top: 25px; /* 上边距 */
    padding-bottom: 25px; /* 下边距 */
    padding-right: 50px; /* 右边距 */
    padding-left: 50px; /* 左边距 */
}
```

### 简写属性
为了缩短代码, 允许在一个属性中指定的所有填充属性, 用 `padding`
表示

`padding` 属性可以有 1-4 个值
+ `padding: 上 右 下 左;`
```
div {
    /* 上边距: 25px; 右边距: 50px; 下边距: 75px; 左边距: 100px */
    padding: 25px 50px 75px 100px;
}
```
+ `padding: 上 左右 下;`
```
div {
    /* 上边距: 25px; 左右边距: 50px; 下边距: 75px */
    padding: 25px 50px 75px;
}
```
+ `padding: 上下 左右;`
```
div {
    /* 上下边距: 25px; 左右边距: 50px */
    padding: 25px 50px;
}
```
+ `padding: 上下左右;`
```
div {
    /* 上下左右边距: 25px */
    padding: 25px;
}
```

## 边框 `border`
CSS边框属性允许你指定一个元素边框的样式和颜色

### 边框宽度
通过 `border-width` 属性为边框指定宽度, 可以有 1-4 个值
```
div {
    border-width: 1px 2px 3px 4px; /* 上 右 下 左 */
    border-width: 1px 2px 3px; /* 上 左右 下 */
    border-width: 1px 2px; /* 上下 左右 */
    border-width: 1px; /* 上下左右 */
}
```

### 边框样式
`border-style` 属性用来定义边框的样式
```
div {
    border-style: none; /* [默认]无边框 */
    border-style: dashed; /* 虚线边框 */
    border-style: solid; /* 实线边框 */
    border-style: double; /* 两个边框 */
}
```

### 边框颜色
`border-color 属性用于设置边框的颜色

可以设置的颜色：
+ name - 指定颜色的名称，如 `red`
+ RGB - 指定 RGB 值, 如 `rgb(255,0,0)`
+ Hex - 指定16进制值, 如 `#ff0000`

### 单边属性
```
div {
    border-top-width: 1px; /* 设置上边框宽度为 1px */
    border-right-style: solid; /* 设置右边框样式为 solid */
    border-bottom-color: #000; /* 设置下边框颜色为 #000 */
}
```

### 简写属性
上面的例子用了很多属性来设置边框

当然, 你也可以用一个属性 `border` 设置
```
div {
    border: 1px solid #000; /* 宽度 样式 颜色 */
}
```

# 元素尺寸计算
`box-sizing` 属性定义如何计算一个元素的总宽度和总高度

`box-sizing` 常用值有两个: `content-box` 和 `border-box`

## `content-box` 与 `border-box` 区别

### `content-box` [默认值]
内边距 (`padding`) 和边框 (`border`) 的值**不包含**在宽 (`width`) 高 (`height`)中
```
div {
    box-sizing: content-box;

    width: 200px;
    height: 100px;
    padding: 10px;
    border: 20px solid #ff0;
    margin: 30px;
    background-color: lightblue;
}
```
上面例子计算公式为:
+ 实际宽度 = 设置宽度 `width` + 左右内边距 `padding` + 左右边框 `border`
    + 260px = 200px + (10px * 2) + (20px * 2)
+ 实际高度 = 设置高度 `height` + 上下内边距 `padding` + 上下边框 `border`
    + 160px = 100px + (10px * 2) + (20px * 2)

### `border-box`
内边距 (`padding`) 和边框 (`border`) 的值**包含**在宽 (`width`) 高 (`height`)中
```
div {
    box-sizing: border-box;

    width: 200px;
    height: 100px;
    padding: 10px;
    border: 20px solid #ff0;
    margin: 30px;
    background-color: lightcoral;
}
```
上面例子计算公式为:
+ 实际宽度 = 设置宽度 `width`
    + 200px = 200px
+ 实际高度 = 设置高度 `height`
    + 100px = 100px

> 注: `margin` 属性虽然不会计算到宽高中, 但也会占用元素周围的空间, 常用于用于增加两个相邻元素的间隔
