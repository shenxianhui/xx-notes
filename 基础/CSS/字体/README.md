<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:08:19
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-13 17:08:19
 * @Description: CSS 字体
-->

- [字体大小](#字体大小)
- [字体样式](#字体样式)
- [字体粗细](#字体粗细)

# 字体大小
`font-size` 属性设置字体大小
```
h1 {
    font-size: 40px;
}
h2 {
    font-size: 30px;
}
p {
    font-size: 14px;
}
```

# 字体样式
`font-style` 属性设置字体样式
```
p {
    font-style: normal; /* 正常 */
    font-style: italic; /* 斜体 */
}
```

# 字体粗细
`font-weight` 属性设置字体粗细
```
p {
    font-weight: normal; /* 正常 */
    font-weight: bold; /* 加粗 */
}
```
也可以用数值表示 (整百数: 100-900)
+ `400` 等同于 `normal`
+ `700` 等同于 `bold`
```
p {
    font-weight: 400; /* 正常 */
    font-weight: 700; /* 加粗 */
}
```
