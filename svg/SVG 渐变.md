# SVG 渐变
渐变是一种从一种颜色到另一种颜色的平滑过渡。另外，可以把多个颜色的过渡应用到同一个元素上。
在 SVG 中，有两种主要的渐变类型：

*  线性渐变
*  放射性渐变


## 线性渐变


<svg width="500" height="400">

  <linearGradient id="linear_gradient">
    <stop offset="0%" stop-color="#39c0ff"/>
    <stop offset="100%" stop-color="#ff60c9"/>
  </linearGradient>
  
  <rect x="0" y="0" width="500" height="400" style="fill:url(#linear_gradient);"/>
  <text x="50%" y="50%" font-size="72" text-anchor="middle"  font-family="monospace" fill="#ffffff" >svg</text>

</svg>

`<linearGradient>` 可用来定义 SVG 的线性渐变。  

```svg
<svg width="500" height="400">

  <linearGradient id="linear_gradient">
    <stop offset="0%" stop-color="#39c0ff"/>
    <stop offset="100%" stop-color="#ff60c9"/>
  </linearGradient>
  
  <rect x="0" y="0" width="500" height="400" style="fill:url(#linear_gradient);"/>
  <text x="50%" y="50%" font-size="72" text-anchor="middle"  font-family="monospace" fill="#ffffff" >svg</text>

</svg>
```


##  放射性渐变
`<radialGradient>` 用来定义放射性渐变。



<svg width="500" height="400" >
  
  <radialGradient id="radial_gradient">
     <stop offset="0%" style="stop-color:#09f47f;stop-opacity:0.6"/>
     <stop offset="100%" style="stop-color:#e4d4fe; stop-opacity:1"/>
  </radialGradient>
  
  <circle cx="200" cy="200" r="110" style="fill:url(#radial_gradient)"/>

</svg>

```
<svg width="500" height="400" >
  
  <radialGradient id="radial_gradient">
     <stop offset="0%" style="stop-color:#09f47f;stop-opacity:0.6"/>
     <stop offset="100%" style="stop-color:#e4d4fe; stop-opacity:1"/>
  </radialGradient>
  
  <circle cx="200" cy="200" r="110" style="fill:url(#radial_gradient)"/>

</svg>
```
