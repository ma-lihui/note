# SVG 滤镜
** SVG 滤镜用来向形状和文本添加特殊的效果。 **  

在 SVG 中，可用的滤镜有：
* feBlend
* feColorMatrix
* feComponentTransfer
* feComposite
* feConvolveMatrix
* feDiffuseLighting
* feDisplacementMap
* feFlood
* feGaussianBlur
* feImage
* feMerge
* feMorphology
* feOffset
* feSpecularLighting
* feTile
* feTurbulence
* feDistantLight
* fePointLight
* feSpotLight


## 高斯模糊（Gaussian Blur）
`<filter>` 标签用来定义 SVG 滤镜。
```
<svg>
  <filter id="Gaussian_Blur">
  	<feGaussianBlur in="SourceGraphic"  stdDeviation="5" />
  </filter>
  <ellipse cx="100" cy="50" rx="70" ry="40" style="fill:#3498db;filter:url(#Gaussian_Blur)"/>
</svg>
```
<svg>
  <filter id="Gaussian_Blur">
  	<feGaussianBlur in="SourceGraphic"  stdDeviation="5" />
  </filter>
  <ellipse cx="100" cy="50" rx="70" ry="40" style="fill:#3498db;filter:url(#Gaussian_Blur)"/>
</svg>

## 多个滤镜叠加使用
```
  <svg width="600" height="200">
    <defs>
      <filter id="goo">
        <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
        <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -8" result="goo" />
      </filter>
    </defs>
    <g filter="url(#goo)">
      <circle class="dot" cx="50" cy="50" r="25" fill="#f1c40f" />
      <circle class="dot" cx="105" cy="50" r="25" fill="#ff5050" />
    </g>
  </svg>
```
  
  <svg width="600" height="200">
    <defs>
      <filter id="goo">
        <feGaussianBlur in="SourceGraphic" stdDeviation="10" result="blur" />
       <feColorMatrix in="blur" mode="matrix" values="1 0 0 0 0  0 1 0 0 0  0 0 1 0 0  0 0 0 19 -8" result="goo" />
      </filter>
    </defs>
    <g filter="url(#goo)">
      <circle class="dot" cx="50" cy="50" r="25" fill="#f1c40f" />
      <circle class="dot" cx="105" cy="50" r="25" fill="#ff5050" />
    </g>
  </svg>
