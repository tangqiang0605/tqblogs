
并集选择器逗号隔开
```
li.special,
span.special {
```
后代选择器空格隔开
```
li em {
```
兄弟选择器（相邻）
```
h1 + p {
```
伪类选择器
未访问的、访问过的、被鼠标悬停的、被键盘定位的，亦或是正在被点击当中的状态
```
a:link {
  color: pink;
}

a:visited {
  color: green;
}
```


示例
```
在 `<body>` 之内，紧接在 `<h1>` 后面的 `<p>` 元素的内部，类名为 special。
body h1 + p .special {
```