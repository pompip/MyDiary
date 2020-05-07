# html

## xhtml 
* 更严格的html
* 所有的标签都必须关闭比如`</br>` `</p>`等等标签
* 标签名字必须小写
* `<table width="100%"/>` =号的引号不能省略 
* `<!DOCTYPE >`是必须在首行申明

## html标签

1. 段落
* `<p>`段落
* `<hX>` 不同的标题`<h1> -> <h6>` 
* `<span>`无特殊效果，用css标志特殊样式，用在`<p>`内部

2. 强调字体

* `<em>` 斜体 
* `<strong>`粗体
3. 引用

* `<q>`标签 简短文本的引用 自动生成引号
* `<blockquote>` 块状文本引用 前后锁进
* `<br>` 换行
* `<hr>` 分割线
* `& n b s p ;`表示一个空格，因为空格和回车都没作用

4. 特殊标识

    * `<address>` 标志这是地址
    * `<code>` 表示这是代码
    * `<pre>` 表示这是多行代码
    * `<div>` 分割网页

6. 列表

    * `<ul><li>`表示列表
    * `<ol><li>` 带序号的列表

7. table表格

    * `<table>`表格
    * `<tr>`表行
    * `<th>`表头
    * `<td>`表列 加上`<tbody>`代表需要表格全部下载完成才会显示 
    * `<caption>`标题 
    * `summary ＝“”`这是摘要

8. 链接和图片
    * `<a href=""连接地址 target="_blank"新窗口打开>`超链接 
    *  `<a href = "mailto:yy@imooc.com?subject=观了了不起的盖茨比有感&body=你好，对此评论有些想法">`对此影评有何感想，发送邮件给我</a> 
    * `<img src = ""地址  title = ""标题 alt = ""描述，图片不可见时代替图片>`图片

9. form表单

    * `<form method="post" action＝“”地址 >` 表单
    * `<input type="text/password/checkbox/radio／submit／reset" name = "">` 输入框 文本／密码／多选框／单选框／提交按钮／重置按钮
    * `<textarea rows="2" cols="2" >`输入域
    * `<select><option>` 下拉框

9. label

    * `<input type="checkbox" name = "manpao"id="manpao"/><br/><label for="manpao">慢跑</label>` 让文字和控件连带作用


## css


    * 基本格式`selector{property: value;property: value;...}`

    * ![css代码结构](http://www.w3school.com.cn/i/ct_css_selector.gif)

    * css大小写不敏感,但是与html一起工作,class和id例外

1. 选择器分组和继承

    + 选择器分组`h1,h2,h3,h4,h5,h6{color:green;}`;
    +  标准情况下,css子元素从父元素继承所有属性

2.  派生选择权

    * ul li { color :red} 那么ul 下的 li标签内容变为红色,其他li标签不变

3. css id选择器

    * id选择器 用#号来定义:`#red{color:red;} <p id=red>这个段落是红色的</p>`其中必须又 # 号来标明ID;
    *  可以结合派生选择器使用`#sidebar p{color :red;}` 表示sidebar这个id的标签下的p标签内容为红色;

4. 类选择器

    * `.center{text-align:center} <h1 class="center">this heading will be center-aligned</h1>` class的用法 
    *  class 和id不一样,class在一个页面可以有多个,但是id只有一个;
    *  同样可以用作派生选择器 `.fancy td{color: #f60} `

5. 属性选择器/属性值选择器

    * 属性选择器,就是tilte这个属性 `[title]{color:read}`
    *  属性值选择器,`[title=w3cshcool]{boorder:5px solid blue;}`

### 如何创建css

1.  外部样式表

```
<head>
<link rel="stylesheet" type="text/css" href="mystyle.css" />
```
2.  内部样式表

```
<head>
<style type="text/css">
hr {color: sienna;}
p {margin-left: 20px;}
body {background-image: url("images/back40.gif");}
</style>
</head>
```

3. 内联样式表 

```
<p style="color: sienna; margin-left: 20px">
This is a paragraph
</p>
```




