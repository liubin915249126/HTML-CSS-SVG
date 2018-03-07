#### svg动画
aniamte
```
  attributeName	动画中改变的值
  attributeType	width是一个XML属性，另一个常用的值是CSS，如果忽略这个值，则默认是auto，会先搜索CSS属性，再搜索XML属性
  from to	by 起始值和结束值和偏移量
  values	from和to只能指定两个值，使用values时可以以列表形式同时指定多个中间值，变换会依次使用列表内的值。如果要交替动画，则指定为start,end,start三个即可实现
  begin dur	end 动画开始时间 持续时间 动画结束时间
  fill	结束时该怎么做，freeze表示冻结，如果不指定会使用默认值：remove，表示动画完成后会返回原始值。
  repeatCount	动画重复次数 
  repeatDur	重复应该进行多长时间(在时间内)
  calcMode	过渡类型，可以为线性(linear)，直接跳转(不支持过渡时直接跳转到结束值discrete)，spline，paced等。
```