### js

### JS调用

> 外部调用`<script src="script.js"></script>`
> 内部调用 `<script type="text/javascript"></script>`


### 入门

> 变量 关键字 var ；也可以不定义，直接使用；
> 函数 关键字 function ；
> 流程控制 

```javascript
 <script type="text/javascript">
 switch(v1){
 case 1:
 	break;
 default:
 break;
 }
 </script>
```


### 浏览器交互

#### 对话框

> alert  单选
> confirm  `var mymessage= confirm("你是女士？")`  双选，my message 为bool
> prompt	`score = prompt("标题","hint")`

#### 其他
> 打开窗口 `window.open("url","name","_top/_blank","窗口参数`
> 关闭窗口 `window.close`关闭自己 ；<窗口对象>.close 关闭自定窗口；
```html
 <script type="text/javascript">
 var mywin = window.open("http://www.imooc.com");
 mywin.close();
 </script>
```

### 文档对象模型
> DOM（Document Object Model）定义访问和处理HTML文档的标准方法。DOM 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）。



> * 通过ID获取元素 
>   `var xx = document.getElementById(“id”) `
> * 改变内容
>   'Object.innerHTML'  xx.innerHTML = "hello world"
> * 改变样式
>   `Object.style.property=new style;` `xx.style.backgoundColor = "#ccc"`
> * 显示和隐藏
>   `Object.style.display = value`;`xx.style.display = "none"`,value 为none或者为block；
> * 控制类名（className 属性）
>   `object.className = classname`; xx.className = "two"
>   `.two{color:red;}` two 指定class样式；

* getElementsByName('my'),返回的是节点数组。<div name= "my"/>
* elementNode.getAttribute(name),获取标签的属性；elementNode.setAttribute(name，value),设置属性
#### 节点属性
> 通过getElementById()getElementsByTagName()等获取到elementNode后，elementNode.nodeName/childNodes,调用
* nodeName
> 1. nodeName : 节点的名称 
> 2. nodeValue ：节点的值
> 3. nodeType ：节点的类型
* nodeValue
> 1. 元素节点的 nodeValue 是 undefined 或 null
> 2. 文本节点的 nodeValue 是文本自身
> 3. 属性节点的 nodeValue 是属性的值
* nodeType

> 元素类型    节点类型
> 元素          1
> 属性          2
> 文本          3
> 注释          8
> 文档          9


* childNodes 
  > firstChild  
  > lastChild 
  > parentNode 
  > nextSibling下一个节点
  > previousSibing 上一个节点

``` var p = document.createElement('p'),p.innerHTML= "haha",node.append(p);```


### function 函数
```html
<script type="text/javascript">
  function xx(x,y){
	retun x>y?x:y;
 }
</script>
```

### 浏览器事件
* onclick 点击

* onmouseover 鼠标经过

* onmouseout 鼠标移出

* onfocus 获取焦点

* onblur 失焦

* unselect 选中事件

* onchange 文本框内容改变事件

* onload 加载事件，事件写在<body onload="">

* onunload 关闭网页事件

```
  <script type="text/javascript">  
   	window.onunload = onunload_message;   
       function onunload_message(){   
          alert("您确定离开该网页吗？");   
      }   
  </script> 
```

### 内置对象

#### Date日期对象

```javascript
var d = new Date(2012,10,1);
var d1 = new Date('oct 1,2012');
d.getDate();
d.getFullYear();
d.getYear();
d.getMonth;
...
```

#### String字符串对象

```javascript
var mystr = 'hello world';
var length = mystr.length;
mystr.toUpperCase();
mystr.toLowerCase();
mystr.charAt(index);
mystr.indexOf(substring,startpos);//检索首次出现substring的位置，startpos:开始检索的位置 startpos可选
mystr.split('',limit)//以‘’分割limit次 limit可选
mystr.substring(start,end)//截取 end可选 end小于start责交换参数
mystr.substr(start,length);//截取 start为负，末尾开始算
```

#### Math对象

#### Array数组对象

```javascript
var arr1 =['a','2']; 
var arr2= new Array();
arr1.length; //数组长度；
var a = arr1[1];//取值
arr1[8] = '9';//直接赋值;这个时候arr.length = 9;
var arr3 ＝ arr1.concat(arr2,...);//连接数组；返回一个新的数组
arr3.join(seqarator);//返回一个加了separator的字符串，可选，不选责添加逗号；
arr3.reverse();//倒序
arr3.slice(start ,end);
arr3.sort(方法函数);
```

### 浏览器对象

#### 循环计时器setInterval() clearInterval()

```javascript
setInterval("clock()",100);
setInterval(clock,100);//设置计时器
clearInterval(id);//取消计时器

 var attime;
  function clock(){
    var time=new Date();          
    attime= time.getHours()+":"+time.getMinutes()+":"+time.getSeconds() ;
    document.getElementById("clock").value = attime;
  }
 var id =  setInterval(clock,100);

clearInterval(id);
```

#### 单次计时器 setTimeout()

```javascript
setTimeout(代码，延迟时间)；
clearTimeout(id);
```

#### history 浏览器历史

```javascript
window.history.length;
window.history.back(); //go(-1) == back();
foward();//==go(1)
go(number); 
```

#### location 对象

>当前窗口的URL，可以用于解析URL

```

```

#### navigator对象

> 包含浏览器的信息，包括浏览器和操作系统

```javascript
navigator.userAgent;//用户信息

  function validB(){ //查看浏览器
    var u_agent = navigator.userAgent; 
    var B_name="不是想用的主流浏览器!"; 
    if(u_agent.indexOf("Firefox")>-1){ 
        B_name="Firefox"; 
    }else if(u_agent.indexOf("Chrome")>-1){ 
        B_name="Chrome"; 
    }else if(u_agent.indexOf("MSIE")>-1&&u_agent.indexOf("Trident")>-1){ 
        B_name="IE(8-10)";  
    }
        document.write("浏览器:"+B_name+"<br>");
        document.write("u_agent:"+u_agent+"<br>"); 
  } 
```



#### screen对象

> 获取用户的屏幕信息

```
screen.width;
screen.height;
screen.availWidth; //可用宽度，减去了任务栏
screen.availHeight;
```

