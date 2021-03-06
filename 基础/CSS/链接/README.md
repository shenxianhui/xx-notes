<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:08:37
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:51:47
 * @Description: CSS 链接
-->

- [链接样式](#链接样式)
- [文本修饰](#文本修饰)
- [背景颜色](#背景颜色)

# 链接样式
链接的样式可以用任何CSS属性 (如颜色，字体，背景等) 来设置

特别的链接, 可以有不同的样式, 这取决于他们是什么状态
```
/* 未访问链接*/
a:link {
    color: #000;
}
/* 已访问链接 */
a:visited {
    color: #0f0;
}
/* 鼠标移动到链接上 */
a:hover {
    color: #f0f;
}
/* 鼠标点击链接时 */
a:active {
    color: #0ff;
}
```

# 文本修饰
`text-decoration` 属性主要用于删除链接中的下划线
```
/* 未访问链接*/
a:link {
    text-decoration: none; /* 不显示下划线 */
}
/* 已访问链接 */
a:visited {
    text-decoration: none; /* 不显示下划线 */
}
/* 鼠标移动到链接上 */
a:hover {
    text-decoration: underline; /* 显示下划线 */
}
/* 鼠标点击链接时 */
a:active {
    text-decoration: underline; /* 显示下划线 */
}
```

# 背景颜色
```
a {
    background-color: #f0f;
}
```
