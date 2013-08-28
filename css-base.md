DOC  online:

<http://www.divcss5.com/shouce/>

<http://zh.html.net/tutorials/css/>

常见CSS属性单词及解释
1. 常用CSS单词有哪些
2. 常用CSS单词对应作用和解释
3. CSS单词对应实例
4. 是否需要记住这些单词

常见CSS英文单词、对应功能、对应解释、对应简单例子
1. float 浮动
Float:left;靠左浮动
Float:right:靠右浮动
2. width 宽度
Width:20px; 对象宽度20px
3. height 高度
Height:20px; 对象高度20px
4. margin 外补距
Margin:1px 2px 3px 4px 对象上距离1px；右为2px；下为3px；左为4px
5. padding 内补距
Padding:1px 2px 3px 4px 对象内距离边上为1px；右为2px；下为3px；左为4px
6. border 边框
Border:1px solid #111; 对象边框为1px宽黑实线
7. font-family 字体
font-family:"黑体"; 对象文字字体为黑体
8. font-size 文字大小
font-size:12px 对象文字大小为12px
9. font-weight 文字加粗
font-weight:bold 对象文字被加粗
10. line-height 行高
line-height:20px 对象内上下2排文字行高为20px（包括文字自身占用高度）
11. text-decoration 文字装饰（下划线、删除线）
text-decoration:underline 对象文字加下划线
12. background 背景属性
background:#FFF url(bg.png) repeat-x 0 0 对象背景色为白色、背景图片为bg.png 按X轴分析重复显示并距离顶部和左为0像素
13. text-align 内容左中右对齐属性
text-align:center 对象内内容左右居中显示
14. position 定位属性
15. overflow溢出处理
Overflow:hidden 对象内容被隐藏并且不占用虚拟位置

以上为常用的CSS单词及其属性。更多请进入：<http://www.divcss5.com/rumen/r11.shtml>
或CSS手册查看：<http://www.divcss5.com/shouce>

这么多的单词我需要全部会拼写记住吗？
答案是如果不会拼写也无所谓，借助DW软件很快能写出输入各个属性及对应的值。因为平时会大量接触和使用，日久自然就会拼写，所以没必要硬记住，当然记住也可以。
技巧：一看见CSS 属性单词就知道他用法或想实现什么效果就想到用什么CSS单词，前字母是什么即可，用DW既可以很快输入这些单词同时也无需记住这些单词。


层叠次序
当同一个 HTML 元素被不止一个样式定义时，会使用哪个样式呢？
一般而言，所有的样式会根据下面的规则层叠于一个新的虚拟样式表中，其中数字 4 拥有最高的优先权。
浏览器缺省设置
外部样式表
内部样式表（位于 <head> 标签内部）
内联样式（在 HTML 元素内部）
因此，内联样式（在 HTML 元素内部）拥有最高的优先权，这意味着它将优先于以下的样式声明：<head> 标签中的样式声明，外部样式表中的样式声明，或者浏览器中的样式声明（缺省值）。


class 和 id 名称对大小写是敏感的。

你可以对选择器进行分组，这样，被分组的选择器就可以分享相同的声明。用逗号将需要分组的选择器分开。在下面的例子中，我们对所有的标题元素进行了分组。所有的标题元素都是绿色的。
h1,h2,h3,h4,h5,h6 { color: green; }

有关继承及其特殊规则!

比方说，你希望列表中的 strong 元素变为斜体字，而不是通常的粗体字，可以这样定义一个派生选择器：
li strong { font-style: italic; font-weight: normal; }
在上面的例子中，只有 li 元素中的 strong 元素的样式为斜体字，无需为 strong 元素定义特别的 class 或 id，代码更加简洁。


id 选择器和派生选择器
在现代布局中，id 选择器常常用于建立派生选择器。
#sidebar p { font-style: italic; text-align: right; margin-top: 0.5em; }

在 CSS 中，类选择器以一个点号显示：
.center { text-align: center; }

和 id 一样，class 也可被用作派生选择器：
.fancy td { color: #f60; background: #666; }

元素也可以基于它们的类而被选择：
td.fancy { color: #f60; background: #666; }
在上面的例子中，类名为 fancy 的表格单元将是带有灰色背景的橙色。
<td class="fancy"> </td>

设置表单的样式
属性选择器在为不带有 class 或 id 的表单设置样式时特别有用：
input[type="text"]
{ width:150px; display:block; margin-bottom:10px; background-color:yellow; font-family: Verdana, Arial; }

input[type="button"]
{ width:120px; margin-left:35px; display:block; font-family: Verdana, Arial; }

属性和值选择器
下面的例子为 title="W3School" 的所有元素设置样式：
[title=W3School]
{ border:5px solid blue; }

CSS 选择器参考手册
选择器	描述
[attribute]	用于选取带有指定属性的元素。
[attribute=value]	用于选取带有指定属性和值的元素。
[attribute~=value]	用于选取属性值中包含指定词汇的元素。
[attribute|=value]	用于选取带有以指定值开头的属性值的元素，该值必须是整个单词。
[attribute^=value]	匹配属性值以指定值开头的每个元素。
[attribute$=value]	匹配属性值以指定值结尾的每个元素。
[attribute*=value]	匹配属性值中包含指定值的每个元素。

CSS 允许应用纯色作为背景，也允许使用背景图像创建相当复杂的效果。
CSS 在这方面的能力远远在 HTML 之上。
p { background-color: gray; }
background-color 不能继承，其默认值是 transparent。transparent 有“透明”之意。也就是说，如果一个元素没有指定背景色，那么背景就是透明的，这样其祖先元素的背景才能可见。

CSS 背景属性
属性	描述
background	简写属性，作用是将背景属性设置在一个声明中。
background-attachment	背景图像是否固定或者随着页面的其余部分滚动。
background-color	设置元素的背景颜色。
background-image	把图像设置为背景。
background-position	设置背景图像的起始位置。
background-repeat	设置背景图像是否及如何重复。

CSS 文本属性
属性	描述
color	设置文本颜色
direction	设置文本方向。
line-height	设置行高。
letter-spacing	设置字符间距。
text-align	对齐元素中的文本。
text-decoration	向文本添加修饰。
text-indent	缩进元素中文本的首行。
text-shadow	设置文本阴影。CSS2 包含该属性，但是 CSS2.1 没有保留该属性。
text-transform	控制元素中的字母。
unicode-bidi	设置文本方向。
white-space	设置元素中空白的处理方式。
word-spacing	设置字间距。

CSS 字体属性
属性	描述
font	简写属性。作用是把所有针对字体的属性设置在一个声明中。
font-family	设置字体系列。
font-size	设置字体的尺寸。
font-size-adjust	当首选字体不可用时，对替换字体进行智能缩放。（CSS2.1 已删除该属性。）
font-stretch	对字体进行水平拉伸。（CSS2.1 已删除该属性。）
font-style	设置字体风格。
font-variant	以小型大写字体或者正常字体显示文本。
font-weight	设置字体的粗细。

实例
a:link { color:#FF0000; }		/* 未被访问的链接 */
a:visited { color:#00FF00; }	/* 已被访问的链接 */
a:hover { color:#FF00FF; }	/* 鼠标指针移动到链接上 */
a:active { color:#0000FF; }	/* 正在被点击的链接 */

CSS Table 属性
属性	描述
border-collapse	设置是否把表格边框合并为单一的边框。
border-spacing	设置分隔单元格边框的距离。
caption-side	设置表格标题的位置。
empty-cells	设置是否显示表格中的空单元格。
table-layout	设置显示单元、行和列的算法。


属性	描述	CSS
outline	在一个声明中设置所有的轮廓属性。	2
outline-color	设置轮廓的颜色。	2
outline-style	设置轮廓的样式。	2
outline-width	设置轮廓的宽度。	2

CSS 框模型 (Box Model) 规定了元素框处理元素内容、内边距、边框 和 外边距 的方式。
元素框的最内部分是实际的内容，直接包围内容的是内边距。内边距呈现了元素的背景。内边距的边缘是边框。边框以外是外边距，外边距默认是透明的，因此不会遮挡其后的任何元素。
提示：背景应用于由内容和内边距、边框组成的区域。
内边距、边框和外边距都是可选的，默认值是零。但是，许多元素将由用户代理样式表设置外边距和内边距。可以通过将元素的 margin 和 padding 设置为零来覆盖这些浏览器样式。这可以分别进行，也可以使用通用选择器对所有元素进行设置：
* { margin: 0; padding: 0; }
在 CSS 中，width 和 height 指的是内容区域的宽度和高度。增加内边距、边框和外边距不会影响内容区域的尺寸，但是会增加元素框的总尺寸。



一切皆为框
div、h1 或 p 元素常常被称为块级元素。这意味着这些元素显示为一块内容，即“块框”。与之相反，span 和 strong 等元素称为“行内元素”，这是因为它们的内容显示在行中，即“行内框”。
您可以使用 display 属性改变生成的框的类型。这意味着，通过将 display 属性设置为 block，可以让行内元素
（比如 <a href=""></a> 元素）表现得像块级元素一样。还可以通过把 display 设置为 none，让生成的元素根本没有框。这样的话，该框及其所有内容就不再显示，不占用文档中的空间。

CSS 定位机制
CSS 有三种基本的定位机制：普通流、浮动和绝对定位。
除非专门指定，否则所有框都在普通流中定位。也就是说，普通流中的元素的位置由元素在 (X)HTML 中的位置决定。
块级框从上到下一个接一个地排列，框之间的垂直距离是由框的垂直外边距计算出来。
行内框在一行中水平布置。可以使用水平内边距、边框和外边距调整它们的间距。但是，垂直内边距、边框和外边距不影响行内框的高度。由一行形成的水平框称为行框（Line Box），行框的高度总是足以容纳它包含的所有行内框。不过，设置行高可以增加这个框的高度。
在下面的章节，我们会为您详细讲解相对定位、绝对定位和浮动。

CSS position 属性
通过使用 position 属性，我们可以选择 4 种不同类型的定位，这会影响元素框生成的方式。
position 属性值的含义：
static
元素框正常生成。块级元素生成一个矩形框，作为文档流的一部分，行内元素则会创建一个或多个行框，置于其父元素中。
relative
元素框偏移某个距离。元素仍保持其未定位前的形状，它原本所占的空间仍保留。
absolute
元素框从文档流完全删除，并相对于其包含块定位。包含块可能是文档中的另一个元素或者是初始包含块。元素原先在正常文档流中所占的空间会关闭，就好像元素原来不存在一样。元素定位后生成一个块级框，而不论原来它在正常流中生成何种类型的框。
fixed
元素框的表现类似于将 position 设置为 absolute，不过其包含块是视窗本身。
提示：相对定位实际上被看作普通流定位模型的一部分，因为元素的位置相对于它在普通流中的位置。


CSS 定位属性
CSS 定位属性允许你对元素进行定位。
属性	描述
position	把元素放置到一个静态的、相对的、绝对的、或固定的位置中。
top	定义了一个定位元素的上外边距边界与其包含块上边界之间的偏移。
right	定义了定位元素右外边距边界与其包含块右边界之间的偏移。
bottom	定义了定位元素下外边距边界与其包含块下边界之间的偏移。
left	定义了定位元素左外边距边界与其包含块左边界之间的偏移。
overflow	设置当元素的内容溢出其区域时发生的事情。
clip	设置元素的形状。元素被剪入这个形状之中，然后显示出来。
vertical-align	设置元素的垂直对齐方式。
z-index	设置元素的堆叠顺序。

h2.pos_left{ position:relative; left:-20px; }
h2.pos_right{ position:relative; left:20px; }
滚动条显示溢出内容:或者设置为auto,自动处理溢出
div{ background-color:#00FFFF; width:150px; height:150px; overflow: scroll; }
剪切图像：
img { position:absolute; clip:rect(0px 50px 200px 0px); }
文本中的图像:
<style type="text/css">
img.top { vertical-align:text-top; }
img.bottom { vertical-align:text-bottom; }
</style>

Z-index可被用于将在一个元素放置于另一元素之后。值越大优先级越高.
img.x{ position:absolute; left:0px; top:0px; z-index:-1; }

注意，在使用相对定位时，无论是否进行移动，元素仍然占据原来的空间。因此，移动元素会导致它覆盖其它框。
CSS 绝对定位
绝对定位使元素的位置与文档流无关，因此不占据空间。这一点与相对定位不同，相对定位实际上被看作普通流定位模型的一部分，因为元素的位置相对于它在普通流中的位置。


绝对定位的元素的位置相对于最近的已定位祖先元素，如果元素没有已定位的祖先元素，那么它的位置相对于最初的包含块。
对于定位的主要问题是要记住每种定位的意义。所以，现在让我们复习一下学过的知识吧：相对定位是“相对于”元素在文档中的初始位置，而绝对定位是“相对于”最近的已定位祖先元素，如果不存在已定位的祖先元素，那么“相对于”最初的包含块。

要想阻止行框围绕浮动框，需要对该框应用 clear 属性。clear 属性的值可以是 left、right、both 或 none，它表示框的哪些边不应该挨着浮动框。

类选择器还是 ID 选择器？
在类选择器这一章中我们曾讲解过，可以为任意多个元素指定类。前一章中类名 important 被应用到 p 和 h1 元素，而且它还可以应用到更多元素。
区别 1：只能在文档中使用一次
与类不同，在一个 HTML 文档中，ID 选择器会使用一次，而且仅一次。
区别 2：不能使用 ID 词列表
不同于类选择器，ID 选择器不能结合使用，因为 ID 属性不允许有以空格分隔的词列表。
区别 3：ID 能包含更多含义
类似于类，可以独立于元素来选择 ID。有些情况下，您知道文档中会出现某个特定 ID 值，但是并不知道它会出现在哪个元素上，所以您想声明独立的 ID 选择器。例如，您可能知道在一个给定的文档中会有一个 ID 值为 mostImportant 的元素。您不知道这个最重要的东西是一个段落、一个短语、一个列表项还是一个小节标题。您只知道每个文档都会有这么一个最重要的内容，它可能在任何元素中，而且只能出现一个。

属性选择:
与简单属性选择器类似，可以把多个属性-值选择器链接在一起来选择一个文档。
a[href="http://www.w3school.com.cn/"][title="W3School"] { color: red; }

强大的后代选择器!（descendant selector）又称为包含选择器。
后代选择器可以选择作为某元素后代的元素。
根据上下文选择元素
我们可以定义后代选择器来创建一些规则，使这些规则在某些文档结构中起作用，而在另外一些结构中不起作用。
举例来说，如果您希望只对 h1 元素中的 em 元素应用样式，可以这样写：
h1 em { color:red; }

子元素选择器:
如果您不希望选择任意的后代元素，而是希望缩小范围，只选择某个元素的子元素，请使用子元素选择器（Child selector）。
例如，如果您希望选择只作为 h1 元素子元素的 strong 元素，可以这样写：
h1 > strong { color:red; }

CSS 伪类用于向某些选择器添加特殊的效果。
提示：在 CSS 定义中，a:hover 必须被置于 a:link 和 a:visited 之后，才是有效的。
提示：在 CSS 定义中，a:active 必须被置于 a:hover 之后，才是有效的。
提示：伪类名称对大小写不敏感。

伪类可以与 CSS 类配合使用：
a.red : visited { color: #FF0000; }

伪类
W3C："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。
属性	描述	CSS
:active	向被激活的元素添加样式。	1
:focus	向拥有键盘输入焦点的元素添加样式。	2
:hover	当鼠标悬浮在元素上方时，向元素添加样式。	1
:link	向未被访问的链接添加样式。	1
:visited	向已被访问的链接添加样式。	1
:first-child	向元素的第一个子元素添加样式。	2
:lang	向带有指定 lang 属性的元素添加样式。	2




"first-line" 伪元素用于向文本的首行设置特殊样式。
在下面的例子中，浏览器会根据 "first-line" 伪元素中的样式对 p 元素的第一行文本进行格式化：
p:first-line
  { color:#ff0000; font-variant:small-caps; }

注释："first-line" 伪元素只能用于块级元素。
注释：下面的属性可应用于 "first-line" 伪元素：
font
color
background
word-spacing
letter-spacing
text-decoration
vertical-align
text-transform
line-height
clear


:first-letter 伪元素
"first-letter" 伪元素用于向文本的首字母设置特殊样式：
p:first-letter  { color:#ff0000; font-size:xx-large; }


CSS2 - :before 伪元素
":before" 伪元素可以在元素的内容前面插入新内容。
下面的例子在每个 <h1></h1> 元素前面插入一幅图片：
h1:before  { content:url(logo.gif); }
亲自试一试
CSS2 - :after 伪元素
":after" 伪元素可以在元素的内容之后插入新内容。
下面的例子在每个 <h1></h1> 元素后面插入一幅图片：
h1:after  { content:url(logo.gif); }

伪元素:
W3C："W3C" 列指示出该属性在哪个 CSS 版本中定义（CSS1 还是 CSS2）。
属性	描述	CSS
:first-letter	向文本的第一个字母添加特殊样式。	1
:first-line	向文本的首行添加特殊样式。	1
:before	在元素之前添加内容。	2
:after	在元素之后添加内容。	2



使用 margin 属性来水平对齐
可通过将左和右外边距设置为 "auto"，来对齐块元素。
注释：除非已经声明了 !DOCTYPE，否则使用 margin:auto 在 IE8 以及更早的版本中是无效的。
把左和右外边距设置为 auto，规定的是均等地分配可用的外边距。结果就是居中的元素：


使用 position 属性进行左和右对齐
对齐元素的方法之一是使用绝对定位：
实例
.right
{ position:absolute; right:0px; width:300px; background-color:#b0e0e6; }


使用 float 属性来进行左和右对齐
对齐元素的另一种方法是使用 float 属性：
实例
.right
{ float:right; width:300px; background-color:#b0e0e6; }


CSS 尺寸属性
CSS 尺寸属性允许你控制元素的高度和宽度。同样，还允许你增加行间距。
属性	描述
height	设置元素的高度。
line-height	设置行高。
max-height	设置元素的最大高度。
max-width	设置元素的最大宽度。
min-height	设置元素的最小高度。
min-width	设置元素的最小宽度。
width	设置元素的宽度。


CSS 分类属性 (Classification)
CSS 分类属性允许你控制如何显示元素，设置图像显示于另一元素中的何处，相对于其正常位置来定位元素，使用绝对值来定位元素，以及元素的可见度。
属性	描述
clear	设置一个元素的侧面是否允许其他的浮动元素。
cursor	规定当指向某元素之上时显示的指针类型。
display	设置是否及如何显示元素。
float	定义元素在哪个方向浮动。
position	把元素放置到一个静态的、相对的、绝对的、或固定的位置中。
visibility	设置元素是否可见或不可见。

通过 CSS 创建透明图像是很容易的。
注释：CSS opacity 属性是 W3C CSS 推荐标准的一部分。


下面的图片库是由 CSS 创建的：
实例
<!doctype html>
<html>
<head>
	<style>
div.img
  { margin:3px; border:1px solid #bebebe; height:auto; width:auto; float:left; text-align:center; }
div.img img
  { display:inline; margin:3px; border:1px solid #bebebe; }
div.img a:hover img
  { border:1px solid #333333; }
div.desc
  { text-align:center; font-weight:normal; width:150px; font-size:12px; margin:10px 5px 10px 5px; }
</style>
</head>
<body>

	<div class="img">
		<a target="_blank" href="/i/tulip_ballade.jpg">
			<img src="/i/tulip_ballade_s.jpg" alt="Ballade" width="160" height="160"></a>
		<div class="desc">在此处添加对图像的描述</div>
	</div>

	<div class="img">
		<a target="_blank" href="/i/tulip_flaming_club.jpg">
			<img src="/i/tulip_flaming_club_s.jpg" alt="Ballade" width="160" height="160"></a>
		<div class="desc">在此处添加对图像的描述</div>
	</div>

	<div class="img">
		<a target="_blank" href="/i/tulip_fringed_family.jpg">
			<img src="/i/tulip_fringed_family_s.jpg" alt="Ballade" width="160" height="160"></a>
		<div class="desc">在此处添加对图像的描述</div>
	</div>

	<div class="img">
		<a target="_blank" href="/i/tulip_peach_blossom.jpg">
			<img src="/i/tulip_peach_blossom_s.jpg" alt="Ballade" width="160" height="160"></a>
		<div class="desc">在此处添加对图像的描述</div>
	</div>

</body>
</html>