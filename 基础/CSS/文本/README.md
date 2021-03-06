<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:08:02
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:56:40
 * @Description: CSS 文本
-->

- [文本颜色](#文本颜色)
- [文本水平对齐方式](#文本水平对齐方式)
- [文本垂直对齐方式](#文本垂直对齐方式)
- [文本修饰](#文本修饰)
- [文本阴影](#文本阴影)

# 文本颜色
颜色用 `color` 属性设置, 属性值有三种写法：
+ 十六进制值 - 如: `#FF0000`
+ 一个RGB值 - 如: `RGB(255, 0, 0)`
+ 颜色的名称 - 如: `red`

例如以下三种标题样式都是同样的颜色
```
h1 {
    color: #f00;
}
h2 {
    color: red;
}
h3 {
    color: rgb(255, 0, 0);
}
```

# 文本水平对齐方式
用 `text-align` 属性来设置文本的水平对其方式

+ 文本可左对齐、右对齐或居中对齐
+ 当 `text-align` 设置为 `justify` 时, 每一行被展开为宽度相等，左右外边距是对齐的（如杂志和报纸）
```
h1 {
    text-align: left; /* 左对齐 */
    text-align: center; /* 居中对齐 */
    text-align: right; /* 右对齐 */
}
```

# 文本垂直对齐方式
如果元素设置了高度的话, 我们一般通过设置行高 `line-height`, 使之等于高度 `height`, 来实现文本的垂直对齐

```
<h1>标题</h1>
```
```
h1 {
    height: 100px;
    line-height: 100px;
    background-color: lightblue;
}
```

# 文本修饰
`text-decoration` 属性用来设置或删除文本的装饰

从设计的角度看 `text-decoration` 属性主要是用来删除链接的下划线：
```
a {
    text-decoration: none;
}
```

# 文本阴影
通过 `text-shadow` 来设置文本阴影, 以达到文字美化的效果
```
h1 {
    text-shadow: 2px 2px #f00;
}
```
