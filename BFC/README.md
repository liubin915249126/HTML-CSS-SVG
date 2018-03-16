#### margin负值
两种情况
#### float,absolute,inline-block
```css
   float 文字环绕效果
   float,absolute脱离文档流
   float,absolute,inline-block包裹性
   absolute:定位在border box
   float：content box 
```
#### 1.BFC 定义
```js
   BFC(Block formatting context)直译为"块级格式化上下文"。它是一个独立的渲染区域，只有Block-level box参与， 它规定了内部的Block-level Box如何布局，并且与这个区域外部毫不相干。
```
#### 2.BFC布局规则：
```js
    内部的Box会在垂直方向，一个接一个地放置。
    Box垂直方向的距离由margin决定。属于同一个BFC的两个相邻Box的margin会发生重叠
    每个元素的margin box的左边， 与包含块border box的左边相接触(对于从左往右的格式化，否则相反)。即使存在浮动也是如此。
    BFC的区域不会与float box重叠。
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
    align-items: flex-start | flex-end | center | baseline | stretch;
    align-content
```
