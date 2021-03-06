<!--
 * @Author: shenxh
 * @Date: 2021-12-13 16:50:08
 * @LastEditors: shenxh
 * @LastEditTime: 2021-12-15 15:54:38
 * @Description: HTML5 音频和视频
-->

- [音频 Audio](#音频-audio)
  - [`<audio>` 标签属性](#audio-标签属性)
- [视频 Video](#视频-video)
  - [`<video>` 标签属性](#video-标签属性)
  - [`<source>` 标签属性](#source-标签属性)

# 音频 Audio
`<audio>` 标签定义声音，比如音乐或其他音频

`<audio>` 与 `</audio>` 标签之间插入的内容是提供给不支持 `audio` 元素的浏览器显示的

```
<audio
    src="https://bjetxgzv.cdn.bspapp.com/VKCEYUGU-hello-uniapp/2cc220e0-c27a-11ea-9dfb-6da8e309e0d8.mp3"
    controls
>
    您的浏览器不支持 audio 标签
</audio>
```

`<audio>` 元素允许使用多个 `<source>` 元素. `<source>` 元素可以链接不同的音频文件，浏览器将使用**第一个**支持的音频文件

```
<audio controls>
    <source src="xxx.ogg" type="audio/ogg">
    <source src="xxx.wav" type="audio/wav">
    <source src="xxx.mp3" type="audio/mpeg">
    您的浏览器不支持 audio 标签
</audio>
```

## `<audio>` 标签属性
|属性|值|描述|
|-|-|-|
|autoplay|autoplay|音频立即播放|
|controls|controls|显示音频控件, 比如播放按钮|
|loop|loop|音频结束后重新开始播放 (循环播放)|
|muted|muted|静音播放|
|preload|preload|音频在页面加载时进行加载，并预备播放<br />如果使用 "autoplay"，则忽略该属性|
|src|*url*|音频地址|

# 视频 Video
`<video>` 标签定义视频，比如电影片段或其他视频流

`<video>` 与 `</video>` 标签之间插入的内容是提供给不支持 `video` 元素的浏览器显示的

```
<video
    src="https://img.cdn.aliyun.dcloud.net.cn/guide/uniapp/%E7%AC%AC1%E8%AE%B2%EF%BC%88uni-app%E4%BA%A7%E5%93%81%E4%BB%8B%E7%BB%8D%EF%BC%89-%20DCloud%E5%AE%98%E6%96%B9%E8%A7%86%E9%A2%91%E6%95%99%E7%A8%8B@20200317.mp4"
    controls
    width="300"
>
    您的浏览器不支持 video 标签
</video>
```

`<video>` 元素允许使用多个 `<source>` 元素. `<source>` 元素可以链接不同的视频文件，浏览器将使用**第一个**支持的视频文件

```
<video controls>
    <source src="xxx.webm" type="video/webm">
    <source src="xxx.ogg" type="video/ogg">
    <source src="xxx.mp4" type="video/mp4">
    您的浏览器不支持 video 标签
</video>
```

## `<video>` 标签属性
|属性|值|描述|
|-|-|-|
|autoplay|autoplay|视频立即播放|
|controls|controls|显示视频控件, 比如播放按钮|
|height|*pixels*|设置视频播放器的高度|
|loop|loop|视频结束后重新开始播放 (循环播放)|
|muted|muted|静音播放|
|poster|*url*|播放前显示的图像 (视频封面)|
|preload|preload|视频在页面加载时进行加载，并预备播放<br />如果使用 "autoplay"，则忽略该属性|
|src|*url*|视频地址|
|width|*pixels*|设置视频播放器的宽度|

## `<source>` 标签属性
|属性|值|描述|
|-|-|-|
|media|*media_query*|规定媒体资源的类型，供浏览器决定是否下载|
|src|*url*|规定媒体文件的 URL|
|type|*MIME_type*|规定媒体资源的 MIME 类型|
|sizes||不同页面布局设置不同图片大小|
|srcset|*url*|`<source>` 应用于 `<picture>` 标签时需要使用到。指定在不同情况下使用的图像 URL|
