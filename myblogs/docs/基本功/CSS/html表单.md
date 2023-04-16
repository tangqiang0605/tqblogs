form标签

语义化标签包裹表单。

1.发送表单数据的方式method：get  | post

2.向何处发送表单数据action

```

<form  method="post" action="xxx.html"></form>

域：使用<fieldset>来定义。将一组表单元素放到域中
域标题：使用<legend>。所谓的域标题就是给创建的域设置个标题。


```

label标签

for值为input的id



input标签

name

pattern：内容需要符合pattern的值（正则）

id用于label的for绑定。

type：**text、password、**file文件选择、button、checkboxes多选复选框、radio单选、image图片提交、**submit提交、**reset重置按钮、hidden、number、select 标签用于声明下来列表、option 标签用于声明列表项

**value：input的值**

size属性：元素的宽度，当 type 为 text 或 password时。

maxlength：type为text 或 password 时，输入的最大字符数

特殊属性：

checked：type为radio或checkbox时，指定按钮是否是被选中

disabled

readonly



button标签

type：submit



textarea标签

、<textarea id="content" cols="30" row="10"></textarea>

可见行数：标签属性：rowsrows 属性规定 textarea 的可见高度。
可见宽度：标签属性：colscols 属性规定 textarea 的可见宽度。
最大长度：标签属性：maxlengthmaxlength 属性规定文本区域的最大长度（以字符计）。
名称：标签属性：namename 属性为文本区规定名称。