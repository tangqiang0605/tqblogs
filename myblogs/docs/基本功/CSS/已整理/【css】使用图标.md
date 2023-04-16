# 【css】使用图标

## 使用img图片

## 使用csssprite

  ## 使用unicode

------

   unicode是字体在网页端最原始的应用方式，特点是：

   - 兼容性最好，支持ie6+，及所有现代浏览器。
   - 支持按字体的方式去动态调整图标大小，颜色等等。
   - 但是因为是字体，所以不支持多色。只能使用平台里单色的图标，就算项目里有多色图标也会自动去色。

   > 注意：新版iconfont支持多色图标，这些多色图标在unicode模式下将不能使用，如果有需求建议使用symbol的引用方式

   unicode使用步骤如下：

   第一步：拷贝项目下面生成的font-face

   ```js
   @font-face {font-family: 'iconfont';
       src: url('iconfont.eot');
       src: url('iconfont.eot?#iefix') format('embedded-opentype'),
       url('iconfont.woff') format('woff'),
       url('iconfont.ttf') format('truetype'),
       url('iconfont.svg#iconfont') format('svg');
   }
   ```

   第二步：定义使用iconfont的样式

   ```js
   .iconfont{
       font-family:"iconfont" !important;
       font-size:16px;font-style:normal;
       -webkit-font-smoothing: antialiased;
       -webkit-text-stroke-width: 0.2px;
       -moz-osx-font-smoothing: grayscale;}
   ```

   第三步：挑选相应图标并获取字体编码，应用于页面

   ```js
   <i class="iconfont">&#x33;</i>
   ```

## 使用iconfont

解决unicode语义不明问题（多加了一层语义）

1.阿里巴巴矢量图标库iconfont.cn，下载

2. 本地iconfont文件夹放入iconfont.css iconfont.js iconfont.json iconfont.tff

3. 引入

   ``` html
   <link rel="stylesheet" href="iconfont/iconfont.css">
   在head里面
   ```

   4.使用

   ``` 
   <i class="iconfont icon-wift"></i>
   标签是什么都可以。
   第一个是iconfont，第二个在iconfont.css文件中查
   ```
   

##  使用svg（推荐）

阿里巴巴矢量图标库

第一步：拷贝项目下面生成的symbol代码：

```html
//at.alicdn.com/t/font_8d5l8fzk5b87iudi.js
<script src="./js/fonticon.js"></script>
```

第二步：加入通用css代码（引入一次就行。也可以不用）：

```js
<style type="text/css">
    .icon {
       width: 1em; height: 1em;
       vertical-align: -0.15em;
       fill: currentColor;
       overflow: hidden;
    }
</style>
<link rel="stylesheet" href="./css/iconfont.css">
```

第三步：挑选相应图标并获取类名，应用于页面：

```js
<svg class="icon" aria-hidden="true">
    <use xlink:href="#icon-xxx"></use>
</svg>
```

字节跳动图标库

1. 选择图标，生成js，在项目全局引入该js。
2. （可以不用）通过iconpark-icon类设置全局样式（宽高）
3. 复制svg symbol粘贴使用。

```
<svg class="iconpark-icon">
    <use href="#icon-xxx"></use>
</svg>
```

## 使用component

字节跳动为例

```
<script src="https://lf1-cdn-tos.bytegoofy.com/obj/iconpark/icons_22789_2.d74952a3647e8b102c80f214851cdde9.js"></script>

<iconpark-icon name="all-application"></iconpark-icon>
```

## svg图标原理

总文件定义多个symbol

```xml
<svg>
  <symbol viewBox="0 0 24 24" id="heart">
    <path fill="#E86C60" d="M17,0c-1.9,0-3.7,0.8-5,2.1C10.7,0.8,8.9,0,7,0C3.1,0,0,3.1,0,7c0,6.4,10.9,15.4,11.4,15.8 c0.2,0.2,0.4,0.2,0.6,0.2s0.4-0.1,0.6-0.2C13.1,22.4,24,13.4,24,7C24,3.1,20.9,0,17,0z">
    </path>
  </symbol>
  <symbol viewBox="0 0 32 32" id="arrow">
    <path fill="#0f0f0f" d="M16,0C7.2,0,0,7.2,0,16s7.2,16,16,16s16-7.2,16-16S24.8,0,16,0z M22.8,13.6l-6,8C16.6,21.9,16.3,22,16,22 s-0.6-0.1-0.8-0.4l-6-8c-0.2-0.3-0.3-0.7-0.1-1S9.6,12,10,12h12c0.4,0,0.7,0.2,0.9,0.6S23,13.3,22.8,13.6z">
    </path>
  </symbol>
</svg>
```

使用时引用其中一个图标

```
<svg>
    <use xlink:href="#heart"/>
</svg>
```
