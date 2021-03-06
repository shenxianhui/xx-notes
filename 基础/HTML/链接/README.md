<!--
 * @Author: shenxh
 * @Date: 2021-12-13 16:46:52
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-13 16:46:52
 * @Description: HTML 链接
-->

- [HTML 链接](#html-链接)
  - [属性](#属性)
  - [扩展](#扩展)

# HTML 链接
HTML使用标签 `<a>` 来设置超文本链接

超链接可以是一个字，一个词，或者一组词，也可以是一幅图像，您可以点击这些内容来跳转到新的文档或者当前文档中的某个部分

当您把鼠标指针移动到网页中的某个链接上时，箭头会变为一只小手

比如这样: [跳转至百度](https://www.baidu.com/)
```
<a href="https://www.baidu.com">跳转至百度</a>

<a href="https://www.baidu.com" target="_blank">在新窗口中打开</a>
```

## 属性
+ `href`: 跳转地址, 默认当前页
+ `target`: 设置跳转页面的弹出方式, 默认当前页打开

|属性填|值|描述|
|-|-|-|
|`href`|URL|跳转地址|
|`target`|`_blank`<br />`_parent`<br />`_self`<br />`_top`|规定在何处打开目标 URL。仅在 `href` 属性存在时使用<br /><br />`_blank`: 在新窗口中打开<br />`_parent`: 在父窗口中打开<br />`_self`: [默认] 在当前页面中打开

## 扩展
超链接除了页面跳转之外, 还可以实现**锚点**功能
```
<a href="#title1">定位到一级标题</a>
<a href="#title2">定位到二级标题</a>
<a href="#title3">定位到三级标题</a>

<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<h1 id="title1">一级标题</h1>
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<h2 id="title2">二级标题</h2>
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<h3 id="title3">三级标题</h3>
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
<br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br /><br />
```
