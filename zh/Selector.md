# 选择器与取值器

## 选择器

无相使用 CSS 选择器来选择元素，然后使用取值器来提取值。无相还支持高级的 CSS3 选择器。

### 基本选择器

| 选择器 | 作用 |
| ---- | ---- |
| `#ID` | 匹配元素的 id 属性，比如 `#header` 匹配 `<div id=header>`  |
| `.CLASS` | 匹配元素的 class 属性，比如 `.post` 匹配 `<div class="post odd no-ad">`  |
| `TAG` | 匹配元素的 tag `nav` 匹配 `<nav><ul></ul></nav>`  |

### 进阶技巧

示例 HTML

```html
<ul class='articles'>
  <li>
    <article>
      <h2>title</h2>

      <ul class='tags'>
        <li>Computer</li>
        <li>Tech</li>
        <li>Python</li>
      </ul> 
    </article>
  </li>
</ul>

<ul class='pagination'>
  <li>
    <a rel='prev' href=''>上一页</a>
  </li>

  <li> <a>第2页</a> </li>
  <li> <a>第3页</a> </li>
  <li> <a>第4页</a> </li>

  <li>
    <a rel='next' href=''>下一页</a>
  </li>
</ul> 
```

#### `选择器 > 选择器2` 选择亲儿子元素

比如 `#list > li` 只会选择 第一层的 `<li>` 但不会选择 `<ul class=tags>` 下面的 `<li>` 会防止误选中孙子节点，而且还可以加强性能（因为不需要比对孙子元素）建议使用，


#### `[属性] 或者 [属性=值]` 选中是否拥有某个属性，或者属性等于多少

比如上面要选中下一页的链接可以用 `a[ref=next]`


#### `[属性^=XX]` 属性以 `XX` 开头

比如 `div[class^=post_]` 将选中 `class` 以 `post_` 开头的元素。


#### `:first-child :last-child` 选择第一个、最后一个子元素

比如上面要选中下一页的链接可以用 `.pagination > li:last-child a`
上一页 `.pagination > li:first-child a`

#### `:nth-child()` 选择第n个元素

比如上面你想要选中第2个 tag 可以用 `.tags > li:nth-child(2)`


## 取值器

取值器以 `@` 开头，后面跟属性值，或者几个内置取值器。


| 取值器 | 作用 |
| ---- | ---- |
| `@text` | 取元素的 `.innerText` 比如 `h1 @text` 遇到 `<h1><span>hello</span> <em>world</em> agian</h1> ` 时结果是 `hello world again` |
| `@>text` | 取亲儿子元素中的 `text` 节点的值，比如上面同一个例子 `h1 @>text` 取到的只有 `again` 因为 `hello world` 是孙子节点。 |
| `@html` | 取当前元素的 `innerHTML` |
| `@属性值` | 取当前元素的某个属性的值，比如 `@href` 取 'href' 的值 |
| `@background-image` | 取内联 `style` 中的 `background-image: url()` 的值，因为很多站点的幻灯片组件都是用此方法设置图片，所以我写了这么一个特殊的取值器 |


很多情况下你可以忽略取值器，忽略的话将使用默认的取值器


### 默认的取值器

* 链接的（比如列表 和 Tabs 的 url 结尾的属性）默认取值器是 `@href` 
* 图片（比如列表和幻灯片）的默认取值器是 `@src`
* 其它所有情况的默认的取值器 `@text`，