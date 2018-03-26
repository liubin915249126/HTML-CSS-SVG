#### float,absolute,inline-block
```css
   float 文字环绕效果
   absolute，float脱离文档流
   float 父元素高度塌陷
   float,absolute,inline-block包裹性
   absolute left right流体特性
   absolute:定位在border box (box-sizing 无效)
   float：content box 
```
#### margin
元素充分利用可用空间，margin才能改变元素可视尺寸
元素设定了宽度(100%),或是包裹性的时候对尺寸没有影响

margin负值：
absolute 设置了left,right流体特性，设置了宽度分两种情况
float margin-bottom 要一行全部相同
      margin-top 向上
inline-block水平方向有影响分两种情况
#### 1.BFC 定义
```js
   BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level box参与， 它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干。
```
#### 2.BFC布局规则：
```js
    (内部的Box会在垂直方向，一个接一个地放置。block
    每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。inline float)
    Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠
    BFC的区域不会与float box重叠(absolute 与float会重叠)
    BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素。反之也如此。
    计算BFC的高度时，浮动元素也参与计算
```
#### 3.怎样触发BFC
```css
    根元素
    float属性不为none
    position为absolute或fixed
    display为inline-block, table-cell, table-caption, flex, inline-flex
    overflow不为visible
```
#### flex
```css
   display:flex; //触发
```
```css
    flex-direction: row | row-reverse | column | column-reverse; 属性决定主轴的方向（即项目的排列方向）。
    flex-wrap: nowrap | wrap | wrap-reverse; 决定如何换行
    flex-flow
    justify-content: flex-start | flex-end | center | space-between | space-around;
    align-items: flex-start | flex-end | center | baseline | stretch; /* 如果项目未设置高度或设为auto，将占满整个容器的高度。 */
    align-content
```
```css
   order: <integer>; //项目排列顺序，越大越靠后
   flex-grow：<integer>; //属性定义项目的放大比例，默认为0，即如果存在剩余空间，也不放大。
   flex-shrink: <number>; /* default 1 */
   flex-basis: <length> | auto; /* default auto */属性定义了在分配多余空间之前，项目占据的主轴空间（main size）
   align-self: auto | flex-start | flex-end | center | baseline | stretch;可覆盖align-items属性。默认值为auto，表示继承父元素的align-items属性，如果没有父元素，则等同于stretch
```