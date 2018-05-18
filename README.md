# 无相文档

<img src="https://is5-ssl.mzstatic.com/image/thumb/Purple128/v4/dd/5d/8e/dd5d8ed6-3642-7e77-eebf-457c6a243c9e/AppIcon-1x_U007emarketing-85-220-6.png/246x0w.jpg" width=128/>

[![无相 on AppStore](https://linkmaker.itunes.apple.com/assets/shared/badges/zh-chs/appstore-lrg.svg "View on App Store")](https://itunes.apple.com/cn/app/id1331533746?mt=8?ct=docs&mt=8)


## 什么是无相

网站虽千变万化，但其本质都是一样的，由一个个的 `列表,标签页,图片` 等基础组件组合而来。 无相就是忽略其表相，将其重新解构成一个个的组件，提取出来数据后使用原生的组件重新渲染这些数据。 从而既可以消除噪音，又可以提升性能，以及节省流量。


「无相」是一个应用引擎，或者类似微信小程序的一个“平台”。实现了一些常用的组件，比如 `标签页、列表、阅读模式` 等，当无相访问一个网站时，会查找是否有某一个「相」可以适配该网站（通过域名比对），如果有的话继续查找这个「相」中是否有某一个页面匹配了当前访问的 URL。 如果找到的话无相就会根据「相」的规则从 HTML 中提取出来信息后使用指定的布局和组件渲染成原生的页面。


「相」是无相的配置文件，做的就是教无相怎么解构某一个网站的数据，并且重新渲染。


## 如何制作相

✅  文章已完成 ⚠️  部分完成 ⭕️ 尚未开始


### 已具备 HTML/CSS 相关经验

1. [从 0 创建 ifanr 网站的客户端 ✅](./zh/GetStarted.md)
    * 注册无相账号
    * 填写基本信息
    * 适配一个页面
2. [相的基本介绍 ⚠️](./zh/Editor.md)
    * 相的基本信息
    * 相的域名匹配规则
    * 网页匹配规则
3. [选择器和取值器 ✅](./zh/Selector.md)
    * 选择器：如何选择元素和高级选择器技巧
    * 取值器：查看各种 `@` 的取值器
4. [无相的控件文档 ⭕️](./zh/Components.md)
5. [相的建议](./zh/Common.md)
    * 相图标的选择 (apple-touch-icon, icon, favicon)
6. [相配置实例](./zh/Demo.md)
    * Discuz
7. 常见问题
    * 如何知道一个网站是不是静态加载的？
    * 为什么明明正确的 CSS 规则，「无相」取不到数据？
    * UA 使用 PC 还是 移动网站？


## 常见问题

### 如何制作 RSS 的相

1. 新建一个应用
2. 起始地址中填入 RSS 地址，如 `https://sspai.com/feed`
3. 新建一个页面再匹配地址中填入上面的路径名比如上面这个就是 `/feed`，页面类型选择 `RSS` 保存，完成！


#### 如何知道一个网站是不是静态加载的？

最简单的办法：查看网页源代码，然后搜索你在网页里面看到的关键词，试试能不能搜索的到。比如你看到一个网站“iPhone XXX" 然后再源代码中搜索 iPhone 如果能看到对应的代码那么「无相」就可以提取出来。


#### 为什么明明正确的 CSS 规则，「无相」取不到数据？

有两种可能

1. HTML 是动态加载的，比如你打开少数派的首页，虽然你能看到文章列表的样式，但是它的内容都是 AJAX 动态加载的，所以取不到数据。

2. User Agent 原因：适配网站时一定要选择正确的 UA，因为大部分网站都会针对 PC和手机版使用不同的模板，「无相」默认使用手机版的 UA，而你用 Chrome 开发者工具查看网页结构时一定不要忘了切换到 `移动模式` 后刷新。


### 使用 PC 还是 移动网站？

这个要看具体情况，一般情况下重视移动端的公司移动版会做的很好，那就更有可能使用比较炫酷的技术，网站动态加载的可能性就更大。而 PC 版一般会显示更多的信息。

不过新闻资讯类网站很依赖 SEO，所以大部分都是静态站。
