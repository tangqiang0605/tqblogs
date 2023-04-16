临摹网页的经验。包括在实际开发中遇到的问题、工具、方法、建议。包括接单方法、参考网站、文档、测量工具、使用字体、字体图标、颜色、图片资源等。

工具一般放在cube。浏览器搜索框输入c加tab回车打开。

spacingjs在css/工具库中。snipaste使用win+q搜索名字打开。

1.图片2图标3字体4开始

## 一、图片资源

1. 下载图片

- 使用edge插件或火狐下载图片。
- 校对和筛选图片。
- 将图片放在img目录下。
- 引入图片并测试

2. 引入图标

- 新建图标库。
- 半屏选择图标，全屏查看疏漏
- 引入svg并测试

## 二、引入字体

- 查看源代码/下载获得字体
  - link标签中以css引用
  - css文件中通过import导入


大多数网站都是通过链接引用自己或他人的字体，没见过是放在本地的。

- 引入并测试

## 三、网站信息

- 引入网站图标
  - type类型为short icon的link


``` html
    <link rel="shortcut icon" type="image/x-icon" href="assets/img/favicon.png"/>
```

- 设置网站名字

ctrl+u查看页面源码，ctrl+f搜索可以找到对应内容。icon、title。

``` html
示例
title
<title ng-bind="document_title">Listen 1</title>
icon
<link href="images/logo_16.png" rel="shortcut icon" />
```

小技巧：某些网站可以通过网址根地址/favicon.ico获得网站图标。如果没有，查看页面源码。

## 四、reset.css

详细查看【css】重置样式。

一般不可继承的属性写在`*,*::before,*::after`选择器里。可继承的属性写在`html`里。

接下来不是reset部分了，而是网站的个性部分：:root写变量，body以及其他标签写基础的网站个性样式。所有统称为base。

``` css
// base.css
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

## 五、颜色变量字体变量其他变量

命名规则：查看【css】命名参考。颜色可以直接在源代码找。或者直接从网页上取。

## 六、实用工具

图标库：cubox样式资源 heroicons

使用spacingjs

工具：检查>控制台，输入spacingjs。

测量：移动鼠标+alt。如果不行鼠标右键再alt（这是因为焦点不在网站里面）

使用snipaste：取色

浏览器开发者工具/调试

f12或Ctrl+Shift+C读取页面的原始数据比如渐变色

ctrl+u查看页面源码

图片助手(ImageAssistant)：浏览器插件，扒图

iconfont.cn：svg图标

font100：字体

[Bootstrap 优站精选 (bootcss.com)](https://expo.bootcss.com/)网站参考（客户）

[网页模板,网站模板,DIV+CSS模板,企业网站模板下载-模板之家 (cssmoban.com)](http://www.cssmoban.com/)网站参考（开发）

cube：工具一般放在cube。浏览器搜索框输入c加tab回车打开。

## 七、接单计划

1.练习css并发布在小红书上

2.写在md上的问题，制作问卷

## 八、sass

1. 配置vscode的sass插件（具体查看有关sass的笔记）

2. 建页面文件引入必要的其他页面

如home.sass引入reset.css、_abstracts.sass@import导入开头为下划线的文件

``` scss
@import "abstracts";
@import "../css/reset.css";
```

3. 选择器思路

一般内部样式和外边距分开，外边距以`组件__box命名`。其他如`组件__text-title--red`。

每个区块都有自己的字体开头，如果与前面区块的相同，用引入的方法。

``` scss
.banner {
    &__content {
        @extend .header__content;
    }
}
```

 如果出现extend，可以考虑把.header__content的内容放到\_typography.scss或\_utilities.scss中。



