[手摸手，带你优雅的使用 icon - 掘金 (juejin.cn)](https://juejin.cn/post/6844903517564436493)

历程
img、image sprite 雪碧图+background-position、font 库（font awesome）、iconfont

unicode、font-class、svg
格式：png、ai、svg
方式：unicode、font-class、symbol
根据兼容性考虑

封装 svg 组件方便使用

svg 缺点与优化
每次都要改整个 iconfong. js、不能按需加载等。
解决方法是使用 svg-sprite。
webpack 配置
