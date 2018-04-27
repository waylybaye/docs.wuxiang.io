# 相的最佳实践

## 图标的选择

建议按一下优先级选择图标（优先选择正方形的图标）

1. 查看网页源代码，先搜索 `apple-touch-icon` 如果能找到一个或者多个 `<link ref='apple-touch-icon' href='图片地址'>` 则可以使用图片，这种图片是用户在 iOS Safari 中将网站添加到后显示的图标，专门针对 iOS 进行了优化。

这个也如果有多个，会分别提供不同的分辨率，建议选择一个不低于 `100px` 大小的图片

2. 搜索 `icon` 会有 `<link rel="icon" type="image/8" href=""/>` 的标签，这些一般都是方形图标，也可能会多种分辨率的图片，建议选择较大的那个。

3. 如果上面都没有，则可以搜索 `favicon`，如果搜不到记录也可以直接在当前域名后面加上 `http://域名/favicon.ico` 然后尝试访问，这个是网站的默认图标。你用浏览器添加书签后就是显示的这个，但是这个一般非常小，直接用作「相」的图标不太合适 ，非常模糊，不建议使用。

4. 如果网站有 App 可以搜索 `App Store 网站名字` 然后查看其 iOS/Play App Store 的图标。这个图标效果最好。

5. 如果啥都没有, favicon 又太模糊，建议忽略图标字段，让无相自动生成色块图标。