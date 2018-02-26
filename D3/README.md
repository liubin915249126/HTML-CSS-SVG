## D3.js study

#### scale 比例尺

range输出

线性比例尺
>
 ```
    var linearScale = d3.scaleLinear()
        .domain([0, 10])
        .range([0, 600]);
 ```
>
>
scaleBand会将range划分为n个bands(n是domain数组的数值个数)并且在考虑padding的情况下计算出每个band的位置和宽度.
domain()中使用一个数组，不过range()需要是一个连续域
```
  var bandScale = d3.scaleBand()
    .domain(['Mon', 'Tue', 'Wed', 'Thu', 'Fri'])
    .range([0, 200]);
```
>
>
scaleOrdinal
d3.scaleOrdinal()的输入域和输出域都使用离散的数据。
>

#### d3动画
>
  缓动函数：
  [
      "linear", "cubic", "cubic-in-out", 
      "sin", "sin-out", "exp", "circle", "back", 
      "bounce",
      function(t){ // 自定义函数
            return t * t;
      }
  ]
  ease();
>
#### 参考文献:
demo:
[博客](https://www.cnblogs.com/fastmover/p/7779660.html)
[github](https://github.com/nelsonkuang/ant-admin/)