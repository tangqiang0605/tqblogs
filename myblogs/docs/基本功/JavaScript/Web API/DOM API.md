.textContent 
.innerHTML
document.querySelector(*)



```
document.addEventListener("DOMContentLoaded", function() {
  function createParagraph() {
    let para = document.createElement('p');
    para.textContent = '你点击了这个按钮！';
    document.body.appendChild(para);
  }

  const buttons = document.querySelectorAll('button');

  for(let i = 0; i < buttons.length ; i++) {
    buttons[i].addEventListener('click', createParagraph);
  }
});
```

## Dom Api
domapi 非常简单。
```
const element=document.getElementById('myElement');
element.setAttribute('data-custom','value');
element.style.color='red';
element.innerHTMl='<p>hello</p>';
const children=element.childNodes;
```

获取 dom，然后操作其内容（attrs、style、inner），或者像树一样遍历其他节点。

节点与 dom 的区别？前者是一个 node 对象，后者是一个 document object model，不是对象。

### 选择
```
document.querySelector('.myClass');// 推荐
document.querySelectorAll('.myClass');
```

### 样式
```
element.setAttribute('className','xxx');

推荐
element.classList.add('xxx');
element.classList.remove('xxx');
element.classList.toggle('xxx-active');
```

### 内部
innerText、innerHTML。对子元素操作可以看作是对 innerHTML 的字符串编辑操作。
```
el.innerHTML='<div>hello</div>';

推荐
const newEl=document.createElement('div');
newEl.textContent='hello';
el.appendChild(newEl);
```

## 技巧
### 事件监听
事件委托：将事件监听器添加到父元素（currentTarget）上而不是它本身（target）。点击某个组件时，可能没有事件，但会冒泡会触发祖先节点上的所有事件。直接交付 document，可以减少冒泡中触发的事件。可以提高性能。冒泡来源，target，类似 proxy 中的 target 来源。事件监听器委托者 currentTarget。
```
document.addEventListener('click',(event)=>{
	if(event.target.matches('.myClass')){
		console.log('Element clicked:',event.target)
	}
})
```

### 批量更新
使用文档片段（fragement）或 rAF 批量更新。
```
const el=document.querySelectorAll('.myClass');
const fragment=docuemnt.createDocumentFragment();
el.forEach(v=>{
	const newEl=document.createElement('span');
	newEl.textContent='Updated';
	fragment.appendChild(newEl);
})

批量添加dom元素，可以先加在fragement中，再作为一个整体一次性加入某个dom中。
document.body.appendChild(fragment);
```

### shadow dom
创建自定义组件。
HTMLElement 的 attahShadow 方法可以创建一个 shadow dom。并被 customElement 的 define 方法使用。
```
class MyComponent extends HTMLElement {
	construct(){
		super();
		const shadowRoot=this.attachShadow({mode:'open'});
		shadowRoot.innerHTML='<p>hello</p>';
	}
}

customElement.define('my-component',MyComponent);
```

### template 标签
h 5 一个强大的功能。
```
<template id="#myt"><p>hello</p></template>
```

```
const template=docuemnt.getElementById('myt');
const el=template.content.cloneNode(true);
document.body.appendChild(el);
```