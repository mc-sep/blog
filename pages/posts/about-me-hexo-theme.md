---
title: 聊聊我在开发的主题&博客框架
date: 2023-11-30T16:00:00.000+00:00
lang: zh
duration: 10min
comment: true
---

[[toc]]

## 起因

来回折腾博客已经是我这几年的一个习惯了，从最开始的 Hexo 到 WordPress，再到 Typecho，最后又回到了 Hexo，这一路走来，我也是折腾了不少的主题，也改了不少的主题，但是我一直都没有一个自己的主题，这次我就想着自己写一个主题或者博客框架，这样就可以满足自己的需求了。

### 我的博客折腾历史

看看我是怎么来来回回折腾又回到起点的吧<span i-noto-loudly-crying-face text-2xl />

- 2019 年末 - 2020 年中：使用 <span op75 i-simple-icons-hexo /> Hexo + Butterfly 主题
- 2020 年中 - 2021 年末 ：使用 <span op75 i-simple-icons-wordpress /> WordPress 主题记不太清了 - CorePress 主题
- 2021 年末 - 2022 年末 ：使用 Typecho + Joe 主题 - Spimes 主题
- 2022 年末 - 2023 年中 ：使用 <span op75 i-simple-icons-wordpress /> WordPress 的 Zibll 主题 和 <span op75 i-simple-icons-hugo /> Hugo 的 LoveIt 主题
- 2023 年中 - 2023 年 10月 ：由于忙于工作一直没有时间去管理博客，索性直接关了
- 2023 年 11月 - 至今 ：刚好工作轻松，想着自己编写个主题，可以满足自己的需求



## 主题特性

技术栈：Nuxt + Vue + TypeScript + UnoCss + Less

基本博客功能除外，我还加入了一些认为有趣的功能，下面我就来介绍一下这些功能吧。

### 1. 在文章中使用 Icon 和 Emoji

在写博客的时候，我们有时候要用到 图标 或者 Logo，这时候我们就需要去下载 图标 或者 Logo 上传图床，然后在引入到文章中，这样做很麻烦，无疑增加了我们的工作量，所以我就想着能不能在文章中直接使用图标呢，刚好想起来  <a href="https://github.com/antfu" target="_blank"><span op75 i-simple-icons-github /> Anthony Fu</a> 大佬的 UnoCss 中可以直接使用图标，于是我果断转换技术栈从 TailwindCss 转到了 UnoCss，这样就可以直接在文章中使用图标了，而且还可以使用 Emoji，这样就可以让文章看起来更加的生动了。

那要如何使用呢？方法极其简单只需要在 Markdown 文件中写这样一段代码就能直接使用了。

```html
<!-- 一个Github的图标 -->
<span i-simple-icons-github />
<!-- 一个Vue的Logo -->
<span i-logos-vue />
<!-- 一个Emoji -->
<span i-twemoji-grinning-face />
<!-- 一个Emoji，鼠标移上去会变成另一个Emoji -->
<span i-twemoji-grinning-face-with-smiling-eyes hover:i-twemoji-face-with-tears-of-joy />
```
<div mt-10px text-4xl flex justify-between >
<span i-simple-icons-github />
<span i-logos-vue />
<span i-twemoji-grinning-face />
<span i-twemoji-grinning-face hover:i-twemoji-grinning-squinting-face />
</div>

不止于此，高度定制话化体验，可以随意的改变图标的大小，颜色，旋转，动画等等，，具体可以等主题发布之后参考文档。

### 2. 在文章中自定义这段文本的样式

有时候我们需要使用一些颜色来做强调提醒之类的，那么肯定要改变这段文本的样式，比如说 文字颜色、文字加粗、文字大小等等，那我们可以这样来定义这段文本的样式。

```html
<!-- 文字颜色 -->
<div text-sky >这是一段蓝色的文字</div>
<!-- 文字加粗 -->
<div font-bold>这是一段加粗的文字</div>
<!-- 文字大小 -->
<div text-20px>这是一段文字大小为20像素的文字</div>
<!-- 组合使用 -->
<div text="sky 20px" font-bold>这是一段蓝色加粗大小为20像素的文字 <i i-uil-cloud-showers-heavy /></div>
```
<div flex="~ col">
<div text-sky >这是一段红色的文字</div>
<div font-bold>这是一段加粗的文字</div>
<div text-20px>这是一段文字大小为20像素的文字</div>
<div text="sky 20px" font-bold>这是一段蓝色加粗大小为20像素的文字 <i i-uil-cloud-showers-heavy /></div>
</div>




未完待续...





[本文谢绝转载，谢谢]
