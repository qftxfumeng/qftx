# svg  
## 什么是SVG？
* SVG指可伸缩矢量图形
* SVG用来定义用于网络的基于矢量的图形
* SVG使用XML格式定义图形
* SVG图像在放大或改变尺寸的情况下其图片质量不会有所损失  
```
<?xml version="1.0" standalone="no"?>
<!DOCTYPE svg PUBLIC  "-//W3C//DTD SVG 1.1//EN"  "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<style>
    svg{
        width:100%; height:100%;
        border:1px solid red;
    }
</style>
<svg xmlns="http://www.w3.org/2000/svg" version="1.1">
  <circle cx="100" cy="50" r="40" stroke="black"
  stroke-width="2" fill="red" />
</svg>
```  
 SVG 代码解析：  
 * 第一行包含了 XML 声明。请注意 standalone 属性！该属性规定此 SVG 文件是否是"独立的"，或含有对外部文件的引用。standalone="no" 意味着 SVG 文档会引用一个外部文件 - 在这里，是 DTD 文件  
 * 第二和第三行引用了这个外部的 SVG DTD。该 DTD 位于 "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd"。该 DTD 位于 W3C，含有所有允许的 SVG 元素。  
 * SVG 代码以 《svg》 元素开始，包括开启标签 《svg》 和关闭标签 《/svg》 。这是根元素。width 和 height 属性可设置此 SVG 文档的宽度和高度。version 属性可定义所使用的 SVG 版本，xmlns 属性可定义 SVG 命名空间。  
 * SVG 的 《circle》 用来创建一个圆。cx 和 cy 属性定义圆中心的 x 和 y 坐标。如果忽略这两个属性，那么圆点会被设置为 (0, 0)。r 属性定义圆的半径。  
 * stroke 和 stroke-width 属性控制如何显示形状的轮廓。我们把圆的轮廓设置为 2px 宽，黑边框。fill 属性设置形状内的颜色。我们把填充颜色设置为红色。  
 * 关闭标签的作用是关闭 SVG 元素和文档本身。
 * 注释：所有的开启标签必须有关闭标签！  
 ## SVG 在 html 页面  
 1、svg文件可通过以下标签嵌入html文档：《embed》、《object》、《iframe》。  
 * 使用 《embed>》标签  
 优势：所有主要浏览器都支持，并允许使用脚本  
缺点：不推荐在HTML4和XHTML中使用（但在HTML5允许）  
```
语法:
<embed src="circle1.svg" type="image/svg+xml" />
```  
* 使用 《object》 标签  
优势：所有主要浏览器都支持，并支持HTML4，XHTML和HTML5标准  
缺点：不允许使用脚本。  
```
语法:
<object data="circle1.svg" type="image/svg+xml"></object>
```  
* 使用 《iframe》标签  
优势：所有主要浏览器都支持，并允许使用脚本  
缺点：不推荐在HTML4和XHTML中使用（但在HTML5允许）  
```
语法:
<iframe src="circle1.svg"></iframe>
```  
* 直接在HTML嵌入SVG代码  
在Firefox、Internet Explorer9、谷歌Chrome和Safari中，你可以直接在HTML嵌入SVG代码。  
```
<!DOCTYPE html>
<html>
<body>

<svg version="1.1">
   <circle cx="100" cy="50" r="40" stroke="black" stroke-width="2" fill="red" />
</svg> 
 
</body>
</html>
```  
* 链接到SVG文件  
您还可以用《a》标签链接到一个SVG文件：链接到SVG文件
您还可以用《a》标签链接到一个SVG文件：  
```
<a href="circle1.svg">View SVG file</a>
```  
##  SVG有一些预定义的形状元素，可被开发者使用和操作：  
* 矩形   《rect》
* 圆形   《circle》
* 椭圆   《ellipse》
* 线     《line》
* 折线   《polyline》
* 多边形 《polygon》
* 路径   《path》  
## 下面会为你们讲解这些元素，首先从矩形元素开始  
# SVG 矩形 - 《rect》  
* rect 元素的 width 和 height 属性可定义矩形的高度和宽度  
* style 属性用来定义 CSS 属性  
* CSS 的 fill 属性定义矩形的填充颜色（rgb 值、颜色名或者十六进制值）  
* CSS 的 stroke-width 属性定义矩形边框的宽度  
* CSS 的 stroke 属性定义矩形边框的颜色  
* x 属性定义矩形的左侧位置（例如，x="0" 定义矩形到浏览器窗口左侧的距离是 0px）  
* y 属性定义矩形的顶端位置（例如，y="0" 定义矩形到浏览器窗口顶端的距离是 0px）  
* CSS 的 fill-opacity 属性定义填充颜色透明度（合法的范围是：0 - 1）  
* CSS 的 stroke-opacity 属性定义笔触颜色的透明度（合法的范围是：0 - 1）  
* rx 和 ry 属性可使矩形产生圆角。   
```
    <svg  version="1.1">
      <rect x="50" y="20" width="150" height="150"
      style="fill:blue;stroke:pink;stroke-width:5;fill-opacity:0.1;
      stroke-opacity:0.9"/>
    </svg>
```   
 # SVG 圆形 - 《circle》  
* cx和cy属性定义圆点的x和y坐标。如果省略cx和cy，圆的中心会被设置为(0, 0)  
* r属性定义圆的半径  (也就是圆的大小)
```
      <svg  version="1.1">
        <circle cx="100" cy="50" r="40" stroke="black"
        stroke-width="2" fill="red"/>
      </svg>
```
 # SVG 椭圆 - 《ellipse》  
* CX属性定义的椭圆中心的x坐标
* CY属性定义的椭圆中心的y坐标
* RX属性定义的水平半径
* RY属性定义的垂直半径  
```
<svg  version="1.1">
  <ellipse cx="240" cy="100" rx="220" ry="30" style="fill:purple"/>
  <ellipse cx="220" cy="70" rx="190" ry="20" style="fill:lime"/>
  <ellipse cx="210" cy="45" rx="170" ry="15" style="fill:yellow"/>
</svg>
```  
 # SVG 直线 - 《line》  
* x1 属性在 x 轴定义线条的开始
* y1 属性在 y 轴定义线条的开始
* x2 属性在 x 轴定义线条的结束
* y2 属性在 y 轴定义线条的结束  
```
<svg  version="1.1">
  <line x1="0" y1="0" x2="200" y2="0"
  style="stroke:rgb(255,0,0);stroke-width:2"/>
</svg>
```  
 # SVG 多边形- 《polygon》  
   《polygon》标签用来创建含有不少于三个边的图形。  
   多边形是由直线组成，其形状是"封闭"的（所有的线条 连接起来）  
   * points 属性定义多边形每个角的 x 和 y 坐标  
   ```
   <svg version="1.1">
        <polygon points="200,10 250,190 160,210"
        style="fill:lime;stroke:purple;stroke-width:1"/>
    </svg>
   ```    
   * SVG的图形填充规则通过fill-rule属性来指定。  
   nonzero  : 字面意思是“非零”。按该规则，要判断一个点是否在图形内，从该点作任意方向的一条射线，然后检测射线与图形路径的交点情况。从0开始计数，路径从左向右穿过射线则计数加1，从右向左穿过射线则计数减1。得出计数结果后，如果结果是0，则认为点在图形外部，否则认为在内部。   
  evenodd : 字面意思是“奇偶”。按该规则，要判断一个点是否在图形内，从该点作任意方向的一条射线，然后检测射线与图形路径的交点的数量。如果结果是奇数则认为点在内部，是偶数则认为点在外部。
   ```
   <svg version="1.1">
    <polygon points="100,10 40,180 190,60 10,60 160,180"
    style="fill:lime;stroke:purple;stroke-width:5;fill-rule:nonzero;" />
    </svg>
   ```  
   # SVG 曲线 - 《polyline》    
   * points 属性定义多边形每个角的 x 和 y 坐标
   ```
   <svg  version="1.1">
        <polyline points="0,40 40,40 40,80 80,80 80,120 120,120 120,160" style="fill:white;stroke:red;stroke-width:4" />
    </svg>
   ```  
   # SVG 路径 - 《path》  
   《path》 元素用于定义一个路径。  
   下面的命令可用于路径数据：  
* M = moveto （移至）
* L = lineto （画连接线）
* H = horizontal lineto （水平线）
* V = vertical lineto （垂直线）
* C = curveto （画弧线)
* S = smooth curveto   (光滑曲线)
* Q = quadratic Bézier curve  (二次 曲线)
* T = smooth quadratic Bézier curveto  (光滑二次弧线)
* A = elliptical Arc (椭圆弧)
* Z = closepath (闭合)
* 注意：以上所有命令均允许小写字母。大写表示绝对定位，小写表示相对定位。  
```
      <svg  version="1.1">
        <path d="M150 0 L75 200 L225 200 Z" />
    </svg>
```  
* 下面的例子创建了一个二次方贝塞尔曲线，A 和 C 分别是起点和终点，B 是控制点：  
```
<svg  version="1.1" height="400" width="450">
    <path id="lineAB" d="M 100 350 l 150 -300" stroke="red" stroke-width="3" fill="none" />
    <path id="lineBC" d="M 250 50 l 150 300" stroke="red" stroke-width="3" fill="none" />
    <path d="M 175 200 l 150 0" stroke="green" stroke-width="3" fill="none" />
    <path d="M 100 350 q 150 -300 300 0" stroke="blue" stroke-width="5" fill="none" />
<!-- 标记相关点 -->
  <circle id="pointA" cx="100" cy="350" r="5" />
  <circle id="pointB" cx="250" cy="50" r="5" />
  <circle id="pointC" cx="400" cy="350" r="5" />
<!-- 标注要点 -->
  <text x="100" y="350" dx="-30" font-size="30"> A</text>
  <text x="250" y="50"  dy="-10" font-size="30">B</text>
  <text x="400" y="350" dx="30" font-size="30">C</text>
</svg>
```    
# SVG 文本 - 《text》    
《text》 元素用于定义文本。  
```
<svg   version="1.1">
  <text x="0" y="15" fill="red">I love SVG</text>
</svg>
```
# SVG Stroke 属性  
* stroke
* stroke-width
* stroke-linecap
* stroke-dasharray  
## Stroke属性定义一条线，文本或元素轮廓颜色： 
``` 
<svg  version="1.1">
    <path stroke="red" d="M5 20 l215 0" />
    <path stroke="blue" d="M5 40 l215 0" />
    <path stroke="black" d="M5 60 l215 0" />
</svg>
```  
## stroke-width 属性 定义了一条线，文本或元素轮廓厚度  
```
<svg   version="1.1">
  <g fill="none" stroke="black">
    <path stroke-width="2" d="M5 20 l215 0" />
    <path stroke-width="4" d="M5 40 l215 0" />
    <path stroke-width="6" d="M5 60 l215 0" />
  </g>
</svg>
```  
## stroke-linecap属性定义不同类型的开放路径的终结：  
```
<svg   version="1.1">
  <g fill="none" stroke="black" stroke-width="6">
    <path stroke-linecap="butt" d="M5 20 l215 0" />
    <path stroke-linecap="round" d="M5 40 l215 0" />
    <path stroke-linecap="square" d="M5 60 l215 0" />
  </g>
</svg>
```
## stroke-dasharray属性用于创建虚线：  
```
<svg version="1.1">
  <g fill="none" stroke="black" stroke-width="4">
    <path stroke-dasharray="5,5" d="M5 20 l215 0" />
    <path stroke-dasharray="10,10" d="M5 40 l215 0" />
    <path stroke-dasharray="20,10,5,5,5,10" d="M5 60 l215 0" />
  </g>
</svg>
```