HTML》》》》https://htmlreference.io/ 

CSS》》》》https://cssreference.io/

 JS》》》》https://jgthms.com/javascript-in-14-minutes/

引入css

``` html
<link rel="stylesheet" href="index.css">
```





## html

#### 行内元素、块级元素、空（void）元素

行内元素：span、img、input...

块级元素：div、footer、header、section、p、h1...h6...

空元素：br、hr

display：inline、inline-block、block

inline：不独占一行，不能设置宽高。

inline-block：不独占一行，可以设置宽高。

block：独占一行，可以设置宽高。

### 标签

基础：h1-6、p段落、ul>li、ol>li、a[href]、img[src]、video[src/controls]、audio[src/controls]

常用：div与它的语义化别名（查看【css】命名参考）

表格：table。thead、tr。th。

表单：form。input。

新版：code显示行内代码、pre保留格式，显示代码块。samp程序输出。

``` 
<html>lang
	<meta>charset="UTF-8"
	<meta name="viewport" content="width=device-width, initial-scale=1.0">
	<title>
	<head>
    块元素<div>
    <h1>-<h6>
    <p>段落
    行内元素<span>
    <!--注释-->
    <hr/>分割线
    <img src文件路径width宽度(px)height高度(px)alt提示语title悬浮提示>
    <a href链接地址(文件路径/外网url/电话/下载文件/#id锚点/空字符串页面刷新)target标签页(_self自身窗口_blank新建空白标签页)
    <ul>无序列表type属性值(none无/circle空心圆/disc实心圆/square实心正方形)
    <li>列表项
    <ol>type属性值(1数字/a/A大小写字母/i/I大小写罗马数字)
    <dl>自定义列表<dt>列表标题<dd>列表内容
	<body>
```

使用语义化标签

HTML5新增语义化标签，本质是换了名字的div。

**header头部信息** 

表示页面中一个内容区块或整个页面的标题（页面头部）

**nav导航栏** 

表示页面中导游链接部分（页面导航栏）

**aside侧边栏** 

在article之外的，与article内容相关的辅助信息（侧边栏）

**main内容区域（ie不兼容）**

**section页面分区**

表示页面中的一个内容区块（页面身体）

**article文章详情** 

表示一块与上下文无关的独立的内容

**footer底部信息** 

表示页面中一个内容区快或整个页面的脚注（页面底部）

**figure元素** 

表示一段独立的流内容，使用figcaption元素为其添加标题（第一个获最后一个子元素的位置）

### 表格

``` 
表格
<table> 标签：定义表格
<tr> 标签：表格均有若干行组成使用tr定义
<td> 标签：每行被分割为若干单元格使用td定义
rowspan跨行  ：rowspan 属性规定单元格可横跨的行数。
colspan跨列    ：colspan 属性规定单元格可横跨的列数。
表格属性
border=""表格边框
cellpadding=""单元格内的空间
cellspacing=""单元格之间的空间
rowspan=""合并行
colspan=""合并列
align=""单元格文字左右对齐方式align：left、center、right
valign=""单元格文字上下对齐方式valign：top、middle、bottom
```

### 表单

``` html
<form>
    <label for="blogtitle">博客标题</label>
<input type="text" id="blogtitle"/>

<label for="content">内容</label>
<textarea id="content" cols="30" row="10"></textarea>

<button type="submit">
    提交
</button>
</form>
```



``` 
HTML表单
1.发送表单数据的方式：
标签属性：method
常用值：get  | post

2.向何处发送表单数据：
标签属性：action
<form  method="post" action="xxx.html"></form>

3.表单元素属性
文本输入：
属性值：text,password
作    用：text,表单中键入字母、数字等内容。password，输入密码字段。
size属性：元素的宽度，当 type 为 text 或 password时。
maxlength：type为text 或 password 时，输入的最大字符数

文件选择：
属性值：file
作    用：file,定义了文件选择。

按钮：
属性值：button
作    用：button,定义了普通按钮。

选择：
属性值：checkboxes,radio
作    用：checkboxes,表单复选框。radio,表单单选框。
checked：type为radio或checkbox时，指定按钮是否是被选中

提交按钮：
属性值：submit，image
作    用：submit,定义了提交按钮。image,定义了图片提交按钮。

重置按钮：
属性值：reset
作    用：reset,定义了重置按钮。

HTML下拉列表
select 标签用于声明下来列表
option 标签用于声明列表项


HTML多行文本域
<textarea rows="3" cols="20" maxlength="50" name="demo"></textarea>
可见行数：标签属性：rowsrows 属性规定 textarea 的可见高度。
可见宽度：标签属性：colscols 属性规定 textarea 的可见宽度。
最大长度：标签属性：maxlengthmaxlength 属性规定文本区域的最大长度（以字符计）。
名称：标签属性：namename 属性为文本区规定名称。

表单的高级应用
隐藏域 type="hidden”
只读：readonly=“readonly”
禁用：disabled="disabled"

 HTML语义化表单：
域：使用<fieldset>来定义。将一组表单元素放到域中
域标题：使用<legend>。所谓的域标题就是给创建的域设置个标题。
```

### 路径

     /    根路径
    
    ./     同级路径
    
    ../    上一级路径

### 媒体

video[src/controls]、audio[src/controls]

``` 
<audio>音频标签
标签写法：< audio  src="音频路径" ></audio>
<audio>标签的作用：网页的音频播放器
常用属性：
① src表示音频路径
②controls表示显示播放的控件(如果有自动播放可以不要插件，表背景音乐)
③ autoplay表示自动播放（部分浏览器不支持）
④loop表示循环播放
⑤音频标签目前支持三种格式：mp3,wav,Ogg,muted静音

<video>视频标签
标签写法:< video src="视频路径"></video>
<video>标签的作用：网页的视频播放器
常用属性：
① src表示视频路径
②controls表示显示播放的控件(如果有自动播放可以不要插件，表背景音乐)
③ autoplay表示自动播放（部分浏览器不支持）
④loop表示循环播放
⑤width表示视频控件的宽度 height表示视频控件的高度
muted静音,poster属性海报
```

### 符号

``` 
&trade；TM
&reg；®
&copy；©
&amp；&
&yen；￥
&deg；摄氏度
大于号&gt;小于号&lt;空格&emsp；&nbsp;引号&quot;商标&reg;
```

### 字体

``` html
<em>斜体<strong>粗体<ins></ins>下划线<del></del>删除线<sub></sub>下标<sup></sup>上际<br/>换行
```

### 结构

``` html
<!DOCTYPE html>
<html>
    <head>
        <title>name</title>
    </head>
    <body>
        
    </body>
</html>
```

``` html
<!DOCTYPE html>
<html lang='en'>
    
<head>
    
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width,initial-scale=1.0">
<meta http-equiv="X-UA-Compatible" content="ie=edge">
    
    引入字体
    <link href="https://fonts.googleapis.com/css?family=Lato:100,300,400,700,900" rel="stylesheet">
    
    <link rel="stylesheet" href="css/style.css">
    引入基础样式
    引入图标
    <link rel="shortcut icon" type="image/png" href="img/favicon.png">
    设置标题
    <title>Natours | Exciting tours for adventurous</title>
    </head>
</html>
```

## css

### 属性

box-shadow

参数：整体大小右偏移下偏移、大小、颜色

``` html
属性
color=""水平线颜色
width=""水平线宽度
align=""水平线方向，left左，right右
noshade="noshade"水平线默认阴影消除
align水平对齐方式，取值：left、center、right。
border：设置边框
bgcolor：设置背景颜色

width/height：表格的宽度/表格高度

list-style
background-color
vertical-align:middle;图片与文字的对齐方式
postition
top
left
border-radius
::before
display
background:url() no-repeat -81px 0;
background-size
媒体查询@media only screen and (max-width:800px){}
```

### 单位

1. 微信wxs

2. px像素光点

3. %

4. em：上一层字体的倍数：如body字体10px，则1em=10px。实现行距等比放大。比如p的父元素font-size：10px；然后p设为font-size：1em；line-height：1.5em。root元素默认16px;

5. rem：基于html的字体大小倍数。root em。

6. vw/vh。viewport可视画面大小。vw/vh取值0-100.

7. vmin/vmax：0-100，可视画面最长边可能是宽也可能是高，可视化画面最短边（可能是高/可能是宽）

8. fr：grid布局的单位

### 原子

常用的TailwindCSS类（配合daisyUI）

h-xxx

w-xxx

p-xxx

m-xxx

flex-xxx

text-xxx

font-xxx

shadow

bg-primary?

text-primary-content?

bg-base-100?

rounded-box?

items-stretch

rounded-btn