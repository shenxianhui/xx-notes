<!--
 * @Author: shenxh
 * @Date: 2021-12-13 17:19:28
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-13 17:20:35
 * @Description: CSS 其他常用属性
-->

- [缩放](#缩放)
  - [`zoom`](#zoom)
  - [`transform: scale();`](#transform-scale)
- [权重 `!important`](#权重-important)

# 缩放

## `zoom`
+ 缩放元素及其内容
+ 元素所占空间也会随之改变
+ 基于元素左上角位置缩放

```
div {
    zoom: 0.5; /* 缩放为之前的 0.5 倍 */
    zoom: 1; /* 缩放为之前的 1 倍 */
    zoom: 2; /* 缩放为之前的 2 倍 */
    background: lightblue;
}
```

## `transform: scale();`
+ 缩放元素及其内容
+ 元素所占空间不会改变
+ 基于元素中心位置缩放

```
div {
    transform: scale(0.5); /* 缩放为之前的 0.5 倍 */
    transform: scale(2); /* 缩放为之前的 2 倍 */
    transform: scale(1); /* 缩放为之前的 1 倍 */
    background: lightcoral;
}
```


# 权重 `!important`
`!important` 与优先级无关，但它与最终的结果直接相关，使用一个 `!important` 规则时，此声明将覆盖任何其他声明

当两条相互冲突的带有 `!important` 规则的声明被应用到相同的元素上时，拥有更大优先级的声明将会被采用

> 注: 使用 `!important` 是一个坏习惯，应该尽量避免，因为这破坏了样式表中的固有的级联规则 使得调试找 bug 变得更加困难了

```
<div id="content" class="content">这里是测试的内容</div>
```
```
div {
    color: #f00 !important; /* 不好意思, 我的优先级最高 */
}
.content {
    color: #0f0;
}
#content {
    color: #00f;
}
```
