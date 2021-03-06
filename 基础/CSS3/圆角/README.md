<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:20:38
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:52:57
 * @Description: CSS3 圆角
-->

- [CSS3 圆角](#css3-圆角)

# CSS3 圆角
使用 CSS3 `border-radius` 属性，你可以给任何元素制作 "圆角"

如果你在 `border-radius` 属性中只指定一个值，那么将生成 4 个 圆角

但是，如果你要在四个角上一一指定，可以使用以下规则：
+ 四个值: 第一个值为左上角，第二个值为右上角，第三个值为右下角，第四个值为左下角。
+ 三个值: 第一个值为左上角, 第二个值为右上角和左下角，第三个值为右下角
+ 两个值: 第一个值为左上角与右下角，第二个值为右上角与左下角
+ 一个值： 四个圆角值相同

```
div {
    border-radius: 10px 20px 30px 40px; /* 左上角: 10px; 右上角: 20px; 右下角: 30px; 左下角: 40px */
    border-radius: 10px 20px 30px; /* 左上角: 10px; 右上角/左下角: 20px; 右下角: 30px */
    border-radius: 10px 20px; /* 左上角/右下角: 10px; 右上角/左下角: 20px */
    border-radius: 10px; /* 四个角都是 10px */

    width: 400px;
    height: 200px;
    background: lightblue;
}
```

还可以创建椭圆边角:
```
div {
    border-radius: 50%/50px;

    width: 400px;
    height: 200px;
    background: lightblue;
}
```
也可以使用 `%`, 相当于宽高的百分比

宽高相等的元素, 把圆角设为宽高的一半, 就成了一个圆
```
div {
    border-radius: 50px; /* 方法 1 */
    border-radius: 50%; /* 方法 2 */

    width: 100px;
    height: 100px;
    background: lightblue;
}
```
