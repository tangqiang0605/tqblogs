css技巧

多看mdn。

## 变量设置、获取、修改

--变量

var(变量名，没有变量值时的默认值)

document.querySelector('.pageone').style.setProperty('变量名','变量值');

全局定义在:root选择器中

document.documentElement.style.setProperty();

## 响应式图片

该图片根据条件（媒体查询、类型等）使用source一个图片，最后都不符合使用img。source可以有多个。

``` html
<picture>
    <source>
    <source>
    <img>
</picture>
```

## scroll-snap轮播回弹

父：scroll-snap-type

子：scroll-snap-align

## 空状态选择器

:empty

当根据列表生成时没有内容，显示空状态可以使用该选择器。

## clamp响应式计算高度

clamp函数

## 遮罩改变图片颜色

![image-20230131225956057](D:\tplmydata\tplmydoc\文档图片\image-20230131225956057.png)

## flex中间留空

用margin-left或margin-right:auto。如果使用flex1，会让东西移到中心，margin则不会。

