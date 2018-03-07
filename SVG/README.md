## SVG 相关学习
#### SVG
>
  SVG 指可伸缩矢量图形 (Scalable Vector Graphics)
> 
#### SVG viewBox
>
<svg width="500" height="300"></svg>
viewport svg 实际大小
</br>
viewBox="x, y, width, height"  // x:左上角横坐标，y:左上角纵坐标，width:宽度，height:高度
</br>
视区盒子：以视区盒子大小选中元素然后缩放至viewport的大小

![viewBox](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/viewbox.gif);
</br> 
preserveAspectRatio()
第1个值表示，viewBox如何与SVG viewport对齐；第2个值表示，如何维持高宽比（如果有)
```
  meet	保持纵横比同时比例大的方向缩放适应viewport
  slice	保持纵横比同时比例小的方向缩放适应viewport
  none	扭曲纵横比以充分适应viewport 
```
参考文章 [张鑫旭](http://www.zhangxinxu.com/wordpress/2014/08/svg-viewport-viewbox-preserveaspectratio/)
>
#### 渐变
##### 线性渐变
>
先定义再引用
```
   <svg width="660" height="220">
        <defs>
            <linearGradient id="linear" x1="0%" y1="0%" x2="100%" y2="0%">
                <stop offset="0%" stop-color="#05a" />
                <stop offset="50%" stop-color="#a55" />
                <stop offset="100%" stop-color="#0a5" />
            </linearGradient>
        </defs>
    </svg>
    <svg width="660" height="220">
        <rect x="10" y="10" width="600" height="200" fill="url(#linear)" />
    </svg>
    <svg width="660" height="220"> 
        <rect x="10" y="10" width="600" height="200" stroke="url(#linear)" stroke-width="20" fill="#fff"/>
    </svg>
```
gradientUnit属性
```
  userSpaceOnUse:(默认值) x1、y1、x2、y2表示当前用户坐标系统的坐标。也就是说渐变中的值都是绝对值。
  objectBoundingBox: x1, y1, x2, y2表示应用渐变的元素创建的边界坐标系统。也就是说渐变随着应用的元素进行了缩放。
```
spreadMethod属性
```
  pad: （默认值）使用渐变的颜色结点来填充剩余的空间。例如，如果第一个结点是20%，那么0%到20%这部分就是相同的颜色。
  reflect: 映射渐变图案，从'start-to-end'，再从'end-to-start'，然后'start-to-end'，直到空间都填满了。
  repeat: 重复渐变图案，从起点->终点，直到空间填满。
```
>
##### 径向渐变
>
先定义再引用
``` 
   <svg width="660" height="330">
        <defs>
            <radialGradient id="radial" fx="50%" fy="50%" cx="50%" cy="50%" r="50%">
                <stop offset="0%" stop-color="#05a" stop-opacity="1" />
                <stop offset="100%" stop-color="#0a5" stop-opacity="1" /> 
            </radialGradient>
        </defs>
        <rect x="0" y="0" width="600" height="300" fill="url(#radial)" /> 
    </svg>

```
stop的属性
```
  offset: 在径向渐变中，它表示从点(fx,fy)到外边缘的圆的百分比值距离。它定义了渐变结点的位置。值从0到1之间，或者0%到100%。
  stop-color: 定义offset结点位置的颜色
  stop-opacity: 定义颜色结点的透明度，值从0到1，或0%到100%。
```
gradientUnit属性和spreadMethod属性类似于线性渐变

焦点：
![focus](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/SVG_Radial_Grandient_Focus.png)

>

#### 基本形状
>
```
矩形 rect:   x:矩形左上角的x坐标  
            y:矩形左上角的y坐标  
            width:矩形的宽度 
            height:矩形的高度  
            rx:对于圆角矩形,圆角对应的椭圆在x方向上的半径  
            ry:对于圆角矩形,圆角对应的椭圆在y方向上的半径  
圆 circle cx:圆心的x坐标  
            cy:圆心的y坐标  
            r:圆的半径  
椭圆 ellipse cx:椭圆心的x坐标  
              cy:椭圆心的y坐标  
              rx:椭圆的x轴半径   
              ry:椭圆的Y轴半径  
线段 line  x1:起点的x坐标  
            y1:起点的y坐标  
            x2:终点的x坐标  
            y2:重点的y坐标  
多边形 polygon points各个点的坐标
```                                                      
>
#### path基本相关属性
>
```
   fill //填充(线条包裹的区间)颜色 
   stroke //定义一条线，文本或元素轮廓颜色 
   stroke-width //定义一条线，文本或元素轮廓厚度
   stroke-linecap //butt | round | square | inherit
```  
>
#### stroke-dasharray,stroke-dashoffset
>
```
stroke-dasharray:绘制虚线:一个参数时： 表示一段虚线长度和每段虚线之间的间距 
                          两个参数或者多个参数时：一个表示长度，一个表示间距 
stroke-dashoffset: 表示虚线的起始偏移                     
```
>
#### path d 路径相关
>
直线命令：
```
   M:将画笔移动 M10,10(两个参数)
   H:画水平线 H100(一个参数)
   V:画竖直线 V100(一个参数)
   Z:闭合(无参数)
``` 
以上命令大写表示绝对位置(明确的坐标)，小写表示相对坐标(相对于前一个点的坐标)

曲线命令：
```
  C 三次贝塞尔曲线 x1 y1, x2 y2, x y (or c dx1 dy1, dx2 dy2, dx dy)
    x1 y1, x2 y2 两个不同的控制点
    x y 终点

  S x2 y2, x y (or s dx2 dy2, dx dy)
    （S命令可以用来创建与之前那些曲线一样的贝塞尔曲线，但是，如果S命令跟在一个C命令或者另一个S命令的后面，
    它的第一个控制点，就会被假设成前一个控制点的对称点。如果S命令单独使用，前面没有C命令或者另一个S命令，
    那么它的两个控制点就会被假设为同一个点。）

  Q x1 y1, x y (or q dx1 dy1, dx dy)
    x1 y1 控制点确定起点终点的斜率
    x y 终点坐标

  T 二次贝塞尔曲线 x y (or t dx dy)
    和之前一样，快捷命令T会通过前一个控制点，推断出一个新的控制点。这意味着，在你的第一个控制点后面，
    可以只定义终点，就创建出一个相当复杂的曲线。需要注意的是，T命令前面必须是一个Q命令，或者是另一个T命令，
    才能达到这种效果。如果T单独使用，那么控制点就会被认为和终点是同一个点，所以画出来的将是一条直线。 

  A:画弧形 A rx ry x-axis-rotation large-arc-flag sweep-flag x y：
     rx,ry:表示弧形X,Y轴半径,
     x-axis-rotation: 弧形的旋转情况(顺时针为正)(0不旋转)
     large-arc-flag:角度大小(0表示小角度弧，1表示大角度弧)  
     sweep-flag:弧线方向(0表示从起点到终点沿逆时针画弧，1表示从起点到终点沿顺时针画弧)
     x,y:弧的终点坐标      
```

三次贝塞尔曲线C:![三次贝塞尔曲线](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/Cubic_Bezier_Curves.png)
三次贝塞尔曲线S:![三次贝塞尔曲线](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/ShortCut_Cubic_Bezier.png)

二次贝塞尔曲线Q:![二次贝塞尔曲线](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/Quadratic_Bezier.png)
二次贝塞尔曲线T:![二次贝塞尔曲线](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/Shortcut_Quadratic_Bezier.png)
>

>
弧线命令A：
```
   <svg width="325px" height="325px" version="1.1" xmlns="http://www.w3.org/2000/svg">
      <path d="M80 80
              A 45 45, 0, 0, 0, 125 125
              L 125 80 Z" fill="green"/>
      <path d="M230 80
              A 45 45, 0, 1, 0, 275 125
              L 275 80 Z" fill="red"/>
      <path d="M80 230
              A 45 45, 0, 0, 1, 125 275
              L 125 230 Z" fill="purple"/>
      <path d="M230 230
              A 45 45, 0, 1, 1, 275 275
              L 275 230 Z" fill="blue"/>
   </svg> 
```

![A](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/SVGArcs_Flags.png)


参考文档[MDN](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Tutorial/Paths);
>
#### 应用
![半圆](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/half.gif)
![loading](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/loading.gif)
![hover](https://github.com/liubin915249126/HTML-CSS-SVG/blob/master/SVG/image/hover.gif)