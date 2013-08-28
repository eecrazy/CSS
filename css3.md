CSS3 完全向后兼容，因此您不必改变现有的设计。浏览器通常支持 CSS2。

CSS3 模块
CSS3 被划分为模块。
其中最重要的 CSS3 模块包括：
选择器
框模型
背景和边框
文本效果
2D/3D 转换
动画
多列布局
用户界面


CSS3 边框
通过 CSS3，您能够创建圆角边框，向矩形添加阴影，使用图片来绘制边框 - 并且不需使用设计软件，比如 PhotoShop。
在本章中，您将学到以下边框属性：
border-radius
box-shadow
border-image

新的边框属性
属性	描述	CSS
border-image	设置所有 border-image-* 属性的简写属性。	3
border-radius	设置所有四个 border-*-radius 属性的简写属性。	3
box-shadow	向方框添加一个或多个阴影。	3


CSS3 圆角边框
在 CSS2 中添加圆角矩形需要技巧。我们必须为每个圆角使用不同的图片。
在 CSS3 中，创建圆角是非常容易的。
在 CSS3 中，border-radius 属性用于创建圆角：
实例:向 div 元素添加圆角：
div{ border:2px solid; border-radius:25px; }

CSS3 边框阴影
在 CSS3 中，box-shadow 用于向方框添加阴影：
实例:向 div 元素添加方框阴影：
div{ box-shadow: 10px 10px 5px #888888; }

CSS3 边框图片
通过 CSS3 的 border-image 属性，您可以使用图片来创建边框：
div{ border-image:url(border.png) 30 30 round; }




CSS3 背景
CSS3 包含多个新的背景属性，它们提供了对背景更强大的控制。
在本章，您将学到以下背景属性：
background-size
background-origin
您也将学到如何使用多重背景图片。

新的背景属性
属性	描述	CSS
background-clip	规定背景的绘制区域。	3
background-origin	规定背景图片的定位区域。	3
background-size	规定背景图片的尺寸。	3

CSS3 background-size 属性
background-size 属性规定背景图片的尺寸。
在 CSS3 之前，背景图片的尺寸是由图片的实际尺寸决定的。在 CSS3 中，可以规定背景图片的尺寸，这就允许我们在不同的环境中重复使用背景图片。
您能够以像素或百分比规定尺寸。如果以百分比规定尺寸，那么尺寸相对于父元素的宽度和高度。

CSS3 background-origin 属性
background-origin 属性规定背景图片的定位区域。
背景图片可以放置于 content-box、padding-box 或 border-box 区域。


CSS3 多重背景图片
CSS3 允许您为元素使用多个背景图像。
实例:为 body 元素设置两幅背景图片：
body{ background-image:url(bg_flower.gif),url(bg_flower_2.gif); }

CSS3 文本效果
CSS3 包含多个新的文本特性。
在本章中，您将学到如下文本属性：
text-shadow
word-wrap

新的文本属性
属性	描述	CSS
hanging-punctuation	规定标点字符是否位于线框之外。	3
punctuation-trim	规定是否对标点字符进行修剪。	3
text-align-last	设置如何对齐最后一行或紧挨着强制换行符之前的行。	3
text-emphasis	向元素的文本应用重点标记以及重点标记的前景色。	3
text-justify	规定当 text-align 设置为 "justify" 时所使用的对齐方法。	3
text-outline	规定文本的轮廓。	3
text-overflow	规定当文本溢出包含元素时发生的事情。	3
text-shadow	向文本添加阴影。	3
text-wrap	规定文本的换行规则。	3
word-break	规定非中日韩文本的换行规则。	3
word-wrap	允许对长的不可分割的单词进行分割并换行到下一行。	3

CSS3 文本阴影
在 CSS3 中，text-shadow 可向文本应用阴影。
文本阴影效果
您能够规定水平阴影、垂直阴影、模糊距离，以及阴影的颜色：
向标题添加阴影：
h1{
text-shadow: 5px 5px 5px #FF0000;//前2个是向左向右的偏移，第三个是模糊程度
}


CSS3 自动换行
单词太长的话就可能无法超出某个区域：
This paragraph contains a very long word: thisisaveryveryveryveryveryverylongword. The long word will break and wrap to the next line.
在 CSS3 中，word-wrap 属性允许您允许文本强制文本进行换行 - 即使这意味着会对单词进行拆分：
This paragraph contains a very long word: thisisaveryveryveryveryveryverylongword. The long word will break and wrap to the next line.
下面是 CSS 代码：
允许对长单词进行拆分，并换行到下一行：
p {word-wrap:break-word;}


CSS3 字体
通过 CSS3，Web 设计师再也不必被迫使用“web-safe”字体了。
CSS3 @font-face 规则
在 CSS3 之前，web 设计师必须使用已在用户计算机上安装好的字体。
通过 CSS3，web 设计师可以使用他们喜欢的任意字体。
当您找到或购买到希望使用的字体时，可将该字体文件存放到 web 服务器上，它会在需要时被自动下载到用户的计算机上。
您“自己的”的字体是在 CSS3 @font-face 规则中定义的。

CSS3 字体描述符
下面的表格列出了能够在 @font-face 规则中定义的所有字体描述符：
描述符	值	描述
font-family	name	必需。规定字体的名称。
src	URL	必需。定义字体文件的 URL。

font-stretch	
normal
condensed
ultra-condensed
extra-condensed
semi-condensed
expanded
semi-expanded
extra-expanded
ultra-expanded
可选。定义如何拉伸字体。默认是 "normal"。

font-style	
ormal
italic
oblique
可选。定义字体的样式。默认是 "normal"。

font-weight	
normal
bold
100
200
300
400
500
600
700
800
900
可选。定义字体的粗细。默认是 "normal"。

unicode-range	unicode-range	可选。定义字体支持的 UNICODE 字符范围。默认是 "U+0-10FFFF"。

使用您需要的字体
在新的 @font-face 规则中，您必须首先定义字体的名称（比如 myFirstFont），然后指向该字体文件。
如需为 HTML 元素使用字体，请通过 font-family 属性来引用字体的名称 (myFirstFont)：
实例
<style> 
@font-face
{
font-family: myFirstFont;
src: url('Sansation_Light.ttf'),
     url('Sansation_Light.eot'); /* IE9+ */
}
div
{
font-family:myFirstFont;
}
</style>

使用粗体字体
您必须为粗体文本添加另一个包含描述符的 @font-face：
实例
@font-face
{
font-family: myFirstFont;
src: url('Sansation_Bold.ttf'),
     url('Sansation_Bold.eot'); /* IE9+ */
font-weight:bold;
}
亲自试一试
文件 "Sansation_Bold.ttf" 是另一个字体文件，它包含了 Sansation 字体的粗体字符。
只要 font-family 为 "myFirstFont" 的文本需要显示为粗体，浏览器就会使用该字体。
通过这种方式，我们可以为相同的字体设置许多 @font-face 规则。



CSS3 2D 转换
CSS3 转换
通过 CSS3 转换，我们能够对元素进行移动、缩放、转动、拉长或拉伸。


它如何工作？
转换是使元素改变形状、尺寸和位置的一种效果。
您可以使用 2D 或 3D 转换来转换您的元素。

2D 转换
在本章中，您将学到如下 2D 转换方法：
translate()
rotate()
scale()
skew()
matrix()

实例
div
{
transform: rotate(30deg);
-ms-transform: rotate(30deg);		/* IE 9 */
-webkit-transform: rotate(30deg);	/* Safari and Chrome */
-o-transform: rotate(30deg);		/* Opera */
-moz-transform: rotate(30deg);		/* Firefox */
}

translate() 方法
通过 translate() 方法，元素从其当前位置移动，根据给定的 left（x 坐标） 和 top（y 坐标） 位置参数：
实例
div
{
transform: translate(50px,100px);
-ms-transform: translate(50px,100px);		/* IE 9 */
-webkit-transform: translate(50px,100px);	/* Safari and Chrome */
-o-transform: translate(50px,100px);		/* Opera */
-moz-transform: translate(50px,100px);		/* Firefox */
}
值 translate(50px,100px) 把元素从左侧移动 50 像素，从顶端移动 100 像素。

rotate() 方法
通过 rotate() 方法，元素顺时针旋转给定的角度。允许负值，元素将逆时针旋转。
实例
div
{
transform: rotate(30deg);
-ms-transform: rotate(30deg);		/* IE 9 */
-webkit-transform: rotate(30deg);	/* Safari and Chrome */
-o-transform: rotate(30deg);		/* Opera */
-moz-transform: rotate(30deg);		/* Firefox */
}
亲自试一试
值 rotate(30deg) 把元素顺时针旋转 30 度。
scale() 方法
通过 scale() 方法，元素的尺寸会增加或减少，根据给定的宽度（X 轴）和高度（Y 轴）参数：
实例
div
{
transform: scale(2,4);
-ms-transform: scale(2,4);	/* IE 9 */
-webkit-transform: scale(2,4);	/* Safari 和 Chrome */
-o-transform: scale(2,4);	/* Opera */
-moz-transform: scale(2,4);	/* Firefox */
}
亲自试一试
值 scale(2,4) 把宽度转换为原始尺寸的 2 倍，把高度转换为原始高度的 4 倍。
skew() 方法
通过 skew() 方法，元素转动给定的角度，根据给定的水平线（X 轴）和垂直线（Y 轴）参数：
实例
div
{
transform: skew(30deg,20deg);
-ms-transform: skew(30deg,20deg);	/* IE 9 */
-webkit-transform: skew(30deg,20deg);	/* Safari and Chrome */
-o-transform: skew(30deg,20deg);	/* Opera */
-moz-transform: skew(30deg,20deg);	/* Firefox */
}

值 skew(30deg,20deg) 围绕 X 轴把元素转动 30 度，围绕 Y 轴转动 20 度。
matrix() 方法
matrix() 方法把所有 2D 转换方法组合在一起。
matrix() 方法需要六个参数，包含数学函数，允许您：旋转、缩放、移动以及倾斜元素。
实例
如何使用 matrix 方法将 div 元素旋转 30 度：
div
{
transform:matrix(0.866,0.5,-0.5,0.866,0,0);
-ms-transform:matrix(0.866,0.5,-0.5,0.866,0,0);		/* IE 9 */
-moz-transform:matrix(0.866,0.5,-0.5,0.866,0,0);	/* Firefox */
-webkit-transform:matrix(0.866,0.5,-0.5,0.866,0,0);	/* Safari and Chrome */
-o-transform:matrix(0.866,0.5,-0.5,0.866,0,0);		/* Opera */
}

新的转换属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
transform	向元素应用 2D 或 3D 转换。	3
transform-origin	允许你改变被转换元素的位置。	3
2D Transform 方法
函数	描述
matrix(n,n,n,n,n,n)	定义 2D 转换，使用六个值的矩阵。
translate(x,y)	定义 2D 转换，沿着 X 和 Y 轴移动元素。
translateX(n)	定义 2D 转换，沿着 X 轴移动元素。
translateY(n)	定义 2D 转换，沿着 Y 轴移动元素。
scale(x,y)	定义 2D 缩放转换，改变元素的宽度和高度。
scaleX(n)	定义 2D 缩放转换，改变元素的宽度。
scaleY(n)	定义 2D 缩放转换，改变元素的高度。
rotate(angle)	定义 2D 旋转，在参数中规定角度。
skew(x-angle,y-angle)	定义 2D 倾斜转换，沿着 X 和 Y 轴。
skewX(angle)	定义 2D 倾斜转换，沿着 X 轴。
skewY(angle)	定义 2D 倾斜转换，沿着 Y 轴。

3D 转换
CSS3 允许您使用 3D 转换来对元素进行格式化。
在本章中，您将学到其中的一些 3D 转换方法：
rotateX()
rotateY()

rotateX() 方法
通过 rotateX() 方法，元素围绕其 X 轴以给定的度数进行旋转。
实例
div
{
transform: rotateX(120deg);
-webkit-transform: rotateX(120deg);	/* Safari 和 Chrome */
-moz-transform: rotateX(120deg);	/* Firefox */
}
亲自试一试
rotateY() 旋转
通过 rotateY() 方法，元素围绕其 Y 轴以给定的度数进行旋转。
实例
div
{
transform: rotateY(130deg);
-webkit-transform: rotateY(130deg);	/* Safari 和 Chrome */
-moz-transform: rotateY(130deg);	/* Firefox */
}

转换属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
transform	向元素应用 2D 或 3D 转换。	3
transform-origin	允许你改变被转换元素的位置。	3
transform-style	规定被嵌套元素如何在 3D 空间中显示。	3
perspective	规定 3D 元素的透视效果。	3
perspective-origin	规定 3D 元素的底部位置。	3
backface-visibility	定义元素在不面对屏幕时是否可见。	3
2D Transform 方法
函数	描述
matrix3d(n,n,n,n,n,n,
n,n,n,n,n,n,n,n,n,n)	定义 3D 转换，使用 16 个值的 4x4 矩阵。
translate3d(x,y,z)	定义 3D 转化。
translateX(x)	定义 3D 转化，仅使用用于 X 轴的值。
translateY(y)	定义 3D 转化，仅使用用于 Y 轴的值。
translateZ(z)	定义 3D 转化，仅使用用于 Z 轴的值。
scale3d(x,y,z)	定义 3D 缩放转换。
scaleX(x)	定义 3D 缩放转换，通过给定一个 X 轴的值。
scaleY(y)	定义 3D 缩放转换，通过给定一个 Y 轴的值。
scaleZ(z)	定义 3D 缩放转换，通过给定一个 Z 轴的值。
rotate3d(x,y,z,angle)	定义 3D 旋转。
rotateX(angle)	定义沿 X 轴的 3D 旋转。
rotateY(angle)	定义沿 Y 轴的 3D 旋转。
rotateZ(angle)	定义沿 Z 轴的 3D 旋转。
perspective(n)	定义 3D 转换元素的透视视图。

CSS3 过渡
通过 CSS3，我们可以在不使用 Flash 动画或 JavaScript 的情况下，当元素从一种样式变换为另一种样式时为元素添加效果。

CSS3 过渡是元素从一种样式逐渐改变为另一种的效果。
要实现这一点，必须规定两项内容：
规定您希望把效果添加到哪个 CSS 属性上
规定效果的时长

过渡属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
transition	简写属性，用于在一个属性中设置四个过渡属性。	3
transition-property	规定应用过渡的 CSS 属性的名称。	3
transition-duration	定义过渡效果花费的时间。默认是 0。	3
transition-timing-function	规定过渡效果的时间曲线。默认是 "ease"。	3
transition-delay	规定过渡效果何时开始。默认是 0。	3


CSS3 动画
通过 CSS3，我们能够创建动画，这可以在许多网页中取代动画图片、Flash 动画以及 JavaScript。
CSS3 @keyframes 规则
如需在 CSS3 中创建动画，您需要学习 @keyframes 规则。
@keyframes 规则用于创建动画。在 @keyframes 中规定某项 CSS 样式，就能创建由当前样式逐渐改为新样式的动画效果。

CSS3 动画属性
下面的表格列出了 @keyframes 规则和所有动画属性：
属性	描述	CSS
@keyframes	规定动画。	3
animation	所有动画属性的简写属性，除了 animation-play-state 属性。	3
animation-name	规定 @keyframes 动画的名称。	3
animation-duration	规定动画完成一个周期所花费的秒或毫秒。默认是 0。	3
animation-timing-function	规定动画的速度曲线。默认是 "ease"。	3
animation-delay	规定动画何时开始。默认是 0。	3
animation-iteration-count	规定动画被播放的次数。默认是 1。	3
animation-direction	规定动画是否在下一周期逆向地播放。默认是 "normal"。	3
animation-play-state	规定动画是否正在运行或暂停。默认是 "running"。	3


什么是 CSS3 中的动画？
动画是使元素从一种样式逐渐变化为另一种样式的效果。
您可以改变任意多的样式任意多的次数。
请用百分比来规定变化发生的时间，或用关键词 "from" 和 "to"，等同于 0% 和 100%。
0% 是动画的开始，100% 是动画的完成。
为了得到最佳的浏览器支持，您应该始终定义 0% 和 100% 选择器。

当动画为 25% 及 50% 时改变背景色，然后当动画 100% 完成时再次改变：
@keyframes myfirst
{
0%   {background: red;}
25%  {background: yellow;}
50%  {background: blue;}
100% {background: green;}
}

改变背景色和位置：
@keyframes myfirst
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}

@-moz-keyframes myfirst /* Firefox */
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}

@-webkit-keyframes myfirst /* Safari 和 Chrome */
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}

@-o-keyframes myfirst /* Opera */
{
0%   {background: red; left:0px; top:0px;}
25%  {background: yellow; left:200px; top:0px;}
50%  {background: blue; left:200px; top:200px;}
75%  {background: green; left:0px; top:200px;}
100% {background: red; left:0px; top:0px;}
}


CSS3 多列
通过 CSS3，您能够创建多个列来对文本进行布局 - 就像报纸那样！
在本章中，您将学习如下多列属性：
column-count
column-gap
column-rule

CSS3 创建多列
column-count 属性规定元素应该被分隔的列数：
实例
把 div 元素中的文本分隔为三列：
div
{
-moz-column-count:3; 	/* Firefox */
-webkit-column-count:3; /* Safari 和 Chrome */
column-count:3;
}

CSS3 规定列之间的间隔
column-gap 属性规定列之间的间隔：
实例
规定列之间 40 像素的间隔：
div
{
-moz-column-gap:40px;		/* Firefox */
-webkit-column-gap:40px;	/* Safari 和 Chrome */
column-gap:40px;
}

CSS3 列规则
column-rule 属性设置列之间的宽度、样式和颜色规则。
实例
规定列之间的宽度、样式和颜色规则：
div
{
-moz-column-rule:3px outset #ff0000;	/* Firefox */
-webkit-column-rule:3px outset #ff0000;	/* Safari and Chrome */
column-rule:3px outset #ff0000;
}


CSS3 用户界面
在 CSS3 中，新的用户界面特性包括重设元素尺寸、盒尺寸以及轮廓等。
在本章中，您将学到以下用户界面属性：
resize
box-sizing
outline-offset


CSS3 Resizing
在 CSS3，resize 属性规定是否可由用户调整元素尺寸。
这个 div 元素可由用户调整尺寸（在 Firefox 4+、Chrome 以及 Safari 中）。
CSS 代码如下：
规定 div 元素可由用户调整大小：
div{
resize:both;
overflow:auto;
}

CSS3 Box Sizing
box-sizing 属性允许您以确切的方式定义适应某个区域的具体内容。
实例
规定两个并排的带边框方框：
div
{
box-sizing:border-box;
-moz-box-sizing:border-box;	/* Firefox */
-webkit-box-sizing:border-box;	/* Safari */
width:50%;
float:left;
}

CSS3 Outline Offset
outline-offset 属性对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓。
轮廓与边框有两点不同：
轮廓不占用空间
轮廓可能是非矩形
这个 div 在边框之外 15 像素处有一个轮廓。
CSS 代码如下：
规定边框边缘之外 15 像素处的轮廓：
div{
border:2px solid black;
outline:2px solid red;
outline-offset:15px;
}

新的用户界面属性
下面的表格列出了所有的转换属性：
属性	描述	CSS
appearance	允许您将元素设置为标准用户界面元素的外观	3
box-sizing	允许您以确切的方式定义适应某个区域的具体内容。	3
icon	为创作者提供使用图标化等价物来设置元素样式的能力。	3
nav-down	规定在使用 arrow-down 导航键时向何处导航。	3
nav-index	设置元素的 tab 键控制次序。	3
nav-left	规定在使用 arrow-left 导航键时向何处导航。	3
nav-right	规定在使用 arrow-right 导航键时向何处导航。	3
nav-up	规定在使用 arrow-up 导航键时向何处导航。	3
outline-offset	对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓。	3
resize	规定是否可由用户对元素的尺寸进行调整。	3



CSS 属性
CSS 属性组：
动画
背景
边框和轮廓
盒（框）
颜色
内容分页媒体
定位
可伸缩框
字体
生成内容
网格
超链接
行框
列表
外边距
Marquee
多列
内边距
分页媒体
定位
打印
Ruby
语音
表格
文本
2D/3D 转换
过渡
用户界面
"CSS" 列指示该属性是在哪个 CSS 版本（CSS1、CSS3 或 CSS3）中定义的。
CSS3 动画属性（Animation）
属性	描述	CSS
@keyframes	规定动画。	3
animation	所有动画属性的简写属性，除了 animation-play-state 属性。	3
animation-name	规定 @keyframes 动画的名称。	3
animation-duration	规定动画完成一个周期所花费的秒或毫秒。	3
animation-timing-function	规定动画的速度曲线。	3
animation-delay	规定动画何时开始。	3
animation-iteration-count	规定动画被播放的次数。	3
animation-direction	规定动画是否在下一周期逆向地播放。	3
animation-play-state	规定动画是否正在运行或暂停。	3
CSS 背景属性（Background）
属性	描述	CSS
background	在一个声明中设置所有的背景属性。	1
background-attachment	设置背景图像是否固定或者随着页面的其余部分滚动。	1
background-color	设置元素的背景颜色。	1
background-image	设置元素的背景图像。	1
background-position	设置背景图像的开始位置。	1
background-repeat	设置是否及如何重复背景图像。	1
background-clip	规定背景的绘制区域。	3
background-origin	规定背景图片的定位区域。	3
background-size	规定背景图片的尺寸。	3
CSS 边框属性（Border 和 Outline）
属性	描述	CSS
border	在一个声明中设置所有的边框属性。	1
border-bottom	在一个声明中设置所有的下边框属性。	1
border-bottom-color	设置下边框的颜色。	2
border-bottom-style	设置下边框的样式。	2
border-bottom-width	设置下边框的宽度。	1
border-color	设置四条边框的颜色。	1
border-left	在一个声明中设置所有的左边框属性。	1
border-left-color	设置左边框的颜色。	2
border-left-style	设置左边框的样式。	2
border-left-width	设置左边框的宽度。	1
border-right	在一个声明中设置所有的右边框属性。	1
border-right-color	设置右边框的颜色。	2
border-right-style	设置右边框的样式。	2
border-right-width	设置右边框的宽度。	1
border-style	设置四条边框的样式。	1
border-top	在一个声明中设置所有的上边框属性。	1
border-top-color	设置上边框的颜色。	2
border-top-style	设置上边框的样式。	2
border-top-width	设置上边框的宽度。	1
border-width	设置四条边框的宽度。	1
outline	在一个声明中设置所有的轮廓属性。	2
outline-color	设置轮廓的颜色。	2
outline-style	设置轮廓的样式。	2
outline-width	设置轮廓的宽度。	2
border-bottom-left-radius	定义边框左下角的形状。	3
border-bottom-right-radius	定义边框右下角的形状。	3
border-image	简写属性，设置所有 border-image-* 属性。	3
border-image-outset	规定边框图像区域超出边框的量。	3
border-image-repeat	图像边框是否应平铺(repeated)、铺满(rounded)或拉伸(stretched)。	3
border-image-slice	规定图像边框的向内偏移。	3
border-image-source	规定用作边框的图片。	3
border-image-width	规定图片边框的宽度。	3
border-radius	简写属性，设置所有四个 border-*-radius 属性。	3
border-top-left-radius	定义边框左上角的形状。	3
border-top-right-radius	定义边框右下角的形状。	3
box-decoration-break		3
box-shadow	向方框添加一个或多个阴影。	3
Box 属性
属性	描述	CSS
overflow-x	如果内容溢出了元素内容区域，是否对内容的左/右边缘进行裁剪。	3
overflow-y	如果内容溢出了元素内容区域，是否对内容的上/下边缘进行裁剪。	3
overflow-style	规定溢出元素的首选滚动方法。	3
rotation	围绕由 rotation-point 属性定义的点对元素进行旋转。	3
rotation-point	定义距离上左边框边缘的偏移点。	3
Color 属性
属性	描述	CSS
color-profile	规定书签的标记。	3
opacity	规定书签的级别。	3
rendering-intent	规定书签链接的目标。	3
Content for Paged Media 属性
属性	描述	CSS
bookmark-label	规定书签的标记。	3
bookmark-level	规定书签的级别。	3
bookmark-target	规定书签链接的目标。	3
float-offset	将元素放在 float 属性通常放置的位置的相反方向。	3
hyphenate-after	规定连字单词中连字符之后的最小字符数。	3
hyphenate-before	规定连字单词中连字符之前的最小字符数。	3
hyphenate-character	规定当发生断字时显示的字符串。	3
hyphenate-lines	指示元素中连续断字连线的最大数。	3
hyphenate-resource	规定帮助浏览器确定断字点的外部资源（逗号分隔的列表）。	3
hyphens	设置如何对单词进行拆分，以改善段落的布局。	3
image-resolution	规定图像的正确分辨率。	3
marks	向文档添加裁切标记或十字标记。	3
string-set		3
CSS 尺寸属性（Dimension）
属性	描述	CSS
height	设置元素高度。	1
max-height	设置元素的最大高度。	2
max-width	设置元素的最大宽度。	2
min-height	设置元素的最小高度。	2
min-width	设置元素的最小宽度。	2
width	设置元素的宽度。	1
可伸缩框属性（Flexible Box）
属性	描述	CSS
box-align	规定如何对齐框的子元素。	3
box-direction	规定框的子元素的显示方向。	3
box-flex	规定框的子元素是否可伸缩。	3
box-flex-group	将可伸缩元素分配到柔性分组。	3
box-lines	规定当超出父元素框的空间时，是否换行显示。	3
box-ordinal-group	规定框的子元素的显示次序。	3
box-orient	规定框的子元素是否应水平或垂直排列。	3
box-pack	规定水平框中的水平位置或者垂直框中的垂直位置。	3
CSS 字体属性（Font）
属性	描述	CSS
font	在一个声明中设置所有字体属性。	1
font-family	规定文本的字体系列。	1
font-size	规定文本的字体尺寸。	1
font-size-adjust	为元素规定 aspect 值。	2
font-stretch	收缩或拉伸当前的字体系列。	2
font-style	规定文本的字体样式。	1
font-variant	规定是否以小型大写字母的字体显示文本。	1
font-weight	规定字体的粗细。	1
内容生成（Generated Content）
属性	描述	CSS
content	与 :before 以及 :after 伪元素配合使用，来插入生成内容。	2
counter-increment	递增或递减一个或多个计数器。	2
counter-reset	创建或重置一个或多个计数器。	2
quotes	设置嵌套引用的引号类型。	2
crop	允许被替换元素仅仅是对象的矩形区域，而不是整个对象。	3
move-to	从流中删除元素，然后在文档中后面的点上重新插入。	3
page-policy	确定元素基于页面的 occurrence 应用于计数器还是字符串值。	3
Grid 属性
属性	描述	CSS
grid-columns	规定网格中每个列的宽度。	3
grid-rows	规定网格中每个列的高度。	3
Hyperlink 属性
属性	描述	CSS
target	简写属性，设置target-name、target-new以及target-position属性。	3
target-name	规定在何处打开链接（链接的目标）。	3
target-new	规定目标链接在新窗口还是在已有窗口的新标签页中打开。	3
target-position	规定在何处放置新的目标链接。	3
CSS 列表属性（List）
属性	描述	CSS
list-style	在一个声明中设置所有的列表属性。	1
list-style-image	将图象设置为列表项标记。	1
list-style-position	设置列表项标记的放置位置。	1
list-style-type	设置列表项标记的类型。	1
marker-offset	 	2
CSS 外边距属性（Margin）
属性	描述	CSS
margin	在一个声明中设置所有外边距属性。	1
margin-bottom	设置元素的下外边距。	1
margin-left	设置元素的左外边距。	1
margin-right	设置元素的右外边距。	1
margin-top	设置元素的上外边距。	1
Marquee 属性
属性	描述	CSS
marquee-direction	设置移动内容的方向。	3
marquee-play-count	设置内容移动多少次。	3
marquee-speed	设置内容滚动得多快。	3
marquee-style	设置移动内容的样式。	3
多列属性（Multi-column）
属性	描述	CSS
column-count	规定元素应该被分隔的列数。	3
column-fill	规定如何填充列。	3
column-gap	规定列之间的间隔。	3
column-rule	设置所有 column-rule-* 属性的简写属性。	3
column-rule-color	规定列之间规则的颜色。	3
column-rule-style	规定列之间规则的样式。	3
column-rule-width	规定列之间规则的宽度。	3
column-span	规定元素应该横跨的列数。	3
column-width	规定列的宽度。	3
columns	规定设置 column-width 和 column-count 的简写属性。	3
CSS 内边距属性（Padding）
属性	描述	CSS
padding	在一个声明中设置所有内边距属性。	1
padding-bottom	设置元素的下内边距。	1
padding-left	设置元素的左内边距。	1
padding-right	设置元素的右内边距。	1
padding-top	设置元素的上内边距。	1
Paged Media 属性
属性	描述	CSS
fit	示意如何对width和height属性均不是auto的被替换元素进行缩放。	3
fit-position	定义盒内对象的对齐方式。	3
image-orientation	规定用户代理应用于图像的顺时针方向旋转。	3
page	规定元素应该被显示的页面特定类型。	3
size	规定页面内容包含框的尺寸和方向。	3
CSS 定位属性（Positioning）
属性	描述	CSS
bottom	设置定位元素下外边距边界与其包含块下边界之间的偏移。	2
clear	规定元素的哪一侧不允许其他浮动元素。	1
clip	剪裁绝对定位元素。	2
cursor	规定要显示的光标的类型（形状）。	2
display	规定元素应该生成的框的类型。	1
float	规定框是否应该浮动。	1
left	设置定位元素左外边距边界与其包含块左边界之间的偏移。	2
overflow	规定当内容溢出元素框时发生的事情。	2
position	规定元素的定位类型。	2
right	设置定位元素右外边距边界与其包含块右边界之间的偏移。	2
top	设置定位元素的上外边距边界与其包含块上边界之间的偏移。	2
vertical-align	设置元素的垂直对齐方式。	1
visibility	规定元素是否可见。	2
z-index	设置元素的堆叠顺序。	2
CSS 打印属性（Print）
属性	描述	CSS
orphans	设置当元素内部发生分页时必须在页面底部保留的最少行数。	2
page-break-after	设置元素后的分页行为。	2
page-break-before	设置元素前的分页行为。	2
page-break-inside	设置元素内部的分页行为。	2
widows	设置当元素内部发生分页时必须在页面顶部保留的最少行数。	2
CSS 表格属性（Table）
属性	描述	CSS
border-collapse	规定是否合并表格边框。	2
border-spacing	规定相邻单元格边框之间的距离。	2
caption-side	规定表格标题的位置。	2
empty-cells	规定是否显示表格中的空单元格上的边框和背景。	2
table-layout	设置用于表格的布局算法。	2
CSS 文本属性（Text）
属性	描述	CSS
color	设置文本的颜色。	1
direction	规定文本的方向 / 书写方向。	2
letter-spacing	设置字符间距。	1
line-height	设置行高。	1
text-align	规定文本的水平对齐方式。	1
text-decoration	规定添加到文本的装饰效果。	1
text-indent	规定文本块首行的缩进。	1
text-shadow	规定添加到文本的阴影效果。	2
text-transform	控制文本的大小写。	1
unicode-bidi	设置文本方向。	2
white-space	规定如何处理元素中的空白。	1
word-spacing	设置单词间距。	1
hanging-punctuation	规定标点字符是否位于线框之外。	3
punctuation-trim	规定是否对标点字符进行修剪。	3
text-align-last	设置如何对齐最后一行或紧挨着强制换行符之前的行。	3
text-emphasis	向元素的文本应用重点标记以及重点标记的前景色。	3
text-justify	规定当 text-align 设置为 "justify" 时所使用的对齐方法。	3
text-outline	规定文本的轮廓。	3
text-overflow	规定当文本溢出包含元素时发生的事情。	3
text-shadow	向文本添加阴影。	3
text-wrap	规定文本的换行规则。	3
word-break	规定非中日韩文本的换行规则。	3
word-wrap	允许对长的不可分割的单词进行分割并换行到下一行。	3
2D/3D 转换属性（Transform）
属性	描述	CSS
transform	向元素应用 2D 或 3D 转换。	3
transform-origin	允许你改变被转换元素的位置。	3
transform-style	规定被嵌套元素如何在 3D 空间中显示。	3
perspective	规定 3D 元素的透视效果。	3
perspective-origin	规定 3D 元素的底部位置。	3
backface-visibility	定义元素在不面对屏幕时是否可见。	3
过渡属性（Transition）
属性	描述	CSS
transition	简写属性，用于在一个属性中设置四个过渡属性。	3
transition-property	规定应用过渡的 CSS 属性的名称。	3
transition-duration	定义过渡效果花费的时间。	3
transition-timing-function	规定过渡效果的时间曲线。	3
transition-delay	规定过渡效果何时开始。	3
用户界面属性（User-interface）
属性	描述	CSS
appearance	允许您将元素设置为标准用户界面元素的外观	3
box-sizing	允许您以确切的方式定义适应某个区域的具体内容。	3
icon	为创作者提供使用图标化等价物来设置元素样式的能力。	3
nav-down	规定在使用 arrow-down 导航键时向何处导航。	3
nav-index	设置元素的 tab 键控制次序。	3
nav-left	规定在使用 arrow-left 导航键时向何处导航。	3
nav-right	规定在使用 arrow-right 导航键时向何处导航。	3
nav-up	规定在使用 arrow-up 导航键时向何处导航。	3
outline-offset	对轮廓进行偏移，并在超出边框边缘的位置绘制轮廓。	3
resize	规定是否可由用户对元素的尺寸进行调整。	3




CSS3 选择器
在 CSS 中，选择器是一种模式，用于选择需要添加样式的元素。
"CSS" 列指示该属性是在哪个 CSS 版本中定义的。（CSS1、CSS2 还是 CSS3。）
选择器	例子	例子描述	CSS
.class	.intro	选择 class="intro" 的所有元素。	1
#id	#firstname	选择 id="firstname" 的所有元素。	1
*	*	选择所有元素。	2
element	p	选择所有 <p> 元素。	1
element,element	div,p	选择所有 <div> 元素和所有 <p> 元素。	1
element element	div p	选择 <div> 元素内部的所有 <p> 元素。	1
element>element	div>p	选择父元素为 <div> 元素的所有 <p> 元素。	2
element+element	div+p	选择紧接在 <div> 元素之后的所有 <p> 元素。	2
[attribute]	[target]	选择带有 target 属性所有元素。	2
[attribute=value]	[target=_blank]	选择 target="_blank" 的所有元素。	2
[attribute~=value]	[title~=flower]	选择 title 属性包含单词 "flower" 的所有元素。	2
[attribute|=value]	[lang|=en]	选择 lang 属性值以 "en" 开头的所有元素。	2
:link	a:link	选择所有未被访问的链接。	1
:visited	a:visited	选择所有已被访问的链接。	1
:active	a:active	选择活动链接。	1
:hover	a:hover	选择鼠标指针位于其上的链接。	1
:focus	input:focus	选择获得焦点的 input 元素。	2
:first-letter	p:first-letter	选择每个 <p> 元素的首字母。	1
:first-line	p:first-line	选择每个 <p> 元素的首行。	1
:first-child	p:first-child	选择属于父元素的第一个子元素的每个 <p> 元素。	2
:before	p:before	在每个 <p> 元素的内容之前插入内容。	2
:after	p:after	在每个 <p> 元素的内容之后插入内容。	2
:lang(language)	p:lang(it)	选择带有以 "it" 开头的 lang 属性值的每个 <p> 元素。	2
element1~element2	p~ul	选择前面有 <p> 元素的每个 <ul> 元素。	3
[attribute^=value]	a[src^="https"]	选择其 src 属性值以 "https" 开头的每个 <a> 元素。	3
[attribute$=value]	a[src$=".pdf"]	选择其 src 属性以 ".pdf" 结尾的所有 <a> 元素。	3
[attribute*=value]	a[src*="abc"]	选择其 src 属性中包含 "abc" 子串的每个 <a> 元素。	3
:first-of-type	p:first-of-type	选择属于其父元素的首个 <p> 元素的每个 <p> 元素。	3
:last-of-type	p:last-of-type	选择属于其父元素的最后 <p> 元素的每个 <p> 元素。	3
:only-of-type	p:only-of-type	选择属于其父元素唯一的 <p> 元素的每个 <p> 元素。	3
:only-child	p:only-child	选择属于其父元素的唯一子元素的每个 <p> 元素。	3
:nth-child(n)	p:nth-child(2)	选择属于其父元素的第二个子元素的每个 <p> 元素。	3
:nth-last-child(n)	p:nth-last-child(2)	同上，从最后一个子元素开始计数。	3
:nth-of-type(n)	p:nth-of-type(2)	选择属于其父元素第二个 <p> 元素的每个 <p> 元素。	3
:nth-last-of-type(n)	p:nth-last-of-type(2)	同上，但是从最后一个子元素开始计数。	3
:last-child	p:last-child	选择属于其父元素最后一个子元素每个 <p> 元素。	3
:root	:root	选择文档的根元素。	3
:empty	p:empty	选择没有子元素的每个 <p> 元素（包括文本节点）。	3
:target	#news:target	选择当前活动的 #news 元素。	3
:enabled	input:enabled	选择每个启用的 <input> 元素。	3
:disabled	input:disabled	选择每个禁用的 <input> 元素	3
:checked	input:checked	选择每个被选中的 <input> 元素。	3
:not(selector)	:not(p)	选择非 <p> 元素的每个元素。	3
::selection	::selection	选择被用户选取的元素部分。	3


CSS 单位
CSS 网络安全字体
CSS 颜色
尺寸
单位	描述
%	百分比
in	英寸
cm	厘米
mm	毫米
em	
1em 等于当前的字体尺寸。
2em 等于当前字体尺寸的两倍。
例如，如果某元素以 12pt 显示，那么 2em 是24pt。
在 CSS 中，em 是非常有用的单位，因为它可以自动适应用户所使用的字体。
ex	一个 ex 是一个字体的 x-height。 (x-height 通常是字体尺寸的一半。)
pt	磅 (1 pt 等于 1/72 英寸)
pc	12 点活字 (1 pc 等于 12 点)
px	像素 (计算机屏幕上的一个点)
颜色
单位	描述
(颜色名)	颜色名称 (比如 red)
rgb(x,x,x)	RGB 值 (比如 rgb(255,0,0))
rgb(x%, x%, x%)	RGB 百分比值 (比如 rgb(100%,0%,0%))
#rrggbb	十六进制数 (比如 #ff0000)