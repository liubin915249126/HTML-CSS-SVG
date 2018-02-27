## SVG 相关学习

#### 1.path基本相关属性
>
```
   fill //填充(线条包裹的区间)颜色 
   stroke //定义一条线，文本或元素轮廓颜色 
   stroke-width //定义一条线，文本或元素轮廓厚度
```  
>
#### 2.stroke-dasharray,stroke-dashoffset
>
stroke-dasharray:绘制虚线:一个参数时： 表示一段虚线长度和每段虚线之间的间距 
                          两个参数或者多个参数时：一个表示长度，一个表示间距 
stroke-dashoffset: 表示虚线的起始偏移                     
>
#### 3.d 路径相关
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
  A:画弧形 A rx ry x-axis-rotation large-arc-flag sweep-flag x y：
     rx,ry:表示弧形X,Y轴半径,
     x-axis-rotation: 弧形的旋转情况(顺时针为正)
     large-arc-flag:角度大小(0表示小角度弧，1表示大角度弧)  
     sweep-flag:弧线方向(0表示从起点到终点沿逆时针画弧，1表示从起点到终点沿顺时针画弧)
     x,y:弧的终点坐标
  C 三次贝塞尔曲线 x1 y1, x2 y2, x y (or c dx1 dy1, dx2 dy2, dx dy)
    x1 y1, x2 y2 两个不同的控制点
    x y 终点
  S x2 y2, x y (or s dx2 dy2, dx dy)
    （S命令可以用来创建与之前那些曲线一样的贝塞尔曲线，但是，如果S命令跟在一个C命令或者另一个S命令的后面，它的第一个控制点，就会被假设成前一个控制点的对称点。如果S命令单独使用，前面没有C命令或者另一个S命令，那么它的两个控制点就会被假设为同一个点。）
  Q x1 y1, x y (or q dx1 dy1, dx dy)
    x1 y1 控制点确定起点终点的斜率
    x y 终点坐标
  T x y (or t dx dy)
    和之前一样，快捷命令T会通过前一个控制点，推断出一个新的控制点。这意味着，在你的第一个控制点后面，可以只定义终点，就创建出一个相当复杂的曲线。需要注意的是，T命令前面必须是一个Q命令，或者是另一个T命令，才能达到这种效果。如果T单独使用，那么控制点就会被认为和终点是同一个点，所以画出来的将是一条直线。     
```
参考文档[MDN](https://developer.mozilla.org/zh-CN/docs/Web/SVG/Tutorial/Paths);
>
