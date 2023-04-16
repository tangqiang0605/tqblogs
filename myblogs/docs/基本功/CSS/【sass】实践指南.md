实践：通过html+sass仿写网站的静态首页。

## 搭建

1.lives-erver拓展，在新建的index.html页面中右键使用

2.live sass compiler拓展

第一步、在vscode拓展市场安装

第二步、对插件进行设置

``` json
  "liveSassCompile.settings.formats": [
    {
      "format": "compressed",
      "extensionName": ".min.css",
      "savePath": "./css"
    }
  ],
  "liveSassCompile.settings.excludeList": [
    "**/node_modules/**",
    ".vscode/**"
  ],
  "liveSassCompile.settings.autoprefix": [
    "> 1%",
    "last 2 versions"
      覆盖99%的浏览器、浏览器的最后两个版本
  ],
```

第三步、安装后点右下角即可开启

3.结构

index.html

css

存放生成的css文件、map文件

sass

存放sass文件、其中abstracts存放_mixin.scss、\_variables.scss等文件。一般\_开头的文件只被唯一的主scss文件引入使用。

js文件夹

4.搭建

写入必要的reset、工具js、fonticon、html中图标标题字体css引入js引入、meta响应式标签。



## 架构

sass+bem。[CSS 架构之 BEM - 掘金 (juejin.cn)](https://juejin.cn/post/7021461539236347940)

bem介绍。通过&

## 常用语法

变量

$color:一切可以作为属性值的值;

一般写在sass/abstracts/_variables.scss中被引入。命名方法查看命名参考。



嵌套

子嵌套、伪类嵌套&（&是占位符代表嵌套父名，所以是可以后置的，比如nav&生成nav:after）



导入

@import "abstracts/variables";

导入scss不需后缀，导入css需要后缀。导入后该命令的位置可以看作导入文件的所有内容，然后生成css。所以import后可以直接使用import里的内容，生成的css也是他们组合的结果。



混入

@mixin定义混入、@include引入混入。混入一般放在sass/abstracts/_mixin.scss中



继承

@extend类名。看占位符选择器。生成并集选择器。被继承的类，继承的类1，继承的类2{}。用了占位符则被继承的类不会写出来。

继承比混入简洁。重复的代码多的用继承，重复代码少的用混入。



## 语法

变量

sass与css变量的区别，sass在编译前决定，转为css时变成硬编码，css在运行时决定。sass的计算也是同理。都是为了方便程序员。

``` scss
$color-red:red;
$border-red:1px solid $color-red;
```

嵌套

``` scss
article {
  ~ article { border-top: 1px dashed #ccc }
  > section { background: #eee }
  dl > {
    dt { color: #333 }
    dd { color: #555 }
  }
  nav + & { margin-top: 0 }
}
生成
article ~ article { border-top: 1px dashed #ccc }
article > footer { background: #eee }
article dl > dt { color: #333 }
article dl > dd { color: #555 }
nav + article { margin-top: 0 }
```

父选择器：嵌套+关键字&

``` scss
h1 {
    &:hover{
        
    }
}
生成h1:hover

h2 {
    h1 & {}
}
生成h1 h2{}
```

群组选择器：嵌套+并集选择器

``` scss
输入
.container {
  h1, h2, h3 {margin-bottom: .8em}
}
输出
.container h1, .container h2, .container h3 { margin-bottom: .8em }
输入
nav, aside {
  a {color: blue}
}
输出
nav a, aside a {color: blue}
```

嵌套属性：嵌套

``` scss
nav {
  border: {
  style: solid;
  width: 1px;
  color: #ccc;
  }
}
输出
nav {
  border-style: solid;
  border-width: 1px;
  border-color: #ccc;
}
输入
nav {
  border: 1px solid #ccc {
  left: 0px;
  right: 0px;
  }
}
输出
nav {
  border: 1px solid #ccc;
  border-left: 0px;
  border-right: 0px;
}
```

@import

导入scss不需后缀，导入css需要后缀。

导入后该命令的位置可以看作导入文件的所有内容，然后生成css。所以import后可以直接使用import里的内容，生成的css也是他们组合的结果。



scss使用mixin

![image-20230128202349463](D:\tplmydata\tplmydoc\文档图片\image-20230128202349463.png)



sass

1.选择器嵌套：类嵌套为后代

2.父选择器&：&:hover中&取父名并与父同级

3.属性嵌套

``` css
a {
    font:{
        size:14px;
        family:sans-serif;
        weight:bold;
    }
}
等同
a {
    font-size:14px;
    font-family:sans-serif;
    weight:bold;
}
```

4.占位符选择器：%base继承。其实是用于取别名。

写在类名后面，该类不会被编译

而其他类中以@extend %base引入，作为子代继承。

.button@base

.btn中使用。

编译为.button .btn{button类的属性}和.btn{原来btn类里的其他属性}



继承@extend类名。看占位符选择器。生成并集选择器。被继承的类，继承的类1，继承的类2{}。用了占位符则被继承的类不会写出来。

继承比混入简洁。重复的代码多的用继承，重复代码少的用混入。



变量

&变量名

变量类型

变量后缀!default/!global



@import 

原生@import url(css.css);

sass中写自己的import导入sass文件可以使用其中的变量，用原生import导入不行，但是会出现在编译的文件里。![image-20230126095522439](D:\tplmydata\tplmydoc\文档图片\image-20230126095522439.png)



声明混入@mixin，在类中@include使用混入。![image-20230126104402622](D:\tplmydata\tplmydoc\文档图片\image-20230126104402622.png)

![image-20230126104623252](D:\tplmydata\tplmydoc\文档图片\image-20230126104623252.png)

![image-20230126104723215](D:\tplmydata\tplmydoc\文档图片\image-20230126104723215.png)



运算

加减，一方缺省没有单位则使用另一方的单位。

乘法最多只能有一方有单位。

除不一定会执行。而是作为分隔符原样照搬。解决方法：加个括号

![image-20230126110054159](D:\tplmydata\tplmydoc\文档图片\image-20230126110054159.png)



插值

#{变量}，将其值作为文本原原本本地粘贴到所在位置。



问题、注意

1. 属性嵌套要加空格，注意格式，不然会报错。
2. 引入的文件加不加下划线前缀都一样。
3. 下划线和横线是一样的。