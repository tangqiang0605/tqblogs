### 自定义类CurrentLine说明

| 绘制配置     | 可以使用 |                                      |
| ------------ | -------- | ------------------------------------ |
| setCanvas    | √        | 静态方法，画板设置                   |
| setBGColor   | √        | 静态方法，设置橡皮擦颜色             |
| setGDuration |          | 静态方法，设置全局单位长度的绘画时间 |
| setDuration  |          | 一单位长度的绘画时间                 |
| getDuration  |          |                                      |
| setAnimate   |          |                                      |
| getAniamte   |          |                                      |
| setLineWidth |          |                                      |
| getLineWidth |          |                                      |

| 创建电路             |      |                                                  |
| -------------------- | ---- | ------------------------------------------------ |
| 类构造器             | √    | 初始化变量以及调用画板设置、根据指令获取点、绘制 |
| drawer               |      | 绘制                                             |
| drawWithNoAnimate    |      | 无逐帧绘制                                       |
| doPolylinesAnimation |      | 逐帧绘制。修改过的方法。                         |


| 电路控制     |      |                                                 |
| ------------ | ---- | ----------------------------------------------- |
| getState     |      | 获取电路状态                                    |
| setState     |      | 设置电路状态                                    |
| setFreeState |      | 设置电路不受父电线影响时的状态                  |
| getFreeState |      | 获取电路不受父电线影响时的状态                  |
| off          | √    | 设置电路状态                                    |
| on           | √    | 设置电路状态                                    |
| off          | √    | 静态方法，输入一个数组，批量关闭                |
| on           | √    | 静态方法，输入一个数组，批量开启                |
|              |      |                                                 |
| detect       |      | 检查电路状态                                    |
| setFrom      |      | 设置父电路，并在父电路中设置该电路为子电路      |
| setOnFrom    | √    | 设置父电路                                      |
| setOffFrom   | √    | 设置父电路                                      |
| getFather    |      | 获取父电路，返回一个属性为onFrom和offFrom的对象 |
| addOn        | √    | 设置子电路，返回子电路                          |
| addOff       | √    | 设置子电路，返回子电路                          |
| addOnBrach   | √    | 设置子电路，返回本电路                          |
| addOffBrach  | √    | 设置子电路，返回本电路                          |
| getSon       |      | 获取子电路，返回一个属性为to的对象              |

| 辅助函数        |      |                                                 |
| --------------- | ---- | ----------------------------------------------- |
| initPoints      |      | 根据构造函数的trace获得this.points和this.length |
| filterFather    |      | detect中获取所有开启的父电线的辅助方法          |
| typeOf          |      | 判断类型                                        |
| getColorByState |      | 根据状态获得颜色                                |



创建一个CurrentLine（电线）类：
**new CurrentLine(ctx,trace,state=0,animate=true);**

ctx电线所在canvas上下文。

trace字符串，绘图指令，例如”x200y200u200r10“表示从(200,200)开始，向上绘制200距离，然后向右绘制10距离。指令有x坐标、y坐标，上u下d左l右r，均为小写。

state电线初始状态：默认0关闭。

animate:绘制电线的方式：是否为逐帧绘制。默认是。



手动改变状态：开启或关闭

const line1=new CurrenLine(ctx,'x0y0r100d100');

**line1.on();**

**line1.off();**

电线绑定父电线后不应该再手动改变。



自动改变状态：绑定其他电线

**电线对象2.setOnFrom(电线对象1);**

当电线对象1开启时，电线对象2也开启。

**电线对象2.setOffFrom(电线对象3);**

当电线对象3开启时，电线对象2关闭。



电线对象2.setOnFrom(电线对象1);

电线对象2.setOffFrom(电线对象3 ,2);

电线对象1和3同时开启时，通过设置优先级（大于等于1）避免冲突。默认1。此处电线对象3优先级为2，电线13同时开启时电线2关闭。



可以添加一个电线对象数组

**line2.setOnFrom([line1,line3,lin4]);**

line2.setOnFrom(line5);

line2.setOffFrom([line6,line7] , 2 );

一、在”line6和line7没有同时开启“的条件下，二、“ line5开启 ”或” line1、line3、line4同时开启 ”，line2就开启。



获取所有绑定的电线

getFather()返回一个属性为onFrom和offFrom的普通对象。

获取被绑定的电线

getSon()返回一个属性为to的普通对象。



其他函数：

是否逐帧绘制：

setAnimate(boolen);

getAnimate();

设置绘画花费时间，animate开启才有效

setDuration(number);

getDuration();

设置线条宽度

setLineWidth(number);

getLineWidth();

