**文档**是由标记语言组织起来的文本文件。HTML 是最常见的标记语言，但你可能也听说过其他可标记语言，如 SVG 或 XML。实际上，HTML 和 SVG 都是 XML 的子集。

## 标签
HTML 由标签以及其属性值构成。

### 基础标签
-   `<!DOCTYPE html>` — 声明文档类型。仅用于保证文档正常读取。

-   `<html></html>` — 元素包含整个页面的内容，也称作根元素。

-   `<head></head>` — 该元素的内容对用户不可见，其中包含例如面向搜索引擎的搜索关键字、页面描述、CSS 样式表和字符编码声明等。

-   `<meta charset="utf-8">` — 该元素指定文档使用 UTF-8 字符编码，UTF-8 包括绝大多数人类已知语言的字符，没有理由再选用其他编码。`<meta>` 元素。这个元素代表了不能由其他 HTML 元相关元素表示的元数据，比如 [`<base>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/base)、[`<link>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/link)、[`<script>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/script)、[`<style>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/style) 或 [`<title>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/title)。

-   `<title></title>` — 设置页面的标题，显示在浏览器标签页上，也作为收藏网页的描述文字。

-   `<body></body>` — 含页面内容。

### 常用标签
 `<br>` 换行
 `<hr>` 分割线

### 注意事项
一般元素应该包含开始标签、结束标签、内容。除了空标签。

空元素只有一个标签，通常用来在此元素所在位置插入/嵌入一些东西。如 img、input。

HTML 中，无需在一个空元素的标签末尾添加 `/`，例如 `<img src="images/cat.jpg" alt="cat" />`。然而，这也是一种有效的语法，当你希望你的 HTML 是有效的 XML 时，这么做也没问题。

HTML 标签不区分大小写。不过，从一致性、可读性来说，最好仅使用小写字母。

我们要敬畏语义，做到**正确选用元素**。不要使用标题元素来加大、加粗字体，因为标题对于 [无障碍访问](https://developer.mozilla.org/zh-CN/docs/Learn/Accessibility) 和 [搜索引擎优化](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/HTML_text_fundamentals#%e4%b8%ba%e4%bb%80%e4%b9%88%e6%88%91%e4%bb%ac%e9%9c%80%e8%a6%81%e7%bb%93%e6%9e%84%e5%8c%96%ef%bc%9f) 等问题非常有意义。要保持页面结构清晰，标题整洁，不要发生标题级别跳跃。

一个块级元素不会嵌套在一个内联元素里面，但它可能嵌套在另一个块级元素里面。 在这篇文章中提到的“块”和“内联”，不应该与 [CSS 盒子的类型](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/The_box_model#%E5%9D%97%E7%BA%A7%E7%9B%92%E5%AD%90%EF%BC%88block_box%EF%BC%89_%E5%92%8C_%E5%86%85%E8%81%94%E7%9B%92%E5%AD%90%EF%BC%88inline_box%EF%BC%89)中的同名术语相混淆。尽管它们默认是相关的，但改变 CSS 显示类型并不会改变元素的**分类**，也不会影响它可以包含和被包含于哪些元素。防止这种混淆也是 HTML5 摒弃这些术语的原因之一。

无论你在 HTML 元素的内容 (innerContext)中使用多少空格（包括一个或多个空白字符或换行），当渲染这些代码的时候，HTML 解释器会将连续出现的空白字符减少为一个单独的空格符。除非使用 `<pre>` 标签包裹。

## 属性值

属性值的引号
不包含 ASCII 空格（以及 `"` `'` `` ` `` `=` `<` `>` ）的简单属性值可以不使用引号，但是建议将所有属性值用引号括起来，这样的代码一致性更佳，更易于阅读。在目前为止，本章内容所有的属性都是由双引号来包裹。然而，你也许在一些 HTML 中也见过单引号。这只是风格的问题，你可以从中选择一个你喜欢的。如果你想将英文引号（单引号或双引号）当作文本显示在 html 中，你就必须使用 [HTML 实体引用](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Getting_started#%E5%AE%9E%E4%BD%93%E5%BC%95%E7%94%A8%EF%BC%9A%E5%9C%A8_html_%E4%B8%AD%E5%8C%85%E5%90%AB%E7%89%B9%E6%AE%8A%E5%AD%97%E7%AC%A6)。
```html
这样的代码就会破坏显示：
<a title='Isn't'></a>
				
要这样做：
<a title='Isn&apos;t'></a>
```

实体引用
在 HTML 中，字符 `<`、`>`、`"`、`'` 和 `&` 是特殊字符。它们是 HTML 语法自身的一部分（实体）。你可以使用以下字符替代：`&lt;`、`&gt;`、`&quot;`、`&apos;`、`&amp;`。

HTML属性值**引用文件路径**的一些通用规则：
-   若引用的目标文件与 HTML 文件同级，只需直接使用文件名，例如：`my-image.jpg`。
-   若引用的目标文件位于 HTML 文件的**上级**，需要加上两个点。
-   Windows 的文件系统使用反斜杠而不是正斜杠，但这在 HTML 中并不重要。

`title` 属性为超链接声明额外的信息，比如你将链接至的那个页面。例如 `title="The Mozilla homepage"`。当鼠标悬停在超链接上面时，这部分信息将以工具提示的形式显示。title 对于无障碍的意义并不大。所以实际开发中不必把精力花在 title 属性上。

布尔属性
有时你会看到没有值的属性，这也是完全可以接受的。这些属性被称为布尔属性。布尔属性只能有一个值，这个值一般与属性名称相同。

全局属性：所有标签都可以添加的属性。而不是作用域为全局的属性。

lang 全局属性。可以（而且有必要）为站点设定语言。这在很多方面都很有用。如果你的 HTML 文档的语言设置好了，那么你的 HTML 文档就会被搜索引擎更有效地索引（例如，允许它在特定于语言的结果中正确显示），对于那些使用屏幕阅读器的视障人士也很有用（例如，法语和英语中都有“six”这个单词，但是发音却完全不同）。
```
<html lang="zh-CN"></html>
<span lang='ja'></span>
```

type 属性：link 引入 css、favicon 都可以不加 type 属性。

## HTML 头部（元信息）
HTML 头部包含 HTML `<head>` 元素的内容，与 `<body>` 元素内容不同，页面在浏览器加载后它的内容不会在浏览器中显示，它的作用是保存页面的一些元数据。在大型页面中，它的头部会相当大。

### 引入文件
引入 css：
标签：link。
属性：rel、href、type（text/css）可省略。
```
<link rel="stylesheet" href="my-css-file.css" />
```

引入 JavaScript：
标签：script。
属性：src、defer、async。
需要注意：[脚本加载策略](https://developer.mozilla.org/zh-CN/docs/Learn/JavaScript/First_steps/What_is_JavaScript#%E8%84%9A%E6%9C%AC%E8%B0%83%E7%94%A8%E7%AD%96%E7%95%A5)
```
<script src="my-js-file.js" defer></script>
```

### 元数据 
下文只介绍 meta。但元数据不止指 `<meta>` 元素，也指 head 中的任一子标签。

元数据就是描述数据的数据，而 HTML 有一个“官方的”方式来为一个文档添加元数据—— [`<meta>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/meta) 元素。当然，其他在这篇文章中提到的东西也可以被当作元数据。
```
指定字符编码
<meta charset="utf-8" />

添加作者和描述
<meta name="author" content="tangqiang"/>
<meta name="description" content="this website is used to ..."/>
description 和 title 标签将被使用在搜索引擎显示的结果页中。
```
指定一个包括与你的页面内容有关的关键词的描述是有用的，因为它有可能使你的页面在搜索引擎进行的相关搜索中出现得更多（这些行为在术语上被称为：[搜索引擎优化](https://developer.mozilla.org/zh-CN/docs/Glossary/SEO) 或 [SEO](https://developer.mozilla.org/zh-CN/docs/Glossary/SEO)）。

许多 `<meta>` 特性已经不再使用。例如，keyword `<meta>` 元素已经被搜索引擎忽略了，因为作弊者填充了大量关键词到 keyword，错误地引导搜索结果。

在谷歌搜索里，在主页面链接下面，你将看到一些相关子页面——这些是站点链接，可以在 [Google's webmaster tools](https://search.google.com/search-console/about) 配置——这是一种可以使你的站点对搜索引擎更友好的方式:
![[Pasted image 20230326171402.png]]

当你在网站上查看源码时，你也会发现其他类型的元数据。旨在向某个网站提供可使用的特定信息。例如，Facebook 的元数据协议 [Open Graph Data](https://ogp.me/) 和 Twitter 的专有元数据协议 [Twitter Cards](https://developer.twitter.com/en/docs/twitter-for-websites/cards/overview/abouts-cards) 为网站提供了更丰富的元数据。当网站的 URL 显示在 twitter.com 上时，它具有特殊的展示的效果。

### 图标
最简单的方法：
```
<link rel="icon" href="favicon.ico" type="image/x-icon" />
```

自适应图标：
```
<!-- 含有高分辨率 Retina 显示屏的第三代 iPad：-->
<link
  rel="apple-touch-icon-precomposed"
  sizes="144x144"
  href="https://developer.mozilla.org/static/img/favicon144.png" />
<!-- 含有高分辨率 Retina 显示屏的 iPhone：-->
<link
  rel="apple-touch-icon-precomposed"
  sizes="114x114"
  href="https://developer.mozilla.org/static/img/favicon114.png" />
<!-- 第一代和第二代 iPad：-->
<link
  rel="apple-touch-icon-precomposed"
  sizes="72x72"
  href="https://developer.mozilla.org/static/img/favicon72.png" />
<!-- 不含高分辨率 Retina 显示的 iPhone、iPod Touch 和 Android 2.1+ 设备：-->
<link
  rel="apple-touch-icon-precomposed"
  href="https://developer.mozilla.org/static/img/favicon57.png" />
<!-- 基本 favicon -->
<link
  rel="icon"
  href="https://developer.mozilla.org/static/img/favicon32.png" />
```

如果你的网站使用了内容安全策略（Content Security Policy，CSP）来增加安全性，这个策略会应用在 favicon 图标上。如果你遇到了图标没有被加载的问题，你需要确认 [`Content-Security-Policy`](https://developer.mozilla.org/zh-CN/docs/Web/HTTP/Headers/Content-Security-Policy) 响应头的 [`img-src` 指令 (en-US)]( https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy/img-src "Currently only available in English (US)") 没有阻止访问图标。

## 排版
### 标题
对网页建立索引的搜索引擎将标题的内容视为影响网页搜索排名的重要关键字。没有标题，你的网页在[搜索引擎优化](https://developer.mozilla.org/zh-CN/docs/Glossary/SEO)方面效果不佳。

建议：
最好只对每个页面使用一次 `<h1>`。

请确保在层次结构中以正确的顺序使用标题。

在现有的六个标题层次中，除非觉得有必要，否则应该争取每页使用不超过三个（写 makedown 也是）。

### 列表
普通列表：ol、ul、li。普通列表常用于重复元素或相近元素的布局中，这是非常明智的选择。比如在卡片、列表、表单中使用 `li` 标签。

描述列表：dl、术语 dt、描述 dd。一个术语 dt 的描述 dd 可以有多个。描述列表并不常用。
```
<dl>
  <dt>内心独白</dt>
    <dd>戏剧中，某个角色对自己的内心活动或感受进行念白表演，这些台词只面向观众，而其他角色不会听到。</dd>
  <dt>语言独白</dt>
    <dd>戏剧中，某个角色把自己的想法直接进行念白表演，观众和其他角色都可以听到。</dd>
  <dt>旁白</dt>
    <dd>戏剧中，为渲染幽默或戏剧性效果而进行的场景之外的补充注释念白，只面向观众，内容一般都是角色的感受、想法、以及一些背景信息等。</dd>
</dl>
```

### 标记
在 HTML 中我们用 [`<em>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/em)（emphasis）元素来标记特殊的情况。这样做既可以让文档读起来更有趣，也可以被屏幕阅读器识别，并以不同的语调发出。浏览器默认该元素样式为斜体，但你不应该纯粹为了获得斜体风格而使用这个标签。为了获得斜体样式，你应该使用 [`<span>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/span) 元素和一些 CSS，或者是 [`<i>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/i) 元素。

`<strong>` 和 `<b>` 元素同上。

仅仅影响表象而且没有语义的元素，被称为**表象元素**并且不该被使用。因为正如我们在之前看到的，**语义对无障碍、SEO（搜索引擎优化）等非常重要**。最好的经验法则：只有在没有更合适的元素时，才适合使用 `<b>`、`<i>` 或 `<u>` 来表达传统上用粗体、斜体或下划线表达的意思；而通常是有的。`<strong>`、`<em>`、`<mark>` 或 `<span>` 可能是更加合适的选择。要始终保持无障碍的心态。

斜体的概念对使用屏幕阅读器的人或使用拉丁字母以外的书写系统的人没有什么帮助。

人们强烈地将下划线与超链接联系起来。因此，在网页中，最好只给链接加下划线。

-   [`<i>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/i) 被用来传达传统上用斜体表达的意义：外国文字，分类名称，技术术语，一种思想……
-   [`<b>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/b) 被用来传达传统上用粗体表达的意义：关键字，产品名称，引导句……
-   [`<u>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/u) 被用来传达传统上用下划线表达的意义：专有名词，拼写错误……

### 语义文本元素
以下内容并不常用。

引用：如果一个块级内容（一个段落、多个段落、一个列表等）从其他地方被引用，你应该把它用 [`<blockquote>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote) 元素包裹起来表示，并且在 [`cite`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/blockquote#attr-cite) 属性里用 URL 来指向引用的资源。如果是行内内容，使用 `<q>` 以及它的 cite 属性。另外还有一个 cite 标签。三者了解即可。

 [`<abbr>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/abbr) ——它常被用来包裹一个缩略语或缩写，并且提供缩写的解释。
 ```
<abbr title="夏季奥林匹克运动会">奥运会</abbr>
```

HTML 有个用于标记联系方式的元素——[`<address>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/address)。它仅仅包含联系方式

当你使用日期、化学方程式、和数学方程式时会偶尔使用上标和下标，以确保它们的正确含义。[`<sup>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/sup) 和 [`<sub>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/sub) 元素可以解决这样的问题。

计算机代码相关：
-   [`<code>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/code)：标记代码。
-   [`<pre>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/pre)：用于保留空白字符（通常用于代码块）——如果文本中使用了缩进或多余的空白，浏览器将忽略它，你将不会在呈现的页面上看到它。但是，如果你将文本包含在 `<pre></pre>` 标签中，那么空白将会以与你在文本编辑器中看到的相同的方式渲染出来。
-   [`<var>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/var)：变量名。
-   [`<kbd>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/kbd)：键盘等设备的输入。
-   [`<samp>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/samp)：输出。

HTML 还支持将时间和日期标记为可供机器识别的格式的 [`<time>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/time) 元素，例如：
```
<!-- 标准简单日期 -->
<time datetime="2016-01-20">20 January 2016</time>
<!-- 只包含年份和月份-->
<time datetime="2016-01">January 2016</time>
<!-- 只包含月份和日期 -->
<time datetime="01-20">20 January</time>
<!-- 只包含时间，小时和分钟数 -->
<time datetime="19:30">19:30</time>
<!-- 还可包含秒和毫秒 -->
<time datetime="19:30:01.856">19:30:01.856</time>
<!-- 日期和时间 -->
<time datetime="2016-01-20T19:30">7.30pm, 20 January 2016</time>
<!-- 含有时区偏移值的日期时间 -->
<time datetime="2016-01-20T19:30+01:00">7.30pm, 20 January 2016 is 8.30pm in France</time>
<!-- 提及特定周 -->
<time datetime="2016-W04">The fourth week of 2016</time>
```
不同的格式不容易被电脑识别——假如你想自动抓取页面上所有事件的日期并将它们插入到日历中，[`<time>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/time) 元素允许你附上清晰的、可被机器识别的时间或日期来实现这种需求。

### 链接
超链接使我们能够将我们的文档链接到任何其他文档（或其他资源），也可以链接到文档的指定部分。URL 可以指向 HTML 文件、文本文件、图像、文本文档、视频和音频文件等任何其他内容的网络资源。如果浏览器不知道如何显示或处理文件，它会询问你是否要打开文件（选择合适的本地应用）或下载文件（以后处理它）。

url 与路径：统一资源定位符（Uniform Resource Locator，URL）是一个定义了在网络上的位置的一个文本字符串。例如，Mozilla 的简体中文主页位于 `https://www.mozilla.org/zh-CN/`。URL 使用**路径**查找文件。路径指定文件系统中你感兴趣的文件所在的位置。

a 标签：跳转本页锚点、他页锚点、其他页面。
```
<p>到指定页的<a href="contacts.html#Mailing_address">指定锚点</a>。
</p>
```

**绝对 URL**：指向由其在 Web 上的绝对位置定义的位置，包括[协议](https://developer.mozilla.org/zh-CN/docs/Glossary/Protocol)和[域名](https://developer.mozilla.org/zh-CN/docs/Glossary/Domain_name)。
**相对 URL**：指向与你链接（即正在访问）的文件相关的位置。

链接文本建议：
-   不要重复 URL 作为链接文本的一部分。
-   不要在链接文本中说“链接”或“链接到”。
-   尽量减少相同文本的多个副本链接到不同地方的情况。比如，存在多个“单击此处”。
-   链接到非 HTML 资源——留下清晰的指示。当链接到一个需要下载的资源（如 PDF 或 Word 文档）或流媒体（如视频或音频）或有另一个潜在的意想不到的效果（打开一个弹出窗口），你应该添加明确的措辞，以减少混乱。

类型
- 当你链接到要下载的资源而不是在浏览器中打开时，你可以使用 `download` 属性来提供一个默认的保存文件名。
```
<a href="https://download.mozilla.org/?product=firefox-latest-ssl&os=win64&lang=zh-CN"
   download="firefox-latest-64bit-installer.exe">
  下载最新的 Firefox 中文版 - Windows（64 位）
</a>
```

当点击一个链接或按钮时，可能会开启新的邮件的发送而不是连接到一个资源或页面。这种场景可以使用 [`<a>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a) 元素和 `mailto:` URL 协议实现。
```
<a href="mailto:nowhere@mozilla.org">向 nowhere 发邮件</a>
```
实际上，电子邮件地址是可选的。如果你省略了它（也就是说，你的 [`href`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/a#attr-href) 属性仅仅只是简单的“mailto:”），发送新的电子邮件的窗口也会被用户的邮件客户端打开，只是没有收件人的地址信息，这通常在“分享”链接是很有用的，用户可以给他们选择的地址发送邮件。
事实上，任何标准的邮件头字段可以被添加到你提供的 `mailto` URL 中。其中最常用的是主题（subject）、抄送（cc）和主体（body）（这不是一个真正的标头字段，但允许你为新邮件指定一个简短的内容消息）。每个字段及其值被指定为查询项。
```
<a
  href="mailto:nowhere@mozilla.org?cc=name2@rapidtables.com&bcc=name3@rapidtables.com&subject=The%20subject%20of%20the%20email&body=The%20body%20of%20the%20email">
  发送含有 cc、bcc、主题和主体的邮件
</a>
```
每个字段的值必须使用 URL 编码，即，使用[百分号转义的](https://zh.wikipedia.org/wiki/%E7%99%BE%E5%88%86%E5%8F%B7%E7%BC%96%E7%A0%81)非打印字符（不可见字符如制表符、换行符、分页符）和空格。

### 页面结构
页眉header
通常横跨于整个页面顶部有一个大标题 和/或 一个标志。这是网站的主要一般信息，通常存在于所有网页。

导航栏nav
指向网站各个主要区段的超链接。通常用菜单按钮、链接或标签页表示。类似于标题栏，导航栏通常应在所有网页之间保持一致，否则会让用户感到疑惑，甚至无所适从。许多 web 设计人员认为导航栏是标题栏的一部分，而不是独立的组件，但这并非绝对；还有人认为，两者独立可以提供更好的 [无障碍访问特性](https://developer.mozilla.org/zh-CN/docs/Learn/Accessibility)，因为屏幕阅读器可以更清晰地分辨二者。

主内容main
主内容中还可以有各种子内容区段，可用 [`<article>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/article)、[`<section>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/section) 和 [`<div>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/div) 等元素表示。

警告
div 元素非常便利但容易被滥用。由于它们没有语义值，会使 HTML 代码变得混乱。要小心使用，只有在没有更好的语义方案时才选择它，而且要尽可能少用，否则文档的升级和维护工作会非常困难。

侧边栏
[`<aside>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/aside)：侧边栏，经常嵌套在 [`<main>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/main) 中。
一些外围信息、链接、引用、广告等。通常与主内容相关（例如一个新闻页面上，侧边栏可能包含作者信息或相关文章链接），还可能存在其他的重复元素，如辅助导航系统。

页脚footer
横跨页面底部的狭长区域。和标题一样，页脚是放置公共信息（比如版权声明或联系方式）的，一般使用较小字体，且通常为次要内容。还可以通过提供快速访问链接来进行 [SEO](https://developer.mozilla.org/zh-CN/docs/Glossary/SEO)。

## HTML调试
写代码和调试的关键其实是：熟悉语言本身和相关工具。

开发者工具：每一个现代网络浏览器都包含一套强大的开发工具套件。这些工具可以检查当前加载的 HTML、CSS 和 JavaScript，显示每个资源页面的请求以及载入所花费的时间。

**如何打开它？有三种方式：**
-   **_键盘快捷键_** _Ctrl + Shift + I_
-   **_菜单栏_**
-  **右键菜单**

HTML 的语法是宽松的，检查 HTML 文件语法的最好的方法就是让你的 HTML 页面通过 [Markup Validation Service](https://validator.w3.org/)。网页可以接受网址、上传一个 HTML 文档，或者直接输入一些 HTML 代码。



>参考
>
>MDN：[开始学习 HTML - 学习 Web 开发 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Learn/HTML/Introduction_to_HTML/Getting_started)