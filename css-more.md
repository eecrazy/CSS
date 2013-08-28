
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