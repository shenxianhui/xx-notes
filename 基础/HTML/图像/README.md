<!--
 * @Author: shenxh
 * @Date: 2021-12-13 16:47:16
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:54:08
 * @Description: HTML 图像
-->

- [HTML 图像](#html-图像)
  - [属性](#属性)

# HTML 图像
在 HTML 中，图像由 `<img>` 标签定义

`<img>` 是空标签，它只包含属性，并且没有闭合标签
```
<img
  src="https://www.baidu.com/img/PCtm_d9c8750bed0b3c7d089fa7d55720d6cf.png"
  alt="百度"
  width="250"
  height="100"
/>
```

## 属性
|属性填|值|描述|
|-|-|-|
|`src`|URL|图像的 URL 地址|
|`alt`|*string*|图像的替代文本, 在图片加载失败时显示|
|`width`|*number*|图片宽度, 单位默认 `px`|
|`height`|*number*|图片高度, 单位默认 `px`|

注: 宽高属性建议不要写, 统一在 CSS 中设置比较好些
