JavaScript 教程
JavaScript 是属于网络的脚本语言！
JavaScript 被数百万计的网页用来改进设计、验证表单、检测浏览器、创建cookies，以及更多的应用。
JavaScript 是因特网上最流行的脚本语言。
JavaScript 很容易使用！你一定会喜欢它的！

HTML 中的脚本必须位于 <script> 与 </script> 标签之间。
脚本可被放置在 HTML 页面的 <body> 和 <head> 部分中。

<body> 中的 JavaScript
在本例中，JavaScript 会在页面加载时向 HTML 的 <body> 写文本：
<script>
document.write("<h1>This is a heading</h1>");
document.write("<p>This is a paragraph</p>");
</script>

JavaScript 函数和事件
上面例子中的 JavaScript 语句，会在页面加载时执行。
通常，我们需要在某个事件发生时执行代码，比如当用户点击按钮时。
如果我们把 JavaScript 代码放入函数中，就可以在事件发生时调用该函数。

<head> 或 <body> 中的 JavaScript
您可以在 HTML 文档中放入不限数量的脚本。
脚本可位于 HTML 的 <body> 或 <head> 部分中，或者同时存在于两个部分中。
通常的做法是把函数放入 <head> 部分中，或者放在页面底部。这样就可以把它们安置到同一处位置，不会干扰页面的内容。

外部的 JavaScript
也可以把脚本保存到外部文件中。外部文件通常包含被多个网页使用的代码。
外部 JavaScript 文件的文件扩展名是 .js。
如需使用外部文件，请在 <script> 标签的 "src" 属性中设置该 .js 文件：
<script src="myScript.js"></script>
在 <head> 或 <body> 中引用脚本文件都是可以的。实际运行效果与您在 <script> 标签中编写脚本完全一致。
提示：外部脚本不能包含 <script> 标签。


操作 HTML 元素
如需从 JavaScript 访问某个 HTML 元素，您可以使用 document.getElementById(id) 方法。
请使用 "id" 属性来标识 HTML 元素：
document.getElementById("demo").innerHTML="My First JavaScript";
JavaScript 由 web 浏览器来执行。在这种情况下，浏览器将访问 id="demo" 的 HTML 元素，并把它的内容（innerHTML）替换为 "My First JavaScript"。


写到文档输出
下面的例子直接把 <p> 元素写到 HTML 文档输出中：
document.write("<p>My First JavaScript</p>");


警告
请使用 document.write() 仅仅向文档输出写内容。
如果在文档已完成加载后执行 document.write，整个 HTML 页面将被覆盖：
实例
<button onclick="myFunction()">点击这里</button>
<script>
function myFunction()
{
document.write("糟糕！文档消失了。");
}
</script>

Windows 8 中的 JavaScript
提示：微软支持通过 JavaScript 创建 Windows 8 app。
对于因特网和视窗操作系统，JavaScript 都意味着未来。


分号 ;
分号用于分隔 JavaScript 语句。
通常我们在每条可执行的语句结尾添加分号。
使用分号的另一用处是在一行中编写多条语句。

JavaScript 对大小写敏感。
JavaScript 对大小写是敏感的。
当编写 JavaScript 语句时，请留意是否关闭大小写切换键。

空格
JavaScript 会忽略多余的空格。您可以向脚本添加空格，来提高其可读性。下面的两行代码是等效的：
var name="Hello";
var name = "Hello";

对代码行进行折行
您可以在文本字符串中使用反斜杠对代码行进行换行。下面的例子会正确地显示：
document.write("Hello \
World!");

JavaScript 是脚本语言。浏览器会在读取代码时，逐行地执行脚本代码。而对于传统编程来说，会在执行前对所有代码进行编译。



下面的例子使用单行注释来解释代码：
// 输出标题：
document.getElementById("myH1").innerHTML="Welcome to my Homepage";
多行注释以 /* 开始，以 */ 结尾。

把变量看做存储数据的容器。

JavaScript 变量
与代数一样，JavaScript 变量可用于存放值（比如 x=2）和表达式（比如 z=x+y）。
变量可以使用短名称（比如 x 和 y），也可以使用描述性更好的名称（比如 age, sum, totalvolume）。
变量必须以字母开头
变量也能以 $ 和 _ 符号开头（不过我们不推荐这么做）
变量名称对大小写敏感（y 和 Y 是不同的变量）
提示：JavaScript 语句和 JavaScript 变量都对大小写敏感。

JavaScript 数据类型
JavaScript 变量还能保存其他数据类型，比如文本值 (name="Bill Gates")。
在 JavaScript 中，类似 "Bill Gates" 这样一条文本被称为字符串。
JavaScript 变量有很多种类型，但是现在，我们只关注数字和字符串。
当您向变量分配文本值时，应该用双引号或单引号包围这个值。
当您向变量赋的值是数值时，不要使用引号。如果您用引号包围数值，该值会被作为文本来处理。

var pi=3.14;
var name="Bill Gates";
var answer='Yes I am!';

我们使用 var 关键词来声明变量：
var carname;

一个好的编程习惯是，在代码开始处，统一对需要的变量进行声明。
您可以在一条语句中声明很多变量。该语句以 var 开头，并使用逗号分隔变量即可：
var name="Gates", age=56, job="CEO";

在执行过以下语句后，变量 carname 的值将是 undefined：
var carname;

如果重新声明 JavaScript 变量，该变量的值不会丢失：
在以下两条语句执行后，变量 carname 的值依然是 "Volvo"：
var carname="Volvo";
var carname;

JavaScript 数据类型
字符串、数字、布尔、数组、对象、Null、Undefined

JavaScript 拥有动态类型。这意味着相同的变量可用作不同的类型：

JavaScript 数组
下面的代码创建名为 cars 的数组：
var cars=new Array();
cars[0]="Audi";
cars[1]="BMW";
cars[2]="Volvo";

或者 (condensed array):
var cars=new Array("Audi","BMW","Volvo");
或者 (literal array):
var cars=["Audi","BMW","Volvo"];

JavaScript 对象
对象由花括号分隔。在括号内部，对象的属性以名称和值对的形式 (name : value) 来定义。属性由逗号分隔：
var person={firstname:"Bill", lastname:"Gates", id:5566};

空格和折行无关紧要。声明可横跨多行：
var person={
firstname : "Bill",
lastname  : "Gates",
id        :  5566
};
对象属性有两种寻址方式：
name=person.lastname;
name=person["lastname"];

Undefined 这个值表示变量不含有值。
可以通过将变量的值设置为 null 来清空变量。

声明变量类型
当您声明新变量时，可以使用关键词 "new" 来声明其类型：
var carname=new String;
var x=      new Number;
var y=      new Boolean;
var cars=   new Array;
var person= new Object;
JavaScript 变量均为对象。当您声明一个变量时，就创建了一个新的对象。

JavaScript 中的所有事物都是对象：字符串、数字、数组、日期，等等。
在 JavaScript 中，对象是拥有属性和方法的数据。

JavaScript 中的对象
在 JavaScript 中，对象是数据（变量），拥有属性和方法。
当您像这样声明一个 JavaScript 变量时：
var txt = "Hello";
您实际上已经创建了一个 JavaScript 字符串对象。字符串对象拥有内建的属性 length。对于上面的字符串来说，length 的值是 5。字符串对象同时拥有若干个内建的方法。

属性：
txt.length=5
方法：
txt.indexOf()
txt.replace()
txt.search()

创建 JavaScript 对象
JavaScript 中的几乎所有事务都是对象：字符串、数字、数组、日期、函数，等等。
你也可以创建自己的对象。
本例创建名为 "person" 的对象，并为其添加了四个属性：
实例
person=new Object();
person.firstname="Bill";
person.lastname="Gates";
person.age=56;
person.eyecolor="blue";


在面向对象的语言中，使用 camel-case 标记法的函数是很常见的。您会经常看到 someMethod() 这样的函数名，而不是 some_method()。

函数是由事件驱动的或者当它被调用时执行的可重复使用的代码块。

函数就是包裹在花括号中的代码块，前面使用了关键词 function：
function functionname()
{
这里是要执行的代码
}

当调用该函数时，会执行函数内的代码。
可以在某事件发生时直接调用函数（比如当用户点击按钮时），并且可由 JavaScript 在任何位置进行调用。

调用带参数的函数
在调用函数时，您可以向其传递值，这些值被称为参数。
这些参数可以在函数中使用。
您可以发送任意多的参数，由逗号 (,) 分隔：
myFunction(argument1,argument2)
当您声明函数时，请把参数作为变量来声明：
function myFunction(var1,var2)
{
这里是要执行的代码
}
变量和参数必须以一致的顺序出现。第一个变量就是第一个被传递的参数的给定的值，以此类推。

function myFunction(name,job)
{
alert("Welcome " + name + ", the " + job);
}

带有返回值的函数
有时，我们会希望函数将值返回调用它的地方。
通过使用 return 语句就可以实现。
在使用 return 语句时，函数会停止执行，并返回指定的值。
语法
function myFunction()
{
var x=5;
return x;
}

注释：整个 JavaScript 并不会停止执行，仅仅是函数。JavaScript 将继续执行代码，从调用函数的地方。
函数调用将被返回值取代：
var myVar=myFunction();

在您仅仅希望退出函数时 ，也可使用 return 语句。返回值是可选的：

局部 JavaScript 变量
在 JavaScript 函数内部声明的变量（使用 var）是局部变量，所以只能在函数内部访问它。（该变量的作用域是局部的）。
您可以在不同的函数中使用名称相同的局部变量，因为只有声明过该变量的函数才能识别出该变量。
只要函数运行完毕，本地变量就会被删除。

全局 JavaScript 变量
在函数外声明的变量是全局变量，网页上的所有脚本和函数都能访问它。

JavaScript 变量的生存期
JavaScript 变量的生命期从它们被声明的时间开始。
局部变量会在函数运行以后被删除。
全局变量会在页面关闭后被删除。

向未声明的 JavaScript 变量来分配值
如果您把值赋给尚未声明的变量，该变量将被自动作为全局变量声明。
这条语句：
carname="Volvo";
将声明一个全局变量 carname，即使它在函数内执行。

运算符与c++一样!!

比较运算符
比较运算符在逻辑语句中使用，以测定变量或值是否相等。
给定 x=5，下面的表格解释了比较运算符：
运算符	描述	例子
==	等于	x==8 为 false
===	全等（值和类型）	x===5 为 true；x==="5" 为 false
!=	不等于	x!=8 为 true
>	大于	x>8 为 false
<	小于	x<8 为 true
>=	大于或等于	x>=8 为 false
<=	小于或等于	x<=8 为 true

可以在条件语句中使用比较运算符对值进行比较，然后根据结果来采取行动：
if (age<18) document.write("Too young");

逻辑运算符
逻辑运算符用于测定变量或值之间的逻辑。
给定 x=6 以及 y=3，下表解释了逻辑运算符：
运算符	描述	例子
&&	and	(x < 10 && y > 1) 为 true
||	or	(x==5 || y==5) 为 false
!	not	!(x==y) 为 true

条件语句
通常在写代码时，您总是需要为不同的决定来执行不同的动作。您可以在代码中使用条件语句来完成该任务。
在 JavaScript 中，我们可使用以下条件语句：
if 语句 - 只有当指定条件为 true 时，使用该语句来执行代码
if...else 语句 - 当条件为 true 时执行代码，当条件为 false 时执行其他代码
if...else if....else 语句 - 使用该语句来选择多个代码块之一来执行
switch 语句 - 使用该语句来选择多个代码块之一来执行
c++一样!


循环:
通常我们这样写：
for (var i=0;i<cars.length;i++)
{
document.write(cars[i] + "<br>");
}

不同类型的循环
JavaScript 支持不同类型的循环：
for - 循环代码块一定的次数
for/in - 循环遍历对象的属性
while - 当指定的条件为 true 时循环指定的代码块
do/while - 同样当指定的条件为 true 时循环指定的代码块

var person={fname:"John",lname:"Doe",age:25};
JavaScript for/in 语句循环遍历对象的属性：
for (x in person)
  {
  txt=txt + person[x];
  }

break 语句用于跳出循环。
continue 用于跳过循环中的一个迭代。

try 语句测试代码块的错误。
catch 语句处理错误。
throw 语句创建自定义错误。

错误一定会发生
当 JavaScript 引擎执行 JavaScript 代码时，会发生各种错误：
可能是语法错误，通常是程序员造成的编码错误或错别字。
可能是拼写错误或语言中缺少的功能（可能由于浏览器差异）。
可能是由于来自服务器或用户的错误输出而导致的错误。
当然，也可能是由于许多其他不可预知的因素。

JavaScript 抛出错误
当错误发生时，当事情出问题时，JavaScript 引擎通常会停止，并生成一个错误消息。
描述这种情况的技术术语是：JavaScript 将抛出一个错误。

JavaScript 测试和捕捉
try 语句允许我们定义在执行时进行错误测试的代码块。
catch 语句允许我们定义当 try 代码块发生错误时，所执行的代码块。
JavaScript 语句 try 和 catch 是成对出现的。
语法
try
  {
  //在这里运行代码
  }
catch(err)
  {
  //在这里处理错误
  }
Throw 语句
throw 语句允许我们创建自定义错误。
正确的技术术语是：创建或抛出异常（exception）。
如果把 throw 与 try 和 catch 一起使用，那么您能够控制程序流，并生成自定义的错误消息。
异常可以是 JavaScript 字符串、数字、逻辑值或对象。

本例检测输入变量的值。如果值是错误的，会抛出一个异常（错误）。catch 会捕捉到这个错误，并显示一段自定义的错误消息：
<script>
function myFunction()
{
try
  {
  var x=document.getElementById("demo").value;
  if(x=="")    throw "empty";
  if(isNaN(x)) throw "not a number";
  if(x>10)     throw "too high";
  if(x<5)      throw "too low";
  }
catch(err)
  {
  var y=document.getElementById("mess");
  y.innerHTML="Error: " + err + ".";
  }
}
</script>

<h1>My First JavaScript</h1>
<p>Please input a number between 5 and 10:</p>
<input id="demo" type="text">
<button type="button" onclick="myFunction()">Test Input</button>
<p id="mess"></p>

JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。
JavaScript 表单验证
JavaScript 可用来在数据被送往服务器前对 HTML 表单中的这些输入数据进行验证。
被 JavaScript 验证的这些典型的表单数据有：
用户是否已填写表单中的必填项目？
用户输入的邮件地址是否合法？
用户是否已输入合法的日期？
用户是否在数据域 (numeric field) 中输入了文本？

必填（或必选）项目
下面的函数用来检查用户是否已填写表单中的必填（或必选）项目。假如必填或必选项为空，那么警告框会弹出，并且函数的返回值为 false，否则函数的返回值则为 true（意味着数据没有问题）：
下面是连同 HTML 表单的代码：
<html>
<head>
<script type="text/javascript">

function validate_required(field,alerttxt)
{
with (field)
  {
  if (value==null||value=="")
    {alert(alerttxt);return false}
  else {return true}
  }
}

function validate_form(thisform)
{
with (thisform)
  {
  if (validate_required(email,"Email must be filled out!")==false)
    {email.focus();return false}
  }
}
</script>
</head>

<body>
<form action="submitpage.htm" onsubmit="return validate_form(this)" method="post">
Email: <input type="text" name="email" size="30">
<input type="submit" value="Submit"> 
</form>
</body>

</html>

E-mail 验证
下面的函数检查输入的数据是否符合电子邮件地址的基本语法。
意思就是说，输入的数据必须包含 @ 符号和点号(.)。同时，@ 不可以是邮件地址的首字符，并且 @ 之后需有至少一个点号：
下面是连同 HTML 表单的完整代码：
<html>
<head>
<script type="text/javascript">
function validate_email(field,alerttxt)
{
with (field)
{
apos=value.indexOf("@")
dotpos=value.lastIndexOf(".")
if (apos<1||dotpos-apos<2) 
  {alert(alerttxt);return false}
else {return true}
}
}

function validate_form(thisform)
{
with (thisform)
{
if (validate_email(email,"Not a valid e-mail address!")==false)
  {email.focus();return false}
}
}
</script>
</head>

<body>
<form action="submitpage.htm"onsubmit="return validate_form(this);" method="post">
Email: <input type="text" name="email" size="30">
<input type="submit" value="Submit"> 
</form>
</body>

</html>

HTML DOM （文档对象模型）
当网页被加载时，浏览器会创建页面的文档对象模型（Document Object Model）。
HTML DOM 模型被构造为对象的树。

通过可编程的对象模型，JavaScript 获得了足够的能力来创建动态的 HTML。
JavaScript 能够改变页面中的所有 HTML 元素
JavaScript 能够改变页面中的所有 HTML 属性
JavaScript 能够改变页面中的所有 CSS 样式
JavaScript 能够对页面中的所有事件做出反应

查找 HTML 元素
通常，通过 JavaScript，您需要操作 HTML 元素。
为了做到这件事情，您必须首先找到该元素。有三种方法来做这件事：
通过 id 找到 HTML 元素
通过标签名找到 HTML 元素
通过类名找到 HTML 元素

通过 id 查找 HTML 元素
在 DOM 中查找 HTML 元素的最简单的方法，是通过使用元素的 id。
实例
本例查找 id="intro" 元素：
var x=document.getElementById("intro");
亲自试一试
如果找到该元素，则该方法将以对象（在 x 中）的形式返回该元素。
如果未找到该元素，则 x 将包含 null。

通过标签名查找 HTML 元素
实例
本例查找 id="main" 的元素，然后查找 "main" 中的所有 <p> 元素：
var x=document.getElementById("main");
var y=x.getElementsByTagName("p");

HTML DOM 教程
在本教程接下来的篇幅中，您将学到：
如何改变 HTML 元素的内容 (innerHTML)
如何改变 HTML 元素的样式 (CSS)
如何对 HTML DOM 事件对出反应
如何添加或删除 HTML 元素

改变 HTML 输出流
JavaScript 能够创建动态的 HTML 内容：
今天的日期是： Sun Aug 25 2013 10:49:37 GMT+0800 (CST)
在 JavaScript 中，document.write() 可用于直接向 HTML 输出流写内容。
实例
<!DOCTYPE html>
<html>
<body>
<script>
document.write(Date());
</script>
</body>
</html>
提示：绝不要使用在文档加载之后使用 document.write()。这会覆盖该文档。

改变 HTML 内容
修改 HTML 内容的最简单的方法时使用 innerHTML 属性。
如需改变 HTML 元素的内容，请使用这个语法：
document.getElementById(id).innerHTML=new HTML
document.getElementById("p1").innerHTML="New text!";

改变 HTML 属性
如需改变 HTML 元素的属性，请使用这个语法：
document.getElementById(id).attribute=new value
document.getElementById("image").src="landscape.jpg";

HTML DOM 允许 JavaScript 改变 HTML 元素的样式。
改变 HTML 样式
如需改变 HTML 元素的样式，请使用这个语法：
document.getElementById(id).style.property=new style
document.getElementById("p2").style.color="blue";

本例改变了 id="id1" 的 HTML 元素的样式，当用户点击按钮时：
<h1 id="id1">My Heading 1</h1>
<button type="button" onclick="document.getElementById('id1').style.color='red'">
点击这里
</button>

如何使元素不可见。您希望元素显示或消失吗？
<p id="p1">这是一段文本。</p>
<input type="button" value="隐藏文本" onclick="document.getElementById('p1').style.visibility='hidden'" />
<input type="button" value="显示文本" onclick="document.getElementById('p1').style.visibility='visible'" />

HTML DOM 使 JavaScript 有能力对 HTML 事件做出反应。
对事件做出反应
我们可以在事件发生时执行 JavaScript，比如当用户在 HTML 元素上点击时。
如需在用户点击某个元素时执行代码，请向一个 HTML 事件属性添加 JavaScript 代码：
onclick=JavaScript

HTML 事件的例子：
当用户点击鼠标时
当网页已加载时
当图像已加载时
当鼠标移动到元素上时
当输入字段被改变时
当提交 HTML 表单时
当用户触发按键时

在本例中，当用户在 <h1> 元素上点击时，会改变其内容：
<h1 onclick="this.innerHTML='谢谢!'">请点击该文本</h1>

HTML 事件属性
如需向 HTML 元素分配 事件，您可以使用事件属性。
向 button 元素分配 onclick 事件：
<button onclick="displayDate()">点击这里</button>

使用 HTML DOM 来分配事件
HTML DOM 允许您通过使用 JavaScript 来向 HTML 元素分配事件：
实例
向 button 元素分配 onclick 事件：
<script>
document.getElementById("myBtn").onclick=function(){displayDate()};
</script>

onload 和 onunload 事件
onload 和 onunload 事件会在用户进入或离开页面时被触发。
onload 事件可用于检测访问者的浏览器类型和浏览器版本，并基于这些信息来加载网页的正确版本。
onload 和 onunload 事件可用于处理 cookie。
实例
<body onload="checkCookies()">

onchange 事件
onchange 事件常结合对输入字段的验证来使用。
下面是一个如何使用 onchange 的例子。当用户改变输入字段的内容时，会调用 upperCase() 函数。
实例
<input type="text" id="fname" onchange="upperCase()">

onmouseover 和 onmouseout 事件
onmouseover 和 onmouseout 事件可用于在用户的鼠标移至 HTML 元素上方或移出元素时触发函数。


onmousedown、onmouseup 以及 onclick 事件
onmousedown, onmouseup 以及 onclick 构成了鼠标点击事件的所有部分。首先当点击鼠标按钮时，会触发 onmousedown 事件，当释放鼠标按钮时，会触发 onmouseup 事件，最后，当完成鼠标点击时，会触发 onclick 事件。

如需所有 HTML DOM 事件的完整列表，请参阅 W3School 提供的 HTML DOM Event 对象参考手册。
创建新的 HTML 元素
如需向 HTML DOM 添加新元素，您必须首先创建该元素（元素节点），然后向一个已存在的元素追加该元素。
实例
<div id="div1">
<p id="p1">这是一个段落</p>
<p id="p2">这是另一个段落</p>
</div>

<script>
var para=document.createElement("p");
var node=document.createTextNode("这是新段落。");
para.appendChild(node);

var element=document.getElementById("div1");
element.appendChild(para);
</script>

这段代码创建新的 <p> 元素：
var para=document.createElement("p");
如需向 <p> 元素添加文本，您必须首先创建文本节点。这段代码创建了一个文本节点：
var node=document.createTextNode("这是新段落。");
然后您必须向 <p> 元素追加这个文本节点：
para.appendChild(node);
最后您必须向一个已有的元素追加这个新元素。
这段代码找到一个已有的元素：
var element=document.getElementById("div1");
这段代码向这个已有的元素追加新元素：
element.appendChild(para);

删除已有的 HTML 元素
如需删除 HTML 元素，您必须首先获得该元素的父元素：
实例
<div id="div1">
<p id="p1">这是一个段落。</p>
<p id="p2">这是另一个段落。</p>
</div>

<script>
var parent=document.getElementById("div1");
var child=document.getElementById("p1");
parent.removeChild(child);
</script>

提示：如果能够在不引用父元素的情况下删除某个元素，就太好了。
不过很遗憾。DOM 需要清楚您需要删除的元素，以及它的父元素。
这是常用的解决方案：找到您希望删除的子元素，然后使用其 parentNode 属性来找到父元素：
var child=document.getElementById("p1");
child.parentNode.removeChild(child);

HTML DOM 教程
在我们的 JavaScript 教程的 HTML DOM 部分，您已经学到了：
如何改变 HTML 元素的内容 (innerHTML)
如何改变 HTML 元素的样式 (CSS)
如何对 HTML DOM 事件作出反应
如何添加或删除 HTML 元素


JavaScript 对象
JavaScript 中的所有事物都是对象：字符串、数值、数组、函数...
此外，JavaScript 允许自定义对象。

JavaScript 对象
JavaScript 提供多个内建对象，比如 String、Date、Array 等等。
对象只是带有属性和方法的特殊数据类型。


创建直接的实例
这个例子创建了对象的一个新实例，并向其添加了四个属性：
实例
person=new Object();
person.firstname="Bill";
person.lastname="Gates";
person.age=56;
person.eyecolor="blue";

使用对象构造器
本例使用函数来构造对象：
实例
function person(firstname,lastname,age,eyecolor)
{
this.firstname=firstname;
this.lastname=lastname;
this.age=age;
this.eyecolor=eyecolor;
}


创建 JavaScript 对象实例
一旦您有了对象构造器，就可以创建新的对象实例，就像这样：
var myFather=new person("Bill","Gates",56,"blue");
var myMother=new person("Steve","Jobs",48,"green");


把属性添加到 JavaScript 对象
您可以通过为对象赋值，向已有对象添加新属性：
假设 personObj 已存在 - 您可以为其添加这些新属性：firstname、lastname、age 以及 eyecolor：
person.firstname="Bill";
person.lastname="Gates";
person.age=56;
person.eyecolor="blue";

JavaScript 类
JavaScript 是面向对象的语言，但 JavaScript 不使用类。
在 JavaScript 中，不会创建类，也不会通过类来创建对象（就像在其他面向对象的语言中那样）。
JavaScript 基于 prototype，而不是基于类的。


JavaScript for...in 循环
JavaScript for...in 语句循环遍历对象的属性。
语法
for (对象中的变量)
  {
  要执行的代码
  }
注释：for...in 循环中的代码块将针对每个属性执行一次。



循环遍历对象的属性：
var person={fname:"Bill",lname:"Gates",age:56};

for (x in person)
  {
  txt=txt + person[x];
  }

JavaScript Number 对象

JavaScript 只有一种数字类型。
可以使用也可以不使用小数点来书写数字。

极大或极小的数字可通过科学（指数）计数法来写：
var y=123e5;    // 12300000
var z=123e-5;   // 0.00123
所有 JavaScript 数字均为 64 位
JavaScript 不是类型语言。与许多其他编程语言不同，JavaScript 不定义不同类型的数字，比如整数、短、长、浮点等等。
JavaScript 中的所有数字都存储为根为 10 的 64 位（8 比特），浮点数。


精度
整数（不使用小数点或指数计数法）最多为 15 位。
小数的最大位数是 17，但是浮点运算并不总是 100% 准确：


八进制和十六进制
如果前缀为 0，则 JavaScript 会把数值常量解释为八进制数，如果前缀为 0 和 "x"，则解释为十六进制数。
实例
var y=0377;
var z=0xFF;
提示：绝不要在数字前面写零，除非您需要进行八进制转换。


数字属性和方法
属性：
MAX VALUE
MIN VALUE
NEGATIVE INFINITIVE
POSITIVE INFINITIVE
NaN
prototype
constructor
方法：
toExponential()
toFixed()
toPrecision()
toString()
valueOf()

JavaScript 字符串(String)对象

String 对象用于处理已有的字符块。
计算字符串的长度.lenght
如何使用长度属性来计算字符串的长度。
为字符串添加样式
如何为字符串添加样式。
indexOf() 方法
如何使用 indexOf() 来定位字符串中某一个指定的字符首次出现的位置。
match() 方法
如何使用 match() 来查找字符串中特定的字符，并且如果找到的话，则返回这个字符。
如何替换字符串中的字符 - replace()
如何使用 replace() 方法在字符串中用某些字符替换另一些字符。

document.write(txt.toUpperCase())


JavaScript Date（日期）对象

返回当日的日期和时间
如何使用 Date() 方法获得当日的日期。
getTime()
getTime() 返回从 1970 年 1 月 1 日至今的毫秒数。
setFullYear()
如何使用 setFullYear() 设置具体的日期。
toUTCString()
如何使用 toUTCString() 将当日的日期（根据 UTC）转换为字符串。
getDay()
如何使用 getDay() 和数组来显示星期，而不仅仅是数字。
显示一个钟表
如何在网页上显示一个钟表。

<html>
<head>
<script type="text/javascript">
function startTime()
{
var today=new Date()
var h=today.getHours()
var m=today.getMinutes()
var s=today.getSeconds()
// add a zero in front of numbers<10
m=checkTime(m)
s=checkTime(s)
document.getElementById('txt').innerHTML=h+":"+m+":"+s
t=setTimeout('startTime()',500)
}

function checkTime(i)
{
if (i<10) 
  {i="0" + i}
  return i
}
</script>
</head>

定义日期
Date 对象用于处理日期和时间。
可以通过 new 关键词来定义 Date 对象。以下代码定义了名为 myDate 的 Date 对象：
var myDate=new Date() 
注释：Date 对象自动使用当前的日期和时间作为其初始值。

操作日期
通过使用针对日期对象的方法，我们可以很容易地对日期进行操作。
在下面的例子中，我们为日期对象设置了一个特定的日期 (2008 年 8 月 9 日)：
var myDate=new Date()
myDate.setFullYear(2008,7,9)

注意：表示月份的参数介于 0 到 11 之间。也就是说，如果希望把月设置为 8 月，则参数应该是 7。
在下面的例子中，我们将日期对象设置为 5 天后的日期：
var myDate=new Date()
myDate.setDate(myDate.getDate()+5)

注意：如果增加天数会改变月份或者年份，那么日期对象会自动完成这种转换。

比较日期
日期对象也可用于比较两个日期。

数组对象的作用是：使用单独的变量名来存储一系列的值。
实例
创建数组
创建数组，为其赋值，然后输出这些值。
For...In 声明
使用 for...in 声明来循环输出数组中的元素。
合并两个数组 - concat()
如何使用 concat() 方法来合并两个数组。
用数组的元素组成字符串 - join()
如何使用 join() 方法将数组的所有元素组成一个字符串。
文字数组 - sort()
如何使用 sort() 方法从字面上对数组进行排序。
数字数组 - sort()
如何使用 sort() 方法从数值上对数组进行排序。

定义数组
数组对象用来在单独的变量名中存储一系列的值。
我们使用关键词 new 来创建数组对象。下面的代码定义了一个名为 myArray 的数组对象：
var myArray=new Array()


Math（算数）对象的作用是：执行常见的算数任务。
实例
round()
如何使用 round()。
random()
如何使用 random() 来返回 0 到 1 之间的随机数。
max()
如何使用 max() 来返回两个给定的数中的较大的数。（在 ECMASCript v3 之前，该方法只有两个参数。）
min()
如何使用 min() 来返回两个给定的数中的较小的数。（在 ECMASCript v3 之前，该方法只有两个参数。）



Math 对象
Math（算数）对象的作用是：执行普通的算数任务。
Math 对象提供多种算数值类型和函数。无需在使用这个对象之前对它进行定义。
算数值
JavaScript 提供 8 种可被 Math 对象访问的算数值：
常数
圆周率
2 的平方根
1/2 的平方根
2 的自然对数
10 的自然对数
以 2 为底的 e 的对数
以 10 为底的 e 的对数
这是在 Javascript 中使用这些值的方法：（与上面的算数值一一对应）
Math.E
Math.PI
Math.SQRT2
Math.SQRT1_2
Math.LN2
Math.LN10
Math.LOG2E
Math.LOG10E
算数方法
除了可被 Math 对象访问的算数值以外，还有几个函数（方法）可以使用。
函数（方法）实例：
下面的例子使用了 Math 对象的 round 方法对一个数进行四舍五入。
document.write(Math.round(4.7))
上面的代码输出为：
5
下面的例子使用了 Math 对象的 random() 方法来返回一个介于 0 和 1 之间的随机数：
document.write(Math.random())
上面的代码输出为：
0.9370844220218102
下面的例子使用了 Math 对象的 floor() 方法和 random() 来返回一个介于 0 和 10 之间的随机数：
document.write(Math.floor(Math.random()*11)) 
上面的代码输出为：
3



RegExp 对象用于规定在文本中检索的内容。
什么是 RegExp？
RegExp 是正则表达式的缩写。
当您检索某个文本时，可以使用一种模式来描述要检索的内容。RegExp 就是这种模式。
简单的模式可以是一个单独的字符。
更复杂的模式包括了更多的字符，并可用于解析、格式检查、替换等等。
您可以规定字符串中的检索位置，以及要检索的字符类型，等等。





JavaScript 库

JavaScript 库 - jQuery、Prototype、MooTools。
JavaScript 框架（库）
JavaScript 高级程序设计（特别是对浏览器差异的复杂处理），通常很困难也很耗时。
为了应对这些调整，许多的 JavaScript (helper) 库应运而生。
这些 JavaScript 库常被称为 JavaScript 框架。
在本教程中，我们将了解到一些广受欢迎的 JavaScript 框架：
jQuery
Prototype
MooTools
所有这些框架都提供针对常见 JavaScript 任务的函数，包括动画、DOM 操作以及 Ajax 处理。
在本教程中，您将学习到如何开始使用它们，来使得 JavaScript 编程更容易、更安全且更有乐趣。
jQuery
jQuery 是目前最受欢迎的 JavaScript 框架。
它使用 CSS 选择器来访问和操作网页上的 HTML 元素（DOM 对象）。
jQuery 同时提供 companion UI（用户界面）和插件。
许多大公司在网站上使用 jQuery：
Google
Microsoft
IBM
Netflix
如需更深入地学习 jQuery，请访问我们的 jQuery 教程。
Prototype
Prototype 是一种库，提供用于执行常见 web 任务的简单 API。
API 是应用程序编程接口（Application Programming Interface）的缩写。它是包含属性和方法的库，用于操作 HTML DOM。
Prototype 通过提供类和继承，实现了对 JavaScript 的增强。
MooTools
MooTools 也是一个框架，提供了可使常见的 JavaScript 编程更为简单的 API。
MooTools 也含有一些轻量级的效果和动画函数。
其他框架
下面是其他一些在上面未涉及的框架：
YUI - Yahoo! User Interface Framework，涵盖大量函数的大型库，从简单的 JavaScript 功能到完整的 internet widget。
Ext JS - 可定制的 widget，用于构建富因特网应用程序（rich Internet applications）。
Dojo - 用于 DOM 操作、事件、widget 等的工具包。
script.aculo.us - 开源的 JavaScript 框架，针对可视效果和界面行为。
UIZE - Widget、AJAX、DOM、模板等等。
CDN - 内容分发网络
您总是希望网页可以尽可能地快。您希望页面的容量尽可能地小，同时您希望浏览器尽可能多地进行缓存。
如果许多不同的网站使用相同的 JavaScript 框架，那么把框架库存放在一个通用的位置供每个网页分享就变得很有意义了。
CDN (Content Delivery Network) 解决了这个问题。CDN 是包含可分享代码库的服务器网络。
Google 为一系列 JavaScript 库提供了免费的 CDN，包括：
jQuery
Prototype
MooTools
Dojo
Yahoo! YUI
如需在您的网页中使用 JavaScript 框架库，只需在 <script> 标签中引用该库即可：
引用 jQuery
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
</script>
使用框架
在您决定为网页使用 JavaScript 框架之前，首先对框架进行测试是明智的。
JavaScript 框架很容易进行测试。您无需在计算机上安装它们，同时也没有安装程序。
通常您只需从网页中引用一个库文件。
在本教程的下一章，我们会为您完整地讲解 jQuery 的测试过程。



jQuery:

测试 JavaScript 框架库 - jQuery
引用 jQuery
如需测试 JavaScript 库，您需要在网页中引用它。
为了引用某个库，请使用 <script> 标签，其 src 属性设置为库的 URL：
引用 jQuery
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
</script>
</head>
<body>
</body>
</html>
jQuery 描述
主要的 jQuery 函数是 $() 函数（jQuery 函数）。如果您向该函数传递 DOM 对象，它会返回 jQuery 对象，带有向其添加的 jQuery 功能。
jQuery 允许您通过 CSS 选择器来选取元素。
在 JavaScript 中，您可以分配一个函数以处理窗口加载事件：
JavaScript 方式：
function myFunction()
{
var obj=document.getElementById("h01");
obj.innerHTML="Hello jQuery";
}
onload=myFunction;
等价的 jQuery 是不同的：
jQuery 方式：
function myFunction()
{
$("#h01").html("Hello jQuery");
}
$(document).ready(myFunction);
上面代码的最后一行，HTML DOM 文档对象被传递到 jQuery ：$(document)。
当您向 jQuery 传递 DOM 对象时，jQuery 会返回以 HTML DOM 对象包装的 jQuery 对象。
jQuery 函数会返回新的 jQuery 对象，其中的 ready() 是一个方法。
由于在 JavaScript 中函数就是变量，因此可以把 myFunction 作为变量传递给 jQuery 的 ready 方法。
提示：jQuery 返回 jQuery 对象，与已传递的 DOM 对象不同。jQuery 对象拥有的属性和方法，与 DOM 对象的不同。您不能在 jQuery 对象上使用 HTML DOM 的属性和方法。
测试 jQuery
例子 1
请试一下下面这个例子：
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
</script>
<script>
function myFunction()
{
$("#h01").html("Hello jQuery")
}
$(document).ready(myFunction);
</script>
</head>

<body>
<h1 id="h01"></h1>
</body>
</html>
亲自试一试
例子 2
请再试一下这个例子：
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/1.8.3/jquery.min.js">
</script>
<script>
function myFunction()
{
$("#h01").attr("style","color:red").html("Hello jQuery")
}
$(document).ready(myFunction);
</script>
</head>

<body>
<h1 id="h01"></h1>
</body>
</html>
亲自试一试
正如您在上面的例子中看到的，jQuery 允许链接（链式语法）。
链接（Chaining）是一种在同一对象上执行多个任务的便捷方法。
需要学习更多内容吗？W3School 为您提供了非常棒的 jQuery 教程。


JavaScript - 测试 Prototype
JS jQuery
JS 实例
测试 JavaScript 框架库 - Prototype
引用 Prototype
如需测试 JavaScript 库，您需要在网页中引用它。
为了引用某个库，请使用 <script> 标签，其 src 属性设置为库的 URL：
引用 Prototype

<!DOCTYPE html>
<html>
<head>
<script src="http://ajax.googleapis.com/ajax/libs/prototype/1.7.1.0/prototype.js>
</script>
</head>
<body>
</body>
</html>
Prototype 描述
Prototype 提供的函数可使 HTML DOM 编程更容易。
与 jQuery 类似，Prototype 也有自己的 $() 函数。
$() 函数接受 HTML DOM 元素的 id 值（或 DOM 元素），并会向 DOM 对象添加新的功能。
与 jQuery 不同，Prototype 没有用以取代 window.onload() 的 ready() 方法。相反，Prototype 会向浏览器及 HTML DOM 添加扩展。
在 JavaScript 中，您可以分配一个函数以处理窗口加载事件：
JavaScript 方式：
function myFunction()
{
var obj=document.getElementById("h01");
obj.innerHTML="Hello Prototype";
}
onload=myFunction;
等价的 Prototype 是不同的：
Prototype 方式：
function myFunction()
{
$("h01").insert("Hello Prototype!");
}
Event.observe(window,"load",myFunction);
Event.observe() 接受三个参数：
您希望处理的 HTML DOM 或 BOM（浏览器对象模型）对象
您希望处理的事件
您希望调用的函数
测试 Prototype
例子 1
请试一下下面这个例子：
<!DOCTYPE html>
<html>
<head>
<script
src="https://ajax.googleapis.com/ajax/libs/prototype/1.7.1.0/prototype.js">
</script>
<script>
function myFunction()
{
$("h01").insert("Hello Prototype!");
}
Event.observe(window,"load",myFunction);
</script>
</head>

<body>
<h1 id="h01"></h1>
</body>
</html>
亲自试一试
例子 2
请再试一下这个例子：
<!DOCTYPE html>
<html>
<head>
<script
src="https://ajax.googleapis.com/ajax/libs/
prototype/1.7.1.0/prototype.js">
</script>
<script>
function myFunction()
{
$("h01").writeAttribute("style","color:red").insert("Hello Prototype!");
}
Event.observe(window,"load",myFunction);
</script>
</head>

<body>
<h1 id="h01"></h1>
</body>
</html>
亲自试一试
正如您在上面的例子中看到的，与 jQuery 相同，Prototype 允许链式语法。
链接（Chaining）是一种在同一对象上执行多个任务的便捷方法。