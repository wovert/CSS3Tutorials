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
- E::after
- E:not(s) 表示 E 元素不被匹配
- E~F 表示E元素挨着的F元素
- Content 属性

- rgba()
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

## 弹性盒模型

- 弹性盒模型父元素必须要加 display:box 或 display:inline-box
- box-orient 定义盒模型的布局方向
  - horizontal 水平显示
  - vertical 垂直方向
- box-direction 元素排列顺序
  - normal 正序
  - reverse 反序
- box-ordinal-group 设置元素的具体位置


