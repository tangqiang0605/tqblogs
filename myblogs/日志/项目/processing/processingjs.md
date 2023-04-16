
即直接在你的页面中添加processing源码这一种方法。
不过也是经过了很大的波折才成功，原因是，

1.刚开始cnblog不让添加canvas标签，

2.引用web上的脚本的话，必须是：

<script type="text/javascript" src="https://rawgit.com/processing-js/processing-js/v1.4.8/processing.min.js"></script>

3.如果插入的代码中有<script>这种东西，就会在脚本中自动在脚本两端添加“// <![CDATA[”  和 “// ]]>”这种东西，这会影响到从processing源码到中间js代码的“编译”（参考官网）

用 jquery 的 apend 方法和 html 方法就是把不让加的东西都用脚本加上。

这个例子所有的代码是

<script type="text/javascript" src="https://rawgit.com/processing-js/processing-js/v1.4.8/processing.min.js"></script>  

<script type="text/javascript">// <![CDATA[  
$(function(){  
("#help").html("<canvas id='pjs'> </canvas>");("#help").html("<canvas id='pjs'> </canvas>");("body").append("<script type=\"application/processing\" data-processing-target=\"pjs\">\  
float radius = 50.0;\  
int X, Y;\  
int nX, nY;\  
int delay = 16; void setup(){\  
size( 200, 200 );\  
strokeWeight( 10 );\  
frameRate( 15 );\  
X = width / 2;\  
Y = height / 2;\  
nX = X;\  
nY = Y;} void draw(){\  
radius = radius + sin( frameCount / 4 );\  
X+=(nX-X)/delay;\  
Y+=(nY-Y)/delay;\  
background( 100 );\  
fill( 0, 121, 184 );stroke(255);ellipse( X, Y, radius, radius );} void mouseMoved(){\  
nX = mouseX;\  
nY = mouseY;}<"+"/script>");});  
// ]]></script>

![复制代码](https://common.cnblogs.com/images/copycode.gif)