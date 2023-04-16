
processing.js：jquery 作者的第二个力作。

[processing-js/processing-js at v1.6.6 (github.com)](https://github.com/processing-js/processing-js/tree/v1.6.6) 最后版本。
唯一的官方示例。

使用 processing 代码的方法
```js    
<script src="processing.js"></script>
<script type="text/processing">
processing代码粘贴此处
</script>
```

获得 processingjs
``npm install processing-js
或直接拷贝 processingjs、processingminjs。

定制 processingjs
[processing-js/processing-js at v1.6.6 (github.com)](https://github.com/processing-js/processing-js/tree/v1.6.6#playing-with-the-code)
1.  Lint: `$> grunt`
2.  Test: `$> node test`
If step 1 gives you a "grunt: command not found" or similar error, run `npm install -g grunt-cli` to make sure grunt is globally installed as CLI command. If step 1 does not throw any errors, step 2 will run the Processing object through a battery of tests. Once the browser reference tests start, your `processing.js` and `processing.min.js` have been successfully built.

测试
手动 node server
http://localhost:3000-普通示例页 
http://localhost:3000/ref-参考测试页面 
http://localhost:3000/perf-性能测试页面 
http://localhost:3000/processing-helper.html-用于转换/运行处理代码的实用程序页 （有问题）

processingjs 已废弃，且版本已停止维护和更新。
p5js 并不是 processing，api 存在较多的差别。p5js 更像是在 web 上实现与 processing 同样效果的其他方法。p5js 不知道可不可以挂载到

参考 openprocessing

项目有益的库
[Credits - OpenProcessing](https://openprocessing.org/home/credits)


SketchDesigner 组件设计

引入 js：
组件 js：processing-helper. js
依赖：processingjs 或 processingminjs
暂时用不到的包
jsbeautifyjs，对 js 代码进行排版美化

SketchEditor 打开时自动聚焦到代码
textarea


？多个 tab

Controller
运行 runSketch

Canvas ，
id：sketch
结果

tools 文件夹：
实现代码的运行、生成。
todo：解读源码

```js
js2processing
const code=document.getElementById('code');

const canvas=document.createElement('cnavas');
canvas.id='sketch';
document.getElementById('sketch-container').appendChild(canvas);

const sketch=Processing.compile(code.value);
const instance=new Processing(canvas,sketch);

canvas.style.width=instance.width+'px';
canvas.style.height=instance.height+'px';

// 获得dataurl
canvas.toDataURL();

```
pjsdemo
最简运行 pjs 版本

test
processing 代码库
