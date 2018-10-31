# CSS3

## [CSS3 属性选择器](./demo/attribute_selector.html)

- E[attr~="value"] 属性值是一个词列表，并且以空格隔开，其中次列表中包含了一个 value 词，而且等号前面的“~”不能大写
- E[attr^="value" value **开头属性值**
- E[attr$="value"] value **结尾属性值**
- E[attr] 有 attr **属性**
- E[attr="value"] 属性值 **相等**
- E[attr*="value"] 属性中包含了 value **包含**
- E[attr|="value"] 属性中包含了 value或者 **value-开头的值**（比如：zh-cn）

## [CSS3 结构伪类选择器](./demo/structure_selector.html)

- E:nth-child(n)：E父元素中的第 n 个字节点
  - p:nth-child(odd) {} 匹配奇数行
  - p:nth-child(even) {} 匹配偶数行
  - p:nth-child(2n) {} 偶数行
  - p:nth-child(2n-1) {} 奇数行

- E:nth-last-child(n) 表示 E 父元素中的第 n  个字节点，从后向前计算
- E:nth-of-type(n) 表示 E 父元素中的第 n 个字节点，且类型为 E
- E:nth-last-of-type(n) 表示 E 父元素中的第 n 个字节点，且类型为 E，从后向前计算
- E:empty() 表示E元素中没有子节点，注意：子节点包括文本节点

- :first-child == :nth-child(1)
- :last-child == :nth-last-child(1)
- :first-of-type == nth-of-type(1)
- :last-of-type == nth-last-of-type(1)

- E:first-child 表示 E 元素中的第一个子节点
- E:last-child 表示 E 元素中的最后一个子节点
- E:first-of-type 表示 E 元素中的第一个子节点且节点类型是 E 的
- E:last-of-type 表示 E 元素中最后一个子节点且节点类型是 E 的
- E:only-child 表示 E 元素中只有一个子节点，注意：自己诶但不包含文本节点
- E：only-of-type 表示 E 父元素中只有一个子节点，且这个唯一的子节点的类型必须是E。注意：子节点不包括文本节点

## [伪类选择器](./demo/weilei_selector.html)

- E:target 表示当前的URL片段的元素类型，这个元素必须是E
- E:disabled 不可点击的表单控件
- E:enabled 可点击的表单控件
- E:checked 已选中的 checkbox 或 radio
- E:first-line E 元素中的第一行
- E:first-letter
- E::selection 表示 E 元素在用户选中文字时
- E::before 生成内容在E 元素之前
  - .c1:before{content:'*',color:red}
- E::after
- E:not(s) 表示 E 元素不被匹配
- E~F 表示E元素挨着的F元素
- Content 属性

- 脱离文档流
  - float
  - absolute
  - fixed

- rgba() 只改变背景颜色的透明度效果（opacity改变元素和其子元素的透明效果）
- 文字阴影：text-shadow: 2px 2px 4px black;
- 阴影叠加：text-shadow: 2px 2px 0px red, 2px 2px 4px green;
- 层叠：color:red;font-size:100px;font-weight:bold;text-shadow:2px 2px 0px white,4px 4px 0px red;
- 光晕：color:white;font-size:100px;text-shadow:0 0 10px #fff,0 0 20px #fff,0 0 30px #fff, 0 0 40px #ff00de, 0 0 70px #ff00de, 0 0 80px #ff00de, 0 0 100px #ff00de, 0 0 150px #ff00de;
- 文字描边：-webkit-text-stroke: 宽度 颜色;
- 文字排列：direction: rtl | ltr; rtl: 从右向左排列; ltr: 从左向右排列
  - 注意要配合 unicode-bidi  一块使用
- text-overflow: clip | ellipsis;
  - ellipsis省略号 注意配合`text-overflow:ellipsis;overlfow:hidden;white-space:nowrap;` 一块使用

## 自定义文字

``` font
@font-face {
  font-faimily: 'wovert';
  src:url('wovert-webfont.eot');
  src:url(wovert-webfont.eot?#iefix) format('embedded-opentype'),
   url('wovert-webfont.woff') format('woff'),
   url('wovert-webfont.tty') format('truetype'),
   url('wovert-webfont.svg#untitledregular') format('svg');
  font-weight: normal;
  font-style: normal;
}
```

- [转换字体格式生成兼容代码](http://fontsquirrel.com/fontface/generator)

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

## 老师浏览器支持 HTML5

``` HTML
<!--[if IE]>
<script src="http://html5shiv.googlecode.com/svn/trunk/html5.js"></script>
<![endif]-->
<style>
  width: 50px;
  height: 50px;
  background: rgb(167, 255 ,109);
  -moz-border-radius: 15px; /* Firefox */
  -webkit-border-radius: 15px; /* Safari and Chrome*/
  border-radius: 15px; /* Opera 10.5+, future browsers, and now also Internet Explorer 6+ using IE-CSS3  */
  -moz-box-shadow: 10px 10p 20px #000; /* Firefox */
  -webkit-box-shadow: 10px 10px 20px #000; /* Sfari and Chrome */
  box-shadow: 10px 10px 20px #000; /* Opera 10.5+, future browsers and IE6+ using IE-CSS# */
  behavior: url(ie-css3.htc); /* IE6模仿大部分CSS3  */
  /*
    IE中的 CSS3不完全兼容方案
    www.cnblogs.com/platero/archive/2010/08/31/1870151.html
  */

</style>
```

### 实例

[Flex 布局](./flexbox-playground/index.html)

[瀑布流](./pubu-fenlan/picEnd.html)

[文本分栏](./pubu-fenlan/textEnd.html)

[媒体查询](./MediaQuery/textEnd.html)

[响应式表格](./responsive-table/end.html)

[响应式图片](./responsive-pic/end.html)

## float

> 任何元素浮动之后都会变成块元素

## clear 清除浮动(清除的是浮动带来的负面效果 -> 父标签塌陷(撑不起来))

最常和伪元素结合起来应用

``` shell
.clearfix:after {
  content: "";
  display: block;
  clear: both
}
```

## font-family

``` CSS
font-family: "Microsoft Yahei", "微软雅黑", "Arial", sans-serif;
```

## background

### background-clip

> 背景图像区域：background-clip

- border-box 背景被裁剪到边框盒
- padding-box 背景被裁剪到内边距框
- content-box 背景被裁剪到内容框
- 兼容性：IE9+,FireFox,Chrome,Safari,Opera

### background-origin

> 背景图像定位， backgrouind-origin 属性指定 background-position 属性应该是相对位置
  
- 设置元素背景图片(background-position)的原始起始位置(默认是0，0)
- padding-box
- border-box
- content-box
- 兼容性：IE9+, FireFox4+, Chrome, Safari5+, Opera

### background-size

> 背景图像大小

- length | percent | cover | contain
  - 100% auto; 高自适应
  - 100% 100%; 拉伸效果
  - 50% auto; 宽度50% 高自适应
  - 600px auto;
  - cover: 不留白，等比例最大化显示
    - 高度正好，宽度会溢出
  - contain: 宽100%(高留白) 或 高100%(宽留白)
- 兼容性：IE9+, FireFox4+, Chrome, Safari5+, Opera

### background-image: url(), url(), ...

> 多重背景图像，允许为元素使用多个背景图像

- background-image: url(1.png), url(2.jpg)
  - 1.png 上一层图片一次覆盖后面的图
  - 2.jpg 下一层显示

### 背景属性整合

- `background: color position size repeat origin clip attachment image;`
- background: #abcdef center no-repeat content-box content-box fixed url(1.jpg)

## grandients

> 在两个或多个指定的颜色之间显示平稳的过度

- 兼容性：
  - IE10+
  - Chrome 26+, 10.0 -webkit-
  - Firefox 16+, 3.6 -moz-
  - Safari 6.1+, 5.1 -webkit-
  - Opera 12.1+, 11.6 -o-

### linear Gradients 线性渐变属性

> 是沿着一根轴线改变颜色，从起点到终点颜色进行顺序渐变（从一边拉向另一边）

- `background: linear-grandient(direction方向, color-stop1, color-stop2, ..)`

``` CSS
background: -webkit-linear-grandient(red, blue);
background: -moz-linear-gradient(red, blue);
background: -o-linear-gradient(red, blue);
background: linear-gradient(red,blue);

从上到下, 红色到蓝色(默认)
background: linear-grandient(color-stop1, color-stop2, ...)


从左到右
background: -webkit-linear-grandient(begin-direction, red, blue);
background: -moz-linear-gradient(end-direction, red, blue);
background: -o-linear-gradient(end-directon, red, blue);
background: linear-gradient(to end-direction, red,blue);

background: -webkit-linear-grandient(left, red, blue);
background: -moz-linear-gradient(right, red, blue);
background: -o-linear-gradient(right, red, blue);
background: linear-gradient(to right, red,blue);

对角(从左上角对右下角)
background: -webkit-linear-grandient(begin-level begin-vertical, red, blue);
background: -moz-linear-gradient(end-level end-vertical, red, blue);
background: -o-linear-gradient(end-level end-vertical, red, blue);
background: linear-gradient(to end-level end-vertical, red,blue);


background: -webkit-linear-grandient(let top, red, blue);
background: -moz-linear-gradient(right bottom, red, blue);
background: -o-linear-gradient(right bottom, red, blue);
background: linear-gradient(to right bottom, red,blue);


使用角度
background: linear-gradient(angle color-stop1, color-stop2, ...)


角度是指水平线和渐变线之间的角度，逆时针方向计算。
上到右(0deg - 90deg)
0deg 将创建一个从下到上的渐变
90deg 将创建一个从左到右的渐变


background: -webkit-linear-grandient(90deg, red 10%, orange 15%, yellow 20%, green 50%, blue 70%, indigo 80%, violet 100%);
background: -moz-linear-gradient(90deg, red 10%, orange 15%, yellow 20%, green 50%, blue 70%, indigo 80%, violet 100%);
background: -o-linear-gradient(90deg, red 10%, orange 15%, yellow 20%, green 50%, blue 70%, indigo 80%, violet 100%);
background: linear-gradient(90deg, red 10%, orange 15%, yellow 20%, green 50%, blue 70%, indigo 80%, violet 100%);

透明渐变
background: -webkit-linear-grandient(90deg, rgba(255,0,0,0), rgba(255,0,0,1));
background: -moz-linear-gradient(90deg, rgba(255,0,0,0), rgba(255,0,0,1));
background: -o-linear-gradient(90deg, rgba(255,0,0,0), rgba(255,0,0,1));
background: linear-gradient(90deg, rgba(255,0,0,0), rgba(255,0,0,1));


```

线性渐变-重复渐变

``` CSS
background: repeating-linear-gradient: color1 length | percentage, color2 length | percentage, ...);


渐变会重复5边
background: -webkit-repeating-linear-grandient(90deg, red 0%, blue 20%);
background: -moz-repeating-linear-gradient(90deg, red 0%, blue 20%);
background: -o-repeating-linear-gradient(90deg, red 0%, blue 20%);
background: linear-repeating-gradient(90deg, red 0%, blue 20%);
```

### 径向渐变

> 从起点到终点颜色从内到外进行圆形渐变（从中间向外拉）

`background: radial-grandient(center, shape size, start-color1, ..., last-color)`

``` CSS
background: -webkit-radial-gradient(red, blue);
background: -moz-radial-gradient(red, blue);
background: -o-radial-gradient(red, blue);
background: radial-gradient(red, blue);

颜色结点均匀分布（默认）
background: radial-gradient(color-stop1, color-stop2, ...);

颜色节点不均匀分布
background: radial-gradient(color1 length | percentage, color2 length | percentage, ...);

半径的50%，半径的70%
background: -webkit-radial-gradient(red 50%, blue 70%);
background: -moz-radial-gradient(red 50%, blue 70%);
background: -o-radial-gradient(red 50%, blue 70%);
background: radial-gradient(red 50%, blue 70%);

径向渐变-设置形状
background: radial-gradient(shape, color-stop1, color-stop2, ...);
circle - 圆形
ellipse - 椭圆(默认)

background: -webkit-radial-gradient(circle, red, blue);
background: -moz-radial-gradient(circle, red, blue);
background: -o-radial-gradient(circle, red, blue);
background: radial-gradient(circle, red, blue);

尺寸大小关键字
backgroun: radial-gradient(size, color-stop1, color-stop2, ...);
closest-side： 最近边
closest-corner: 最近角
farthest-side: 最远边
farthest-corner: 最远角

30% 70% 是圆心位置
background: -webkit-radial-gradient(30% 70%, closest-side circle, red, blue);
background: -moz-radial-gradient(30% 70%, closest-side circle, red, blue);
background: -o-radial-gradient(30% 70%, closest-side circle, red, blue);
background: radial-gradient(30% 70%, closest-side circle, red, blue);

background: -webkit-radial-gradient(30% 70%, closest-corner circle, red, blue);
background: -moz-radial-gradient(30% 70%, closest-corner circle, red, blue);
background: -o-radial-gradient(30% 70%, closest-corner circle, red, blue);
background: radial-gradient(30% 70%, closest-corner circle, red, blue);

background: -webkit-radial-gradient(30% 70%, farthest-side circle, red, blue);
background: -moz-radial-gradient(30% 70%, farthest-side circle, red, blue);
background: -o-radial-gradient(30% 70%, farthest-side circle, red, blue);
background: radial-gradient(30% 70%, farthest-side circle, red, blue);

background: -webkit-radial-gradient(30% 70%, farthest-corner circle, red, blue);
background: -moz-radial-gradient(30% 70%, farthest-corner circle, red, blue);
background: -o-radial-gradient(30% 70%, farthest-corner circle, red, blue);
background: radial-gradient(30% 70%, farthest-corner circle, red, blue);

重复渐变
background: repeating-radial-gradicent(color1 length | percentage, color2 length | percentage, ...);

background: -webkit-repeating-radial-grandient(red 0%, blue 10%, red 20%);
background: -moz-repeating-radial-gradient(red 0%, blue 10%, red 20%);
background: -o-repeating-radial-gradient(red 0%, blue 10%, red 20%);
background: radial-repeating-gradient(red 0%, blue 10%, red 20%);
```

IE6-8 渐变

``` CSS
filter: progid: DXImageTransform.Miscrosoft.gradient(startColorstr='#startColor', endColorstr='#endColor', GradientType=0);

GradientType = 0 上红下黑
GradientType = 1 左红右黑
GradientType = 2 上蓝下黑

filter: progid: DXImageTransform.Miscrosoft.gradient(startColorstr='#ff0000', endColorstr='#0000ff', GradientType=0);
```

## 圆角

> border-radius属性最多可指定四个border-*-radius 属性的复合属性

- border-radius: 1-4 length | % / 1-4 length | %;
- 兼容性：IE9+, Firefox4+, Chrome, Safari5+, Opera
- 多值：左上角,右上角,右下角,左下角
- border-top-left-raidus: 左上角
- border-top-right-radius: 右上角
- border-bottom-right-radius: 有下角
- border-bottom-left-radius: 左下角

## 盒阴影

> 设置一个或多个下拉阴影的框

- `box-shadow: h-shadow v-shadow blur spread扩展 color inset;`
- blur 不可以有负值
- spread 向四个方向扩张
- insert 内阴影，可以网内扩张，即负值
- 兼容性：IE9+， FireFox4+, Chrome, Safari5+, Opera

## 边界图片 - border-image 属性

> border-image-* 属性来构建可扩展按钮

- `border-image: source slice width outset repeat;`
- 兼容性：IE和Opera不兼容, Chrome, FireFox, Safari6+

- border-image-source: none | image;
- border-image-slice: number|%|fill; 指定图像的边界向内偏移
- border-image-width 属性指定图像边界的宽度

- border-image-width: number | % | auto;
- border-image-outset: length | number; 往元素外边扩张
- border-image-repeat: repeated | stretched(默认，拉伸) | rounded(铺满) | initial | inherit;


![border-image结构](./structure.png)