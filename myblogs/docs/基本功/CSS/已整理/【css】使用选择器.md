[CSS 选择器 | 菜鸟教程 (runoob.com)](https://www.runoob.com/cssref/css-selectors.html)

## 选择器权重

权重根据大括号前的内容确定，每对逗号之间是一个选择器。n个选择器加起来是最终结果？？？

100：id

10：类、伪类、属性

1：元素、伪元素

![image-20221231111820871](D:\tplmydata\tplmydoc\文档图片\image-20221231111820871.png)

补充：

继承选择器的权重是0.1或没有权重，

!important是无穷大，

关系选择器是0

通配符选择器是0

## 具体选择器

行内（权重1000）

id选择器（100）
#idName

类名（10）
**.className**

标签（1）
body

全域（0）
*

## 结构选择器

关系选择器

父子 
father>son {
兄弟
bro+sis{下面最近的一个兄弟，必须紧挨否则选择不到。用~则可以选取后面所有兄弟
后代（又名交集）
grand son {



重复选择器

叠加提10

.my .my {}

header header {}



并集选择器

多个/并集：div，p，li



## 伪类选择器（10)

伪类：元素的其中一个特殊状态

事件
：active被点击时/后会处于该种活跃状态

：focus

：hover悬停之上

：link标签a元素未被点击前

：visited标签a元素被点击后

：lang

hover要这样才生效

1. 子元素 a:hover son
2. 兄弟元素 a:hover +bro
3. after a:hover:after·

父子
：nth-child

``` css
:nth-child(2)
:nth-child(odd)
:nth-child(even)
:nth-child(3n+0)三的倍数
:lasttype
:first-child
:last-child
:not()
:not(last-child)
```

不可视
：after
：before

## 属性选择器(10)

a[href]存在
a[href="http..."]相等
a[href^="以什么开头"]用$则是结尾。

## 元素选择器

如input

## 伪元素选择器(1)

::before

修改input上的placehoder输入提示的颜色，元素::input-

placehoder.

:after选择器认定position:relative为父元素？且该选择器对于同个元素的不同类可以叠加。同一元素的after是叠加的。

:after是css2写法，::after是css3写法。没有区别。使用css2提高兼容性。（我认为是有区别的，伪类选择器是10权重、伪元素只有1，而且同时使用二者应该会起冲突？未尝试）

