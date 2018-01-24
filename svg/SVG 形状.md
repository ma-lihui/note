# SVG 形状
SVG 有一些预定义的形状元素，可被开发者使用和操作：

* 矩形 `<rect>`
* 圆形 `<circle>`
* 椭圆 `<ellipse>`
*  线 `<line>`
* 折线` <polyline>`
* 多边形 `<polygon>`
* 路径 `<path>`


## `<rect>` 标签
`<rect>` 标签可用来创建矩形，以及矩形的变种
```
<svg width="100%">
  <rect width="100" height="80" x="50" y="10" fill=" #a0e29e" stroke="#46e2ff"  stroke-width="6" ></rect>
</svg>
```
<svg width="100%">
  <rect width="100" height="80" x="50" y="10" fill=" #a0e29e" stroke="#46e2ff"  stroke-width="6" ></rect>
</svg>



创建带有圆角的矩形：
```
<svg width="100%">
  <rect width="100" height="80" rx="10" ry="10" x="50" y="10" fill="#89dcc1"></rect>
</svg>
```
<svg width="100%">
  <rect width="100" height="80" rx="10" ry="10" x="50" y="10" fill="#89dcc1"></rect>
</svg>



## `<circle>` 标签
`<circle>` 标签可用来创建一个圆。
```
<svg width="100%">
  <circle cx="100" cy="50" r="40" fill="#ff5050"/>
</svg>
```
<svg width="100%">
  <circle cx="100" cy="50" r="40" fill="#ff5050"/>
</svg>


## `<ellipse>` 标签
`<ellipse>` 标签可用来创建椭圆。椭圆与圆很相似。不同之处在于椭圆有不同的 x 和 y 半径，而圆的 x 和 y 半径是相同的。
```
<svg width="100%">
  <ellipse cx="150" cy="80" rx="100" ry="60" fill="#ffff50"/>
</svg>
```
<svg width="100%">
  <ellipse cx="150" cy="80" rx="100" ry="60" fill="#ffff50"/>
</svg>

## `<polygon>` 标签
`<polygon>` 标签用来创建含有不少于三个边的图形。
```
<svg width="100%">
  <polygon points="20,20 20,100 100,100 "  fill="#fd67df"   />
</svg>
```
<svg width="100%">
  <polygon points="20,20 20,100 100,100 "  fill="#fd67df"   />
</svg>

## `<line>` 标签
`<line>` 标签用来创建线条。
```
<svg width="100%">
  <line x1="0" y1="0" x2="300" y2="300"  stroke="#191919" />
</svg>
```
<svg width="100%">
  <line x1="0" y1="0" x2="300" y2="300"  stroke="#191919" />
</svg>

## `<polyline>` 标签
`<polyline>` 标签用来创建线条。
```
<svg width="100%">
  <polyline points="20,20 20,100 100,100 100,60"  fill="transparent"  stroke="#191919" />
</svg>
```
<svg width="100%">
  <polyline points="20,20 20,100 100,100 100,60"  fill="transparent"  stroke="#191919" />
</svg>


## `<path>` 标签
`<path>` 标签用来定义路径。
下面的命令可用于路径数据：

| 命令        | 名称           | 参数  |
|:------------- |:-------------|:-----|
| M     | moveto  移动到 | (x y)+ |
| L     | lineto  画线到      |   	(x y)+ |
| H | horizontal lineto  水平线到    |    x+ |
| V     | vertical lineto  垂直线到 | y+ |
| C     | curveto  三次贝塞尔曲线到    |   (x1 y1 x2 y2 x y)+ |
| S | smooth curveto  光滑三次贝塞尔曲线到    |    (x2 y2 x y)+ |
| Q     | quadratic Bézier curveto  二次贝塞尔曲线到 | (x1 y1 x y)+ |
| T     | smooth quadratic Bézier curveto  光滑二次贝塞尔曲线到      |   (x y)+ |
| A | elliptical arc  椭圆弧    |    (rx ry x-axis-rotation large-arc-flag sweep-flag x y)+ |
| Z | closepath  关闭路径     |    (none) |
>  以上所有命令均允许小写字母。大写表示绝对定位，小写表示相对定位。

```
<svg width="300" height="100" viewBox="0 0 20 60">
    <path  stroke="#D75A4A" stroke-width="2" fill="transparent" d="M14 26c-0.25 0-0.5-0.094-0.688-0.281
    l-9.75-9.406c-0.125-0.109-3.563-3.25-3.563-7 0-4.578 2.797-7.313 7.469-7.313 2.734 0 5.297 2.156 6.531
    3.375 1.234-1.219 3.797-3.375 6.531-3.375 4.672 0 7.469 2.734 7.469 7.313 0 3.75-3.437 6.891-3.578 7.031
    l-9.734 9.375c-0.187 0.187-0.438 0.281-0.688 0.2,5.83-2.58,8.89,8.89,0,0,1,6.31,2.58,8.5,8.5,0,0,1,.13,12l-.13.13Z"/>
 </svg>
```
<svg width="300" height="100" viewBox="0 0 20 60">
    <path  stroke="#D75A4A" stroke-width="2" fill="transparent" d="M14 26c-0.25 0-0.5-0.094-0.688-0.281l-9.75-9.406c-0.125-0.109-3.563-3.25-3.563-7 0-4.578 2.797-7.313 7.469-7.313 2.734 0 5.297 2.156 6.531 3.375 1.234-1.219 3.797-3.375 6.531-3.375 4.672 0 7.469 2.734 7.469 7.313 0 3.75-3.437 6.891-3.578 7.031l-9.734 9.375c-0.187 0.187-0.438 0.281-0.688 0.281z"/>
</svg>


> 可以看出来svg路径很复杂，也很不直观。所以通常我们用绘图工具画出路径，然后导出为svg文件。

