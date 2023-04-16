[howler.js - JavaScript audio library for the modern web (howlerjs.com)](https://howlerjs.com/)
背景音乐？

[Three.js中文网 (webgl3d.cn)](http://www.webgl3d.cn/)

[Pixi.js中文网 (huashengweilai.com)](http://pixijs.huashengweilai.com/)

## 起步
预备知识：
1. html、JavaScript
2. json[JSON: What It Is, How It Works, & How to Use It - Copter Labs](https://www.copterlabs.com/json-what-it-is-how-it-works-how-to-use-it/)
3. canvas
4. 启动 web 服务
5.

安装
1. 引入 pixi. min. js

测试代码
```js
<!doctype html>
<html>
    <head>
        <meta charset="utf-8">
        <title>Hello World</title>
    </head>
    <script src="pixi/pixi.min.js"></script>
    <body>
        <script type="text/javascript">
            let type = "WebGL"
            if(!PIXI.utils.isWebGLSupported()){
            type = "canvas"
            }

            PIXI.utils.sayHello(type)
        </script>
    </body>
</html>
```

## PIXI
### 创建画布
1. 创建 Pixi 应用 (初次设置画布大小)
new PIXI. Application (options);

最简单的 options：{width: 256, height:256}

2. 添加画布到页面上（app. view）
document. body. appendChild (app. view)

3. 再次设置画布大小 (app. renderer)
app. renderer. autoResize
app. renderer. resize (width, height)

app. renderer. view. style. positon
app. renderer. view. style. display

### 创建精灵
创建精灵的方法：
1. 单个图像
2. 雪碧图
3. 纹理贴图

GPU 中的图片：纹理 texture。

pixi 使用纹理缓存储存所有贴图。贴图名称就是图片路径。读取纹理：PIXI. utils. TextureCache\["images/cat. png"\]

使用纹理创建精灵：图片 2 纹理 2 精灵
```js
new PIXI.Sprite(texture)
/// 获取纹理并生成精灵
let texture = PIXI.utils.TextureCache['images/anySpriteImage.png'];
let sprite = new PIXI.Sprite(texture);
/// 图片2纹理
PIXI.loader
	.add('images/anyImage.png')
	.load(setup);
function setup(){
	
}
```