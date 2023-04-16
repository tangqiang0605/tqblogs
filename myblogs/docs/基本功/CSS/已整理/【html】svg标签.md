SVG是是用来制作矢量图的 HTML5 标签，用来定义 SVG 图形的容器。

在开发中，使用他人做好的svg图标即可，不需考虑svg标签中的具体细节。

## svg属性

| 属性                               | 必要 | 说明                                                         |
| ---------------------------------- | ---- | ------------------------------------------------------------ |
| xmlns="http://www.w3.org/2000/svg" | √    | 直接使用，不作说明。                                         |
| viewBox                            | √    | 截取大小0-24                                                 |
| fill                               | √    | 背景的颜色                                                   |
| stroke                             | √    | 线条的颜色                                                   |
| width，height                      | √    | svg内容大小                                                  |
| stroke-width                       |      | 线条的宽度                                                   |
| stroke-linecap                     |      | 线条末尾的样式 (默认)butt (圆角)round (方形)square ，round 和 square 会影响线条的长度 |
| opacity                            |      | 不透明度 0~1                                                 |
| fill-rule                          |      | nonzero (非零环绕原则)evenodd                                |
| stroke-dasharray                   |      | 创建虚线数组 x,y,z,… (长度，间隔，长度，间隔等)              |
| stroke-dashoffset                  |      | 偏移                                                         |
| filter                             |      | url(id) 添加滤镜                                             |

更多属性：[SVG 属性参考 - SVG：可缩放矢量图形 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Attribute)

## path标签

作为svg的子dom，在svg的viewBox上作画。

| 属性            | 必要 | 说明           |
| --------------- | ---- | -------------- |
| stroke-linecap  | √    | 线条头部形状   |
| stroke-linejoin | √    | 线条拐角处形状 |
| stroke-width    | √    | 线条宽度       |
| d               | √    | 绘画命令       |

path绘画指令(大小写敏感。大写一般是绝对位置，小写一般是相对位置)

| 指令                      | 说明                                       |
| ------------------------- | ------------------------------------------ |
| M/m (x,y)                 | 移动当前位置                               |
| L/l (x,y)                 | 从当前位置绘制线段到指定位置               |
| H/h (x)                   | 从当前位置绘制⽔平线到达指定的 x 坐标      |
| V/v (y)                   | 从当前位置绘制竖直线到达指定的 y 坐标      |
| Z/z                       | 闭合当前路径                               |
| C/c (x1,y1,x2,y2,x,y)     | 从当前位置绘制三次⻉塞尔曲线到指定位置     |
| S/s (x2,y2,x,y)           | 从当前位置光滑绘制三次⻉塞尔曲线到指定位置 |
| Q/q (x1,y1,x,y)           | 从当前位置绘制⼆次⻉塞尔曲线到指定位置     |
| T/t (x,y)                 | 从当前位置光滑绘制⼆次⻉塞尔曲线到指定位置 |
| A/a (rx,ry,xr,laf,sf,x,y) | 从当前位置绘制弧线到指定位置               |

### 示例

绘制叉号

<svg xmlns="http://www.w3.org/2000/svg" height="100" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
</svg>

```html
<svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
</svg>
```

绘制爱心

<svg xmlns="http://www.w3.org/2000/svg" height="100px" width="100px" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
</svg>

```html
<svg xmlns="http://www.w3.org/2000/svg" style="height:100px;width:100px" fill="none" viewBox="0 0 24 24" stroke="currentColor">
    <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z" />
</svg>
```