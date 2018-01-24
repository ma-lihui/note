# SVG简介 
> SVG 是使用 XML 来描述二维图形和绘图程序的语言。

* SVG 指可伸缩矢量图形 (Scalable Vector Graphics)
* SVG 用来定义用于网络的基于矢量的图形
* SVG 使用 XML 格式定义图形
* SVG 图像在放大或改变尺寸的情况下其图形质量不会有所损失

# SVG 的优势
与其他图像格式相比（比如 JPEG 和 GIF），使用 SVG 的优势在于：
* SVG 图像可通过文本编辑器来创建和修改
* SVG 可在图像质量不下降的情况下被放大
* SVG 图像中的文本是可选的，同时也是可搜索的

# SVG 实例

```
<svg width="300" height="150">
  <rect width="100" height="80" x="50" y="10" fill=" #a0e29e" stroke="#46e2ff"  stroke-width="6" />
</svg>
```
<svg width="300" height="150">
  <rect width="100" height="80" x="50" y="10" fill=" #a0e29e" stroke="#46e2ff"  stroke-width="6" />
</svg>


SVG 代码以 `<svg> `元素开始，包括开启标签` <svg>` 和关闭标签 `</svg>` 。这是根元素。width 和 height 属性可设置此 SVG 文档的宽度和高度。
`<rect>`元素用于创建矩形，`width` 和 `height` 属性设置矩形的宽和高。`x`、`y`设置矩形的坐标。`fill`设置填充颜色。`stroke`设置轮廓的颜色，`stroke-width`设置轮廓的宽度。