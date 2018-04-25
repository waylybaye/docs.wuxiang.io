# 无相编辑器手把手教程


这篇文章将手把手教你做一个 ifanr 原生 App 出来

## 注册一个账号

你可以在 TestFlight 更新中找到地址。


## 新建一个相

1. 应用名字输入 "ifanr" 点击右上角的 "保存" 后下面会显示一个二维码。
2. 用无相扫描二维码后会自动进入调试模式，并显示 `Waiting for Push` 表示正在准备接收指令。
3. 点击二维码下面的 `推送更新` 可以将最新配置推送到手机上。

「无相」会显示  `No Initial URL` 表示此应用没有设置一个初始地址，在 `起始地址` 中填入 `https://www.ifanr.com` 再点击推送就会显示 `No Matched Page found` 表示我们还没有适配任何页面。


然后我们就要进入下一步开始适配将主页变成 App 吧！


## 匹配一个网页

点击 `添加新页面` 新建一个页面，匹配URL 填入 `/` 表示这个页面将会匹配主页。

### 添加一个幻灯片控件

1. 在右侧拖入一个 `Carousel` 控件，这是一个幻灯片组件。
2. 依次输入
  * selector: `.top-news .news-item`
  * title: `h1`
  * image: `@background-image`
  * url: `.news-link @href`

再点击 `推送更新` 现在手机是不是自动刷新并且显示了一个幻灯片啦？


### 添加一个文章列表控件

1. 在右侧拖入一个 `List` 组件
2. `sections` 和同级的 `text` 留空
3. `items` 填入 `#articles-list .post`
4. `url` 填入 `@href` `title:` `h1 span` `media:``.post-thumb img` `summary:` `.summary p`


再点击 `推送更新` 现在手机是不是自动刷新并且在幻灯片下面显示了一个文章列表。

### 上面填的值都是什么意思？

* `selector` 指选择每一个 `.top-news .news-item` 元素。
* `image` 的 `@background-image` 指的是使用这个元素的 `style 里面的 background-image 图片`，用这个图片作为幻灯片的图片。
* `title` 填的 `h1` 就是选择这个元素下面的 `h1` 子元素，用这个子元素的文本作为幻灯片标题。
* `url` 填的 `.news-link @href` 表示选择 `.news-link` 这个子元素，并且使用 `@href` 属性的值作为链接地址。


## 适配文章页面

### 新建一个页面

Match URL 中填写 `/*` 再加一个值输入 `/*/*`

ifanr 的文章详情页是 `www.ifanr.com/数字` 和 `www.ifanr.com/栏目/数字` 的形式，这两个规则可以匹配。（一个星号不能匹配 /）

### 添加阅读模式

1. 在右侧拖入一个 `Reader` 组件
2. 分别填写

```title: h1.entry-name
author: .entry-meta .auth a
date: .entry-meta span.date
content: #entry-content
```

3. 推送后，点击一个文章页面是不是就显示阅读模式啦
