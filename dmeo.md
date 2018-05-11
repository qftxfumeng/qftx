# 弹性布局  
## 弹性布局 : 弹性布局，是一种布局方式，主要是解决某元素中"子元素"的布局方式，为布局提供了最大的灵活性。  
* 主轴  
排列方向的一根轴，就成为主轴  
如果项目按x轴排列（横向排列），x轴就是主轴  
如果项目按y轴排列（纵向排列），y轴就是主轴 

* 4.交叉轴  
与主轴交叉的一根轴就是交叉轴  
如果主轴是x轴，那么y轴就是交叉轴  
如果主轴是y轴，那么x轴就是交叉轴  
# 语法  
## flex的容器  
将元素变为flex容器后，那么所有的子元素将变为flex项目，都允许按照弹性布局的方式排列。  
如何将元素设为弹性容器？  
属性：display  
取值:  
1.flex 将块级元素变为容器  
2.inline-flex 将行内元素变为容器（较少)    
注意 :  
1.元素设置为容器之后，子元素的float,clear,vertical-align将失效  
2.元素设置为flex容器之后，子元素的尺寸允许被修改  
3.容器的text-align属性将失效  
```
<style> 
.container {
    display: flex;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}

.item {
    background-color: cornflowerblue;
    width: 100px;
    height: 100px;
    margin: 10px;
}
</style>
</head>
<body>

<div class="container">
  <div class="item">flex item 1</div>
  <div class="item">flex item 2</div>
  <div class="item">flex item 3</div>  
</div>

```
## 2.容器的属性  
* 1.flex-direction  
作用：指定容器的主轴及其排列方向  
取值：  
row 默认值，即主轴为x轴，起点在左端  
row-reverse 即主轴为x轴,起点在右端 
column 主轴为y轴，起点在顶端  
column-reverse 主轴为y轴，起点在底端  
```
<style> 
.flex-container {
    display: -webkit-flex;
    display: flex;
    -webkit-flex-direction: row-reverse;
    flex-direction: row-reverse;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}

.flex-item {
    background-color: cornflowerblue;
    width: 100px;
    height: 100px;
    margin: 10px;
}
</style>
</head>
<body>

<div class="flex-container">
  <div class="flex-item">flex item 1</div>
  <div class="flex-item">flex item 2</div>
  <div class="flex-item">flex item 3</div>  
</div>

```
* 2.flex-wrap  
作用：当一个主轴排列不下所有项目时，如何换行  
取值：  
nowrap:默认值，即空间不够时，也不换行，项目会自动缩小  
wrap:换行  
wrap-reverse:换行反转  
```
<style> 
.flex-container {
    display: flex;
    flex-wrap: nowrap;
    width: 300px;
    height: 250px;
    background-color: lightgrey;
}

.flex-item {
    background-color: cornflowerblue;
    width: 100px;
    height: 100px;
    margin: 10px;
}
</style>
</head>
<body>

<div class="flex-container">
  <div class="flex-item">flex item 1</div>
  <div class="flex-item">flex item 2</div>
  <div class="flex-item">flex item 3</div>  
</div>
```

* 3.flex-flow  
作用：是flex-direction与flex-wrap的缩写形式  
取值：  
1.row nowrap 默认值  
2.direction wrap  

* 4.justify-content(必须)  
作用：定义项目在主轴上的对齐方式  
取值：  
1.flex-start 在主轴的起点对齐  
2.flex-end 在主轴的终点对齐  
3.center 在主轴上居中对齐  
4.space-between 两端对齐  
5.space-around 每个项目两端的间距相同  
```
<style> 
.flex-container {
    display: flex;
    justify-content: flex-end;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}

.flex-item {
    background-color: cornflowerblue;
    width: 100px;
    height: 100px;
    margin: 10px;
}
</style>
</head>
<body>

<div class="flex-container">
  <div class="flex-item">flex item 1</div>
  <div class="flex-item">flex item 2</div>
  <div class="flex-item">flex item 3</div>  
</div>

```   

* 5.align-items  
作用：项目在交叉轴上的对齐方式  
取值：  
1.flex-start 交叉轴的起点对齐  
2.flex-end 交叉轴的终点对齐  
3.center 交叉轴上居中对齐  
4.baseline 交叉轴上基线对齐 (与'flex-start'等效)  
5.stretch 如果项目未设置尺寸，在交叉轴上将占满所有的空间  
```
    <style> 
            .flex-container {
                display: flex;
                align-items:stretch ;
                width: 400px;
                height: 250px;
                background-color: lightgrey;
            }
            
            .flex-item {
                background-color: cornflowerblue;
                width: 100px;
                margin: 10px;
            }
            </style>
            </head>
            <body>
            
            <div class="flex-container">
              <div class="flex-item">flex item 1</div>
              <div class="flex-item">flex item 2</div>
              <div class="flex-item">flex item 3</div>  
            </div>
``` 

## 3.弹性子元素属性 
该组属性只能设置在某一项目元素上，只能控制一个项目，是不影响容器以及其他项目的效果  
* 1.order  
作用：定义项目的排列顺序，值越小，越靠近起点，默认值为0  
	      取值：整数数字，无单位  
```
<style> 
.flex-container {
    display: flex;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}

.flex-item {
    background-color: cornflowerblue;
    width: 100px;
    height: 100px;
    margin: 10px;
}

.first {
    order: 1;
}
</style>
</head>
<body>

<div class="flex-container">
  <div class="flex-item">flex item 1</div>
  <div class="flex-item first">flex item 2</div>
  <div class="flex-item">flex item 3</div>  
</div>

```
* 2.flex-grow  
        作用：定义项目的放大比例，如果容器足够空间，项目将如何放大  
        取值：  
          整数数字，无单位  
          默认为0，不放大  
          取值越大，占据的剩余空间越多  
* 3.flex-shrink  
        作用：定义项目的缩小比例，即容器空间不足时，项目该如何缩小  
        取值：  
        默认值为1，空间不足时，则等比缩小  
        取值为0，则不缩小  
* 4.align-self  
        作用：定义当前项目在交叉轴上的对齐方式  
        取值：  
          1.flex-start : 弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴起始边界。  
          2.flex-end : 弹性盒子元素的侧轴（纵轴）起始位置的边界紧靠住该行的侧轴结束边界  
          3.center 弹性盒子元素在该行的侧轴（纵轴）上居中放置。  
          4.baseline  如弹性盒子元素的行内轴与侧轴为同一条，则该值与'flex-start'等效。其它情况下，该值将参与基线对齐。  
          5.stretch  如果指定侧轴大小的属性值为'auto'，则其值会使项目的边距盒的尺寸尽可能接近所在行的尺寸，但同时会遵照'min/max-width/height'属性的限制。  
          6.auto 继承自父元素的align-items的对齐方式   
```
<style> 
.flex-container {
    display: -webkit-flex;
    display: flex;
    width: 400px;
    height: 250px;
    background-color: lightgrey;
}

.flex-item {
    background-color: cornflowerblue;
    width: 60px;
    min-height: 100px;
    margin: 10px;
}

.item1 {
    -webkit-align-self: flex-start;
    align-self: flex-start;
}
.item2 {
    -webkit-align-self: flex-end;
    align-self: flex-end;
}

.item3 {
    -webkit-align-self: center;
    align-self: center;
}

.item4 {
    -webkit-align-self: baseline;
    align-self: baseline;
}

.item5 {
    -webkit-align-self: stretch;
    align-self: stretch;
}
</style>
</head>
<body>

<div class="flex-container">
  <div class="flex-item item1">flex-start</div>
  <div class="flex-item item2">flex-end</div>
  <div class="flex-item item3">center</div>
  <div class="flex-item item4">baseline</div>
  <div class="flex-item item5">stretch</div>
</div>

```
# display: box;  
前者是flex 2012年的语法，也将是以后标准的语法，大部分浏览器已经实现了无前缀版本。  
后者是2009年的语法，已经过时，是需要加上对应前缀的。  
所以兼容性的代码，大致如下   
* display: -webkit-box; /* Chrome 4+, Safari 3.1, iOS Safari 3.2+ */
* display: -moz-box; /* Firefox 17- */
* display: -webkit-flex; /* Chrome 21+, Safari 6.1+, iOS Safari 7+, Opera 15/16 */
* display: -moz-flex; /* Firefox 18+ */
* display: -ms-flexbox; /* IE 10 */
* display: flex; /* Chrome 29+, Firefox 22+, IE 11+, Opera 12.1/17/18, Android 4.4+ */

作者：一丝
链接：https://www.zhihu.com/question/22991944/answer/23302749
来源：知乎
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。  
## display:flex 跟 display:box区别  
* 与子元素 display 方式的相关性不同  
display:box; 作用下，如果子元素是 block 的，竖着排，如果子元素是 inline、inline-block 的，横着排。  
 display:flex; 作用下，是横着排还是竖着排，只取决于 flex-direction 的值是 row 还是 column。
* float 等属性是否受影响的情况不同  
display:box; 作用下，float、clear、text-align、vertical-align 仍起作用。   
display:flex; 作用下，上述四属性失效. 

## 内核的浏览器，必须加上-xx-前缀。   
### -moz-对应 Firefox,
### -webkit-对应 Safari and Chrome 
### -o- 对应  Opera 
### -ms- 对应 Internet Explorer( 注意: Flexible boxes不兼容于 IE 9以及更早版本的浏览器 ) 

* box-direction 属性   box-direction属性指定显示哪个方向的box的子元素。  
normal	以默认方向显示子元素。  
reverse	以反方向显示子元素。  
```
<style> 
div
{
	width:350px;
	height:100px;
	border:1px solid black;
 
	display:-webkit-box;
	-webkit-box-direction:reverse;
}
</style>
</head>
<body>

<div>
<p>Cat</p>
<p>Dog</p>
<p>Horse</p>
</div>

<p><b>注意:</b> Flexible boxes 在 IE 9和更早版本的浏览器中不兼容</p>

```    
* box- align 和 box-pack属性指定box的子元素如何对齐。    
start : 每个子元素的顶部边缘放在沿box的顶部。反向，每个子元素的底边放在沿box的底部  
end : 每个子元素的顶部边缘放在沿box的底部。反向，每个子元素的底边放在沿box的顶部  
center : 任何多余的空间被划分均匀，一半以上的子元素放在上面，剩下的子元素放在另一半  
baseline :  如果box-orient是内嵌单轴或横向，所有的子元素都置于他们的基线对齐  
stretch : 子元素拉伸以填充包含区块    
```
    <style> 
div
{
	width:350px;
	height:100px;
	border:1px solid black;
 
	display:-webkit-box;
	-webkit-box-pack:center;
	-webkit-box-align:center;
}
</style>
</head>
<body>
<div>
<p>Center me!</p>
</div>
```  
* box-flex 属性  
属性定义及使用说明
box-flex属性指定box的子元素是否灵活或固定的大小。  
提示: 随着box收缩和增长，元素是否灵活的收缩或增长。每当有额外的空间，在box里，元素灵活的扩大来填补这一空间。  
默认值:	0.0(表示该元素是不灵活的)  
```
<style> 
div
{
	display:-webkit-box;
	width:300px;
	border:1px solid black;
}

#p1
{
	-webkit-box-flex:1.0; 
	border:1px solid red;
}

#p2
{
	-webkit-box-flex:2.0;
	border:1px solid blue;
}
</style>
</head>
<body>

<div>
<p id="p1">Hello</p>
<p id="p2">W3Schools</p>
</div>
 
```  
* box-lines 属性  
box-lines属性指定每当它运行在父级box的空间，列中是否会得到一个新的行。  
提示： 默认情况下，横向盒里会在单一的行铺陈它的子元素，和一个纵向盒铺陈其在单个列中的子元素。  
single ：将被放置在单个行或列的所有子元素（元素不适合只会被认为是溢出）（默认值）
multiple ：box允许扩大到多行，以适应其所有子项  (目前所有主流浏览器都不支持box-lines属性。)