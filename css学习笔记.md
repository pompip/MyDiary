# css

> css由选择符和声明组成
> `p{color:blue}` 通过：链接，；分割多条属性
>
> `/*xxxx*/` css注释
>
> `<!--xxxxx--> `html注释

## css基本形式分为内连式，嵌入式和外部式
> 
* 内连式
   `<p style="color:red;">`直接在html标签中设置
* 嵌入式 一般写在html head标签中

```
  <style type="text/css">
    span{
    color:red;
    }
  </style>
```

* 外部样式
```
<link href="style.css" rel="stylesheet" type="text/css" />
```

## 选择器

### 基本选择器
* 基本形式 选择权{ 样式；}
* 标签选择器 `h1{font-weight:noaml;color:red;}`
* 类选择器 `.haha{color:read;}` 设置类`<span class = "haha">`
* id选择器 `#heihei{}` id设置 `<span id ="heihei">`
* 类选择器和id选择器区别：类可以多次使用，id不能重复；一个标签可以设置多个类，能同时作用`<span class = "stress bigsize">` 尽量不用id选择器设置css，留给js用
### 组合选择器
* 子选择器`.first>span{border:2px solid red;}` first类里面的<span>标签
* 包含(后代)选择器 `.first span{border:2px solid red;}`
* 区别 子选择器仅仅包含第一层，包含选择器包好标签内部 所有，如名字 一个事儿子，一个是后代
* 通用选择器 `*{font-size:20px}` 所有的标签
* 伪类选择器`a:hover{color:red;}`给鼠标事件设置css
* 分组选择器 `h1,span{color:red;}` 相当于两个选择器

## 继承
* 部分属性可以让子标签继承，部分不能
* 多种选择器作用于同一标签，根据权值来选择最终效果；其中标签的权值为1，类选择符的权值为10，ID选择符的权值最高为100
* 权值相同，层叠样式，就近原则
* 样式优先级为：浏览器默认的样式 < 网页制作者样式 < 用户自己设置的样式，但是`p{color:red!important;}`高于用户选择，具有最高权值

## 格式排版

### 字体
```html
  body{font-family:"微软雅黑";
  font-size:12px;
  color:#666;
  font-weight:bold; /*粗体*/
  font-style:italic; /*斜体*/
  text-decoration:underline; /*下划线*/
  text-decoration:line-through /*删除线*/
  }
```
### 段落 
```html
  p{
  text-indent:2em; /*抬头空2格 2em两倍字 */ 
  line-height:1.5em /* 行高*/
  letter-spacing:50px; /*字母间距*/
  word-spacing:50px; /*英文单词间距*/
  text-align:center;  left／right  /*居中*/
  }
```

## 元素分类

> css中 html元素分为块状元素、行内元素、内联块状元素

### 块状元素

> 1. 每个块级元素都从新的一行开始，并且其后的元素也另起一行。（真霸道，一个块级元素独占一行）
> 2. 元素的高度、宽度、行高以及顶和底边距都可设置。
> 3. 元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度。
> 4. 将行内元素转化成块状元素 `a{display:block;}`

### 行内元素（内联元素）

> 1. 和其他元素都在一行上；
> 2. 元素的高度、宽度及顶部和底部边距**不可**设置；
> 3. 元素的宽度就是它包含的文字或图片的宽度，不可改变。
> 4. 将行内元素转化块状元素 `div{display:inline;}`
>
>

### 内联块状元素

> 1. 和其他元素都在一行上；
> 2. 元素的高度、宽度、行高以及顶和底边距都可设置。
> 3. `{dispaly:inline-block}` 



## 盒子模型

### 边框 border
* boarder-style dashed\dotted\solid
* border-color #ccc
* border-width 2px
* border-bottom\right\top\left 1px solid red;

### 宽高 width／height
> css内定义的宽（width）和高（height），指的是填充以里的内容范围.不包含padding，因此，实际宽度＝padding＋witch；
> Android 中指控件高度，包括padding

### 填充 padding
> padding 10px;四周 ；10px 20px 上下和左右；10px 20px 30px 上下 左 右；10px 20px 30px 40px 分别上下左右
> padding-top\right\bottom\right

### 边界 margin
> 同padding，

## css 布局模型
> 1 流动模型（Flow）
> 2 浮动模型 (Float)
> 3 层模型（Layer）

### flow
* 浏览器默认的模型
* 第一点，块状元素都会在所处的包含元素内自上而下按顺序垂直延伸分布，因为在默认状态下，块状元素的宽度都为100%。实际上，块状元素都会以行的形式占据位置。如右侧代码编辑器中三个块状元素标签(div，h1，p)宽度显示为100%。
* 第二点，在流动模型下，内联元素都会在所处的包含元素内从左到右水平分布显示。（内联元素可不像块状元素这么霸道独占一行）

### float
```html
div{
    width:200px;
    height:200px;
    border:2px red solid;
    float:right;
}
```
> 块状元素这么霸道都是独占一行，如果现在我们想让两个块状元素并排显示，设置float :right/left;

### layer
> 1 绝对定位(position: absolute)
> 2 相对定位(position: relative)
> 3 固定定位(position: fixed)

#### 绝对定位

> 如果想为元素设置层模型中的绝对定位，需要设置**position:absolute**(表示绝对定位)，这条语句的作用将元素从文档流中拖出来，然后使用left、right、top、bottom属性相对于其最接近的一个具有定位属性的父包含块进行绝对定位。如果不存在这样的包含块，则相对于body元素，即相对于**浏览器窗口**

```html
div{
width:200px;
height:200px;
border:2px red solid;
position:absolute;
left:100px;
top:50px;
}
```

#### 相对定位
> 如果想为元素设置层模型中的相对定位，需要设置 `position:relative`(表示相对定位),它通过left、right、top、bottom属性确定元素在正常文档流中的偏移位置。相对定位完成的过程是首先按static(float)方式生成一个元素(并且元素像层一样浮动了起来)，然后相对于以前的位置移动，移动的方向和幅度由left、right、top、bottom属性确定，偏移前的位置保留不动。

#### 固定定位
> fixed：表示固定定位，与absolute定位类型类似，但它的相对移动的坐标是视图（屏幕内的网页窗口）本身。由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化，除非你在屏幕中移动浏览器窗口的屏幕位置，或改变浏览器窗口的显示大小，因此固定定位的元素会始终位于浏览器窗口内视图的某个位置，不会受文档流动影响，这与`background-attachment:fixed`;属性功能相同。以下代码可以实现相对于浏览器视图向右移动100px，向下移动50px。并且拖动滚动条时位置固定不变。

### 盒子模型简写
* margin padding
* color 
* ```html
  body{
    font:italic  small-caps  bold  12px/1.5em  "宋体",sans-serif;
  }
  ```




## 颜色

* `p{color:red;}`
* `p{color:rgb(133,45,200);}`
* `p{color:rgb(20%,33%,25%)}`
* `p{color:#00ffff}`

### 长度

* px 
* em 父控件等百分比
* 百分比