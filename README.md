
## Bootstrap

### Compatible

> 文旦兼容模式，表示如果在 IE 浏览器下则使用最新的标准渲染当前文档

``` HTML
<meta http-equiv="X-UA-Compatible" content="IE=edge">
```

### 视口

``` HTML
<meta name="viewport" content="width=device-width,initial-scale=1">
```

- 适口的作用：在移动浏览器中，当页面宽度超出设备，浏览器内部虚拟的一个页面，将页面容器缩放到设备这个大，然后展示
- 目前大多数收集浏览器的视口（承载页面的容器）宽度都是980
- 视口的宽度可以通过 meta 标签设置
- 此属性为移动端页面适口设置，当前值标识在移动端页面的宽度为设备的宽度，并缩放（缩放级别为1）
  - width: 视口的宽度
  - initial-scale：初始化缩放
  - user-scalable: 是否允许用户自行缩放（value:{yes|no},{1|0}）
  - minimun-scale: 最小缩放
  - maxmun-scale: 最大缩放