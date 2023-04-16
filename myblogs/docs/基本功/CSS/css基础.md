## 介绍
层叠样式表（Cascading Style Sheet）是为网页添加样式的代码。和 HTML 类似，CSS 也不是真正的编程语言，甚至不是标记语言。它是一门样式表语言，这也就是说人们可以用它来选择性地为 HTML 元素添加样式。例如，更改内容的字体、颜色、大小和间距，将其拆分为多个列，或添加动画和其他装饰功能。

在 MDN 上的 [CSS reference](https://developer.mozilla.org/zh-CN/docs/Web/CSS/Reference) 页面列举了所有的 CSS 属性页面。

当你想要寻找一个 CSS 特性的更多内容时，多使用你的搜索引擎来搜索 "mdn _css-feature-name_" 。例如，搜索 "mdn color" 和 "mdn font-size"！

让所有的浏览器都同时支持一个 CSS 新特性是不现实的，通常都会一个空档期——一些浏览器已经支持而另一些仍未支持。因此，查看特性的实现状态是非常有用的。在 MDN 上的每个属性的页面中都标有它们对应的状态，你可以通过这种方法来查看你是否可以去使用它。

## 引入 css
```html
<head>
	内部样式
	<style>
		h1 {
			color:yellow;
		}
	</style>
	外部样式
	<link href="styles/index.css" rel="stylesheet" type="text/css">
</head>
<body>
	内联样式
	<h1 style="color:red">hello</h1>
</body>
```

浏览器会拉取该 HTML 相关的大部分资源，比如嵌入到页面的图片、视频和 CSS 样式。JavaScript 则会稍后进行处理
1.  浏览器拉取到 CSS 之后会进行解析，根据选择器的不同类型（比如 element、class、id 等等）把他们分到不同的“桶”中。浏览器基于它找到的不同的选择器，将不同的规则（基于选择器的规则，如元素选择器、类选择器、id 选择器等）应用在对应的 DOM 的节点中，并添加节点依赖的样式（这个中间步骤称为渲染树）。
2.  上述的规则应用于渲染树之后，渲染树会依照应该出现的结构进行布局。
![css]( https://developer.mozilla.org/en-US/docs/Learn/CSS/First_steps/How_CSS_works/rendering.svg )

当浏览器遇到无法解析的 CSS 选择器或声明的时候会发生什么呢？答案就是浏览器什么也不会做，继续解析下一个 CSS 样式！相似的，当浏览器遇到无法解析的选择器的时候，他会直接忽略整个选择器规则，然后解析下一个 CSS 选择器。
```
.box {
  width: 500px;
  width: calc(100% - 50px);
}
```

## 规则集
一个 css 文件是 css 规则集的集合。
**规则集**（通常简称“规则”）由以下部分构成：
![规则集](https://developer.mozilla.org/en-US/docs/Learn/Getting_started_with_the_web/CSS_basics/css-declaration-small.png)
选择器（**Selector**）
在这个例子中就是 `p` 元素。

声明（**Declaration**）
一个单独的规则，如 `color: red`。**以分号结尾。**

属性（**Properties**）
本例中 `color` 就是 [`<p>`](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/p) 元素的属性。

属性的值（Property value）
在属性的右边，冒号后面即**属性的值**。

## @规则
```
@import 'styles2.css';
```
```
@media (min-width: 30em) {
  body {
    background-color: blue;
  }
}
```

## 选择器
元素选择器：`p` 选择 `<p>`。

id 选择器：单一页面中，每个 ID 只对应一个元素。`#my-id` 选择 `<p id="my-id">`。

类选择器：单一页面中，一个类可以有多个实例。`.my-class` 选择 `<p class="my-class">` 和 `<a class="my-class">`。

属性选择器：`img[src]` 选择 `<img src="myimage.png">` 而不是 `<img>`。

伪（Pseudo）类选择器：特定状态下的特定元素（比如鼠标指针悬停）。`a:hover` 仅在鼠标指针悬停在链接上时选择 `<a>`。之所以称为伪类，是因为它的选择器优先级与类选择器相同。

[CSS 选择器 - 学习 Web 开发 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Building_blocks/Selectors)

选择器示例
```
h1
a:link
.manythings
#onething
*
.box p
.box p:first-child
h1, h2, .intro
```

属性值常见函数
cacl
rotate
url

## 速记属性

一些属性，如 [`font`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/font), [`background`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/background), [`padding`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/padding), [`border`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/border), and [`margin`](https://developer.mozilla.org/zh-CN/docs/Web/CSS/margin) 等属性称为速记属性--这是因为它们允许您在一行中设置多个属性值，从而节省时间并使代码更整洁。

> 参考
> 
> https://developer.mozilla.org/zh-CN/docs/Web/CSS