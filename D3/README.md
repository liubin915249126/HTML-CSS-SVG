## D3.js study

#### scale 比例尺
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
```
  var bandScale = d3.scaleBand()
    .domain(['Mon', 'Tue', 'Wed', 'Thu', 'Fri'])
    .range([0, 200]);
```
>