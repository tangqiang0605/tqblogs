类似正则。很多包的配置文件（比如 ts、jest、gulp）都使用了 node-glob 模块来实现其文件匹配功能。

以下内容引用自：[前端构建工具 GulpJS 快速入门指南 (baidu.com)](https://baijiahao.baidu.com/s?id=1710296849580950050&wfr=spider&for=pc)

| 符号        | 描述       |
| ----------- | ---------- |
| ?           | 一个字符（非分隔符）   |
| *           | 任意字符（非分隔符）   |
| **          | 多个目录   |
| \[...\]     | 某个字符   |
| \[^...\]或\[!...\]    | 非某个字符 |
| !(p\|p\|p)  | 非某个模式 |
| +           | 至少一次   |
| *           | 任意       |
| @(p\|p\|p\) | 某个模式           |
-   `*` 匹配文件路径中的0个或多个字符，但不会匹配路径分隔符，除非路径分隔符出现在末尾
-   `**` 匹配路径中的0个或多个目录及其子目录,需要单独出现，即它左右不能有其他东西了。如果出现在末尾，也能匹配文件。

下面以一系列例子来加深理解

-   `*` 能匹配 `a.js`,`x.y`,`abc`,`abc/`,但不能匹配`a/b.js`
-   `*.*` 能匹配 `a.js`,`style.css`,`a.b`,`x.y`
-   `*/*/*.js` 能匹配 `a/b/c.js`,`x/y/z.js`,不能匹配`a/b.js`,`a/b/c/d.js`
-   `**` 能匹配 `abc`,`a/b.js`,`a/b/c.js`,`x/y/z`,`x/y/z/a.b`,能用来匹配所有的目录和文件
-   `**/*.js` 能匹配 `foo.js`,`a/foo.js`,`a/b/foo.js`,`a/b/c/foo.js`
-   `a/**/z` 能匹配 `a/z`,`a/b/z`,`a/b/c/z`,`a/d/g/h/j/k/z`
-   `a/**b/z` 能匹配 `a/b/z`,`a/sb/z`,但不能匹配`a/x/sb/z`,因为只有单`**`单独出现才能匹配多级目录
-   `?.js` 能匹配 `a.js`,`b.js`,`c.js`
-   `a??` 能匹配 `a.b`,`abc`,但不能匹配`ab/`,因为它不会匹配路径分隔符
-   `[xyz].js` 只能匹配 `x.js`,`y.js`,`z.js`,不会匹配`xy.js`,`xyz.js`等,整个中括号只代表一个字符
-   `[^xyz].js` 能匹配 `a.js`,`b.js`,`c.js`等,不能匹配`x.js`,`y.js`,`z.js`

当有多种匹配模式时可以使用数组

```
//使用数组的方式来匹配多种文件gulp.src(['js/*.js','css/*.css','*.html'])
```

使用数组的方式还有一个好处就是可以很方便的使用排除模式，在数组中的单个匹配模式前加上`!`即是排除模式，它会在匹配的结果中排除这个匹配，要注意一点的是不能在数组中的第一个元素中使用排除模式

```
gulp.src([*.js,'!b*.js']) //匹配所有js文件，但排除掉以b开头的js文件gulp.src(['!b*.js',*.js]) //不会排除任何文件，因为排除模式不能出现在数组的第一个元素中
```

此外，还可以使用展开模式。展开模式以花括号作为定界符，根据它里面的内容，会展开为多个模式，最后匹配的结果为所有展开的模式相加起来得到的结果。展开的例子如下：

-   `a{b,c}d` 会展开为 `abd`,`acd`
-   `a{b,}c` 会展开为 `abc`,`ac`
-   `a{0..3}d` 会展开为 `a0d`,`a1d`,`a2d`,`a3d`
-   `a{b,c{d,e}f}g` 会展开为 `abg`,`acdfg`,`acefg`
-   `a{b,c}d{e,f}g` 会展开为 `abdeg`,`acdeg`,`abdeg`,`abdfg`