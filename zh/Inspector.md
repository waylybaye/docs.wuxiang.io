### 3.3 填的那些是什么意思？

「无相」的每个控件都会从 HTML 中提取信息，填入的那些就是 `CSS 选择器`，「无相」会提取出匹配的 `HTML 元素的值` 然后更新控件。`@开头的` 是取值器，你可以使用 `@属性值` 来获取一些特殊属性比如一些图片真实地址可能保存在 `@data-src` 中。


### 3.4 打开开发者工具

1. 用电脑 Chrome 打开 [https://www.ifanr.com](https://www.ifanr.com) 
2. 使用右键选择 `审查元素` 来打开开发者工具
3. 点击左上角的第二个图标，切换到移动浏览器模式（更改 User Agent）然后刷新就会进入手机版

### 3.5 查看元素信息

![](https://github.com/waylybaye/docs.wuxiang.io/raw/master/img/inspector.png)
然后右键顶部的幻灯片，选择 `审查元素` 如果你懂 CSS 的话你就会看到，幻灯片的容器有个 `class` 叫做 `.top-news`，然后每个幻灯片有个 `class` 叫做 `.news-item`
