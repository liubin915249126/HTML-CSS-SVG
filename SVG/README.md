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
```
>
