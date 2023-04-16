## 个人实践

一般不可继承的属性写在`*,*::before,*::after`选择器里。可继承的属性写在`html`里。

接下来不是reset部分了，而是网站的个性部分：:root写变量，body以及其他标签写基础的网站个性样式。所有统称为base。

``` css
// base.css
// 直接复制粘贴使用
:root {
    --font-primary:'Lato',sans-serif;
}
*,*::before,*::after {
    margin:0;
    padding:0;
    box-sizing:inherit;
}
html {
    box-sizing:border-box;
    font-size:62.5%;
    媒体查询设置font-size
}
body {
    // body里的内容没用要求，这里拿font-family的例子作为变量引用的示例。
    font-family:var(--font-primary);
}
```

## reset库

在jq22.com中有reset库的link标签，直接引用或下载使用都很方便。

## 重置css原理

1. 起初复杂的reset是为了使页面在不同的浏览器上显示相同的效果，由于浏览器页面展示越来越一致，不需要大篇的重置以及样式统一的css文件了。现在已经不需要这样做了。现在的reset则是为了去除一些不必要的样式，使得网页设计更加还原。
2. 所有元素都有但是不能被继承的写在*。
3. 所有元素都有可以继承的属性写在body，比如字体

![image-20230127100808790](D:\tplmydata\tplmydoc\文档图片\image-20230127100808790.png)

5. *不包含伪类元素，所以下面是一个更好的配置。以及使用了继承的力量。

![image-20230128111635778](D:\tplmydata\tplmydoc\文档图片\image-20230128111635778.png)

盒子模型一般选为border-box，即使是使用padding、border扩充盒子，**不加宽高**，和content-box的效果一样（盒子扩大了）。所以border-box符合当下的工作方式。

## 