常用HTML标签元素结合及简介.
HTML 框架:
http://www.w3school.com.cn/html/html_frames.asp
内联框架:
使用 iframe 作为链接的目标:
<iframe src="/example/html/demo_iframe.html" name="iframe_a"></iframe>
<p><a href="http://www.w3school.com.cn" target="iframe_a">W3School.com.cn</a></p>
<p><b>注释：</b>由于链接的目标匹配 iframe 的名称，所以链接会在 iframe 中打开。</p>
表单：
http://www.w3school.com.cn/html/html_forms.asp
<form>	定义供用户输入的表单
<input>	定义输入域
<textarea>	定义文本域 (一个多行的输入控件)
<label>	定义一个控制的标签
<fieldset>	定义域
<legend>	定义域的标题
<select>	定义一个选择列表
<optgroup>	定义选项组
<option>	定义下拉列表中的选项
<button>	定义一个按钮
图像映射:


表格:http://www.w3school.com.cn/html/html_tables.asp
<h4>一行三列：</h4>
<table border="1">
<tr>
  <td>100</td>
  <td>200</td>
  <td>300</td>
</tr>
</table>

<html></html> 创建一个HTML文档
<head></head> 设置文档标题和其它在网页中不显示的信息
<title></title> 设置文档的标题        
<h1></h1> 最大的标题
<pre></pre> 预先格式化文本,保留原格式，不会改变。用于显示计算机程序代码非常好.          
<u></u> 下划线
<b></b> 黑体字    
<i></i> 斜体字    
<tt></tt> 打字机风格的字体
<cite></cite> 引用,通常是斜体        
<em></em> 强调文本(通常是斜体加黑体)
<strong></strong> 加重文本(通常是斜体加黑体)
<font size="" color=""></font> 设置字体大小从1到7，颜色使用名字或RGB的十六进制值
<BASEFONT></BASEFONT> 基准字体标记
<big></big> 字体加大
<SMALL></SMALL> 字体缩小        
<STRIKE></STRIKE> 加删除线
<CODE></CODE> 程式码          
<KBD></KBD> 键盘字
<SAMP></SAMP> 范例    
<bdo dir="rtl">Here is some Hebrew text</bdo>定义文字方向从右向左输出文本
<VAR></VAR> 变量
<BLOCKQUOTE></BLOCKQUOTE> 向右缩排
<DFN></DFN> 述语定义
<ADDRESS></ADDRESS> 地址标记
<sup></SUP> 上标字    
<SUB></SUB> 下标字
<xmp>...</xmp>固定寬度字体(在文件中空白、換行、定位功能有效)
<plaintext>...</plaintext>固定寬度字體(不執行標記符號)
<listing>...</listing> 固定寬度小字體  
<font color=00ff00>...</font>字體顏色
<font size=1>...</font>最小字體  
<font style ='font-size:100 px'>...</font>無限增大 
格式标志标签
<p></p> 创建一个段落    
<p align=""> 将段落按左、中、右对齐 　
<br> 换行 插入换行符  
<blockquote></blockquote> 从两边缩进文本
<dl></dl> 定义列表
<dt> 放在每个定义术语词前
<dd> 放在每个定义之前
<ol></ol> 创建一个标有数字的列表  
<ul></ul> 创建一个标有圆点的列表
<li> 放在每个列表项之前,若在<ol></ol>之间则每个列表项加上一个数字,
  若在<ul></ul>之间则每个列表项加上一个圆点 　 　
<div align=""></div> 用来排版大块HTML段落,也用于格式化表
<MENU> 选项清单  
<DIR> 目录清单  
<nobr></nobr> 强行不换行
<hr size='9' width='80%' color='ff0000'>水平線(設定寬度)  
<center></center> 水平居中  
链接标志表格标志
<a href="URL"></a> 创建超文本链接  
<a href="mailtEMAIL">
</a> 创建自动发送电子邮件的链接  
<a name="name"></a> 创建位于文档内部的书签
<a href="#name"></a> 创建指向位于文档内部书签的链接
<BASE> 文档中不能被该站点辨识的其它所有链接源的URL
<LINK> 定义一个链接和源之间的相互关系 
链接标记注解：
◆target="..."决定链接源在什么地方显示(用户自定义的名字，_blank,_parent,_self,_top
◆rel="..."发送链接的类型  
◆rev="..."保存链接的类型
◆accesskey="..."指定该元素的热键
◆shape="..."允许我们使用已定义的形状定义客户端的图形镜像(default，rect，circle，poly
◆coord="..."使用像素或者长度百分比来定义形状的尺寸
◆tabindex="..."使用定义过的tabindex元素设置在各个元素之间的焦点获取顺序(使用tab键使元素获得焦点)
大部分标签可以运用时候通过CSS控制改变样式达到我们想要的布局效果。

文本格式化标签
标签	描述
<b>	定义粗体文本。
<big>	定义大号字。
<em>	定义着重文字。
<i>	定义斜体字。
<small>	定义小号字。
<strong>	定义加重语气。
<sub>	定义下标字。
<sup>	定义上标字。
<ins>	定义插入字。
<del>	定义删除字。
<s>	不赞成使用。使用 <del> 代替。
<strike>	不赞成使用。使用 <del> 代替。
<u>	不赞成使用。使用样式（style）代替。
“计算机输出”标签
标签	描述
<code>	定义计算机代码。
<kbd>	定义键盘码。
<samp>	定义计算机代码样本。
<tt>	定义打字机代码。
<var>	定义变量。
<pre>	定义预格式文本。
<listing>	不赞成使用。使用 <pre> 代替。
<plaintext>	不赞成使用。使用 <pre> 代替。
<xmp>	不赞成使用。使用 <pre> 代替。
引用、引用和术语定义
标签	描述
<abbr>	定义缩写。
<acronym>	定义首字母缩写。
<address>	定义地址。
<bdo>	定义文字方向。
<blockquote>	定义长的引用。
<q>	定义短的引用语。
<cite>	定义引用、引证。
<dfn>	定义一个定义项目。
<a href="http://www.w3school.com.cn/" target="_blank">Visit W3School!</a>
<p>如果把链接的 target 属性设置为 "_blank"，该链接会在新窗口中打开。</p>
<a href="/index.html" target="_top">请点击这里！</a> 跳出框架，设置target属性
<a href="mailto:someone@microsoft.com?subject=Hello%20again">发送邮件</a>邮件链接
这是另一个高级 mailto 链接：
<a href="mailto:someone@microsoft.com?cc=someoneelse@microsoft.com&bcc=andsomeoneelse2@microsoft.com&subject=Summer%20Party&body=You%20are%20invited%20to%20a%20big%20summer%20party!">发送邮件！</a>
<p>图像 <img src="/i/eg_cute.gif" align="bottom"> 在文本中</p>图像在文本中的对齐方式
<img src ="/i/eg_cute.gif" align ="left">带有图像的一个段落。图像的 align 属性设置为 "left"。图像将浮动到文本的左侧。
<img src="/i/eg_mouse.jpg" width="200" height="200">
通过改变 img 标签的 "height" 和 "width" 属性的值，您可以放大或缩小图像
您也可以把图像作为链接来使用：
<a href="/example/html/lastpage.html"><img border="0" src="/i/eg_buttonnext.gif" />
带有可点击区域的图像映射：
<img src="planets.jpg" border="0" usemap="#planetmap" alt="Planets" />
<map name="planetmap" id="planetmap">
  <area shape="circle" coords="180,139,14" href ="venus.html" alt="Venus" />
  <area shape="circle" coords="129,161,10" href ="mercur.html" alt="Mercury" />
  <area shape="rect" coords="0,0,110,260" href ="sun.html" alt="Sun" />
</map>

1:无序列表
无序列表是一个项目的列表，此列项目使用粗体圆点（典型的小黑圆圈）进行标记。
无序列表始于 <ul> 标签。每个列表项始于 <li>。
<ul type="disc">通过type属性定义样式
<li>Coffee</li>
<li>Milk</li>
</ul>
2:有序列表
同样，有序列表也是一列项目，列表项目使用数字进行标记。
有序列表始于 <ol> 标签。每个列表项始于 <li> 标签。
<ol>
<li>Coffee</li>
<li>Milk</li>
</ol>
3:self定义列表
自定义列表不仅仅是一列项目，而是项目及其注释的组合。
自定义列表以 <dl> 标签开始。每个自定义列表项以 <dt> 开始。每个自定义列表项的定义以 <dd> 开始。
<dl>
<dt>Coffee</dt>
<dd>Black hot drink</dd>
<dt>Milk</dt>
<dd>White cold drink</dd>
</dl>

HTML <div> 元素
HTML <div> 元素是块级元素，它是可用于组合其他 HTML 元素的容器。
<div> 元素没有特定的含义。除此之外，由于它属于块级元素，浏览器会在其前后显示折行。
如果与 CSS 一同使用，<div> 元素可用于对大的内容块设置样式属性。
<div> 元素的另一个常见的用途是文档布局。它取代了使用表格定义布局的老式方法。使用 <table> 元素进行文档布局不是表格的正确用法。<table> 元素的作用是显示表格化的数据。
HTML <span> 元素
HTML <span> 元素是内联元素，可用作文本的容器。
<span> 元素也没有特定的含义。
当与 CSS 一同使用时，<span> 元素可用于为部分文本设置样式属性。











基于内容的样式
基于内容的样式标签会告诉浏览器它所包含的文本具有特定的含义、上下文或者用法。然后浏览器就会把与该含义、上下文或者用法一致的格式应用在文本上。请注意这里面的区别。基于内容的标签赋予含义，而不是格式化。因此，它们对于自动处理来说非常重要；计算机并不关心文档的外观如何。
因为字体样式是通过语义线索来指定的，因此浏览器可以为用户选择一种合适的显示样式。由于不同地点的样式各种各样，所以使用基于内容的样式可以帮助你确保自己的文档对广大范围的读者来说都是有意义的。这一点在专门供那些盲人和残疾人所使用的浏览器上显得尤其重要，因为他们的显示选项可能和我们传统的文本根本不同，或者在某方面具有非常大的局限性。
当前的 HTML 和 XHTML 标准并没有为每一个基于内容的标签都定义一种格式；它们仅仅规定必须用与文档中普通文本不同的方式来显示基于内容的样式。标准甚至没有要求这些基于内容的样式彼此之间都要用不同的方式显示。在实际应用中，你可能会发现很多这样的标签和传统的印刷有着非常明显的关系，它们有着相似的含义和显示样式，而且在多数浏览器中都以相同的样式和字体来显示。
使用 HTML/XHTML 基于内容的样式标签时要遵从一些规则，因为仅仅是简单地想想文本该如何显示，而不必知道这些文本的含义是什么，是十分容易的。一旦你开始使用基于内容的样式之后，文档将会更加一致，而且可以更好地帮助执行自动搜索和内容编辑。这些标签是：
<abbr>
<acronym>
<cite>
<code>
<dfn>
<em>
<kbd>
<samp>
<strong>
<var>
物理样式
在讨论基于内容的样式标签时，我们经常用到“意图”这个词。这是因为由标签传达的含义比浏览器显示文本的方式更为重要。然而，在某些情况下，可能是出于合法性或者版权等方面的原因的考虑，你希望文本以某种特殊的方式来显示（例如斜体或加粗）。在这种情况下，就可以对文本使用物理样式。
虽然其他文字处理系统的趋势是精确地控制样式和外观，但是在使用 HTML 或 XHTML 时，除非极少情况下，都应该避免使用物理标签。应当尽可能地向浏览器提供上下文信息，并使用基于内容的样式。尽管现在浏览器不过是以斜体或者粗体字来显示这些文本，但是将来的浏览器和各种文档生成工具可能会以非常有创建的方式来利用这些基于内容的样式。
当前的 HTML/XHTML 标准一共提供了 9 种物理样式，包括粗体（bold）、斜体（italic）、等宽（monospaced）、下划线（underlined）、删除线（strikethrough）、放大（larger）、缩小（smaller）、上标（superscripted）和下标（subscripted）文本。这些标签是：
<b>
<big>
<i>
<s>
<small>
<strike>
<sub>
<sup>
<tt>