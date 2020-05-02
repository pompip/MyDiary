# html
## xhtml 
> * 更严格的html
> * 所有的标签都必须关闭比如`</br>` `</p>`等等标签
> * 标签名字必须小写
> * `<table width="100%"/>` =号的引号不能省略 
> * `<!DOCTYPE >`是必须在首行申明

## css
> + 基本格式`selector{property: value;property: value;...}`
+  ![css代码结构](http://www.w3school.com.cn/i/ct_css_selector.gif)
+  css大小写不敏感,但是与html一起工作,class和id例外

### 选择器分组和继承
> + 选择器分组`h1,h2,h3,h4,h5,h6{color:green;}`;
+  标准情况下,css子元素从父元素继承所有属性

###  派生选择权
> ul li { color :red} 那么ul 下的 li标签内容变为红色,其他li标签不变

### css id选择器
> * id选择器 用#号来定义:`#red{color:red;} <p id=red>这个段落是红色的</p>`其中必须又 # 号来标明ID;
*  可以结合派生选择器使用`#sidebar p{color :red;}` 表示sidebar这个id的标签下的p标签内容为红色;

###类选择器
> * `.center{text-align:center} <h1 class="center">this heading will be center-aligned</h1>` class的用法 
*  class 和id不一样,class在一个页面可以有多个,但是id只有一个;
*  同样可以用作派生选择器 `.fancy td{color: #f60} `

### 属性选择器/属性值选择器
>  属性选择器,就是tilte这个属性 `[title]{color:read}`
>  属性值选择器,`[title=w3cshcool]{boorder:5px solid blue;}`

## 如何创建css

*  外部样式表
```
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
```
*  内部样式表
```
<head>
<style type="text/css">
hr {color: sienna;}
p {margin-left: 20px;}
body {background-image: url("images/back40.gif");}
</style>
</head>
```
* 内联样式表 
```
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```


