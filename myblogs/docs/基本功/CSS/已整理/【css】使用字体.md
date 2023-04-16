字体来源/下载

谷歌字体或其他字体网站比如100font（推荐）

用字安全提醒：https://100font.com/thread-3.htm

## 方法一引入在线字体（推荐）

在head标签中使用link标签引入，只要设置href rel。通常直接从谷歌字体复制粘贴即可。下面是格式参考。

``` html
<link href="http://fonts.googleapis.com/css?family=Open+Sans:300,300i,400,400i,600,600i,700,700i,800,800i" rel="stylesheet">

<link href="http://fonts.googleapis.com/css?family=Merriweather:300,300i,400,400i,700,700i,900,900i" rel="stylesheet">

<link href='http://fonts.googleapis.comcss?family=Roboto:400,100,100italic,300,300italic,400italic,500,500italic,700,700italic,900,900italic' rel='stylesheet' type='text/css'>
```

## 方法二fontface（推荐）

常用于引入项目资源中的本地字体，本地加载比在线字体加载速度快（实践中个人感觉差别不大）。

``` html
<style>
    @font-face {
        font-family:'MyFont';
        src:url('/fonts/Orbitron-Regular.ttf');
    }
</style>
```

## 方法三@import

``` html
<style>
    @import url('https://fonts.font.im/css?family=Orbitron')
</style>
```

