```
push加到末尾

unshift加到前面

pop删除末尾

shift删除前面

forEach((e,i,arr)=>{})当前元素索引数组本身

map

filter

解构操作

空白占位

let [a,,b]=[1,2,3];//a=1,b=3;



正则表达式、正则验证

reg正则表达式.test(字符串)



setTimeout(()=>{},time)

setInterval(fn,time)返回intervalId

clearInterval(intervalId)暂停循环



promise



const ele=document.querySelector("");

ele.value="";



模块

module

import styles from "./styls.css" assert {type:'css'};
```



## dom

[Web API 接口参考 | MDN (mozilla.org)](https://developer.mozilla.org/zh-CN/docs/Web/API)

![image-20230206230626656](D:\tplmydata\tplmydoc\文档图片\image-20230206230626656.png)

``` js
let sidebar=document.getElementsByClassName("sidebar")[0];
let sidebar_content=document.getElementsByClassName("content-wrapper")[0];
window.onscroll=()=>{
    //当前滚动高度，视口高度，
    console.log(window.scrollY,window.innerHeight,window.pageYOffset);
    //内容高度/元素高度、距离顶部 
    let sidebar-rect=sidebar_content.getBoundingClientRect();
    console.log(sidebar-rect.height,sidebar-rect.top);
    let sidebarTop=sidebar-rect.top+window.pageYOffset;
    属性设置
    sidebar_content.style.transform=`translateY(-${contentHeight}px`;
    sidebar_content.style.position="fixed";
    、属性移除
    sidebar_content.style.position="";
}
```

添加元素

``` js
for(let i=0;i<100;i++){
    const element=document.createElement("div");
    element.innerHTML=i;
    document.body.appendChild(element);
}
一次append渲染一次，该循环导致渲染一百次，也就是页面有100次回流。
```

添加元素（优化）

``` js
const fragment=document.createDocumentFragment();
for(let i=0;i<100;i++){
    const element=document.createElement("div");
    element.innerHTML=i;
    fragment.appendChild(element);
}
document.body.appendChild(fragment);
一次append渲染一次，利用fragment，让页面只渲染一次。
```

拖拽

``` js
let oDiv=document.querySelector('div');
oDiv.addEventListener('mousedown',(e)=>{
    let x=e.offsetX;
    lef y=e.offsetY;
    document.addEventListener('mousemove',(e)=>{
        lef div_left=e.clientX-x;
        let div_top
    })
})

e.clientX鼠标点击的视图位置
e.clientY相对根元素的位置
e.offsetX相对父元素的位置
moveup鼠标松开事件
oDiv.offsetHeight高度
oDiv.offsetWidth元素宽度
window.innerHeight
window.innerWidth视图宽度

```

输入框

``` js
const input=document.querySelector('.ipt');
const items=document.querySelectorAll('.div');
焦点事件focus、blur失去焦点、
input输入事件e.target.value输入的值
移动光标
input.setSelectionRange(input.value.length-1,input.value.length);
```

添加类

``` js
const odiv=document.querySelector('div');
odiv.classList.add(添加的css类名);
odiv.classList.remove(删除的类名);
odiv.classList.toggle(有则删除无则添加)
```

元素内容

``` js
const odiv=document.querySelector('div');
odiv.textContent="";
```

响应式

![image-20230207183942711](D:\tplmydata\tplmydoc\文档图片\image-20230207183942711.png)

自适应

![image-20230207184119693](D:\tplmydata\tplmydoc\文档图片\image-20230207184119693.png)
