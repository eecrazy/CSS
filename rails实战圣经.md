Rails的哲学包括以下指导原则：

不要重复自己( DRY: Don't Repeat Yourself ) –撰写出重复的程式码是件坏事
惯例胜于设计( Convention Over Configuration ) – Rails会预设各种好的设定跟惯例，而不是要求你设定每一个细节到设定档中。
REST是网站应用程式的最佳模式–使用Resources和标准的HTTP verbs (动词)来组织你的应用程式是最快的方式(我们会在路径一章详细介绍这个强大的设计)

采用Rails后生产力暴增：写新的应用程式、增加新功能变成容易地多。让你可以用更少程式码做更多的事情，而且程式也更容易维护。当然，学习新工具总是需要时间投资的，一开始可能没办法立刻见效。但是如果你有长期的开发工作，而且网站有一定的复杂性，那么一个短期学习Ruby on Rails的投资，长期来说将会是非常值得的。

Ruby是一套开放原码、物件导向的动态直译式(interpreted)程式语言，它有着简单哲学、高生产力、精巧、自然的语法。他的创造者是来自日本的松本行弘(又名Matz )，设计的灵感来自于Lisp、Perl和Smalltalk，设计的目的是要让程式设计师能够快乐地写程式。

让我们看一个非常简单的范例：

str = "May Ruby be with you!"
5.times { puts str }
这的范例就简单告诉我们有关Ruby的 ​​三件事情了：

动态分型*(typing)*，不需要宣告型态
每样东西都是物件，包括数字
匿名函式*(code block)*随处可见

著名的”人月神话”一书作者Fred Brooks曾说：「一个程式设计师一天能产生的程式码行数是差不多的，无论什么程式语言」。因此一个具有表达能力的高阶程式语言，就会比低阶的程式语言能完成更多功能。相较于静态程式语言，使用更高阶的动态脚本语言可以帮助我们：

1. 用更少程式码做更多事情，大大增加生产力2. 更快因应客户开发需求，敏捷开发

不过，动态语言也不是没有缺点：

1. 执行效能是绝对比不上静态语言的2. 没有编译期可以检查型别错误

在硬体资源有限的行动装置及嵌入式系统上，仍是静态语言的天下，这一点需要更多时间才有动态语言的生存空间。

没有编译期可以检查型别错误的问题，也随着单元测试和TDD(Test-driven development)测试驱动开发等敏捷最佳实务而逐渐降低重要性。而大部分的Bug会出自于商业逻辑错误，而不是型别错误上。

为何选择Ruby？

Ruby是一套非常重视使用性( Usability )的物件导向程式语言，非常看重程式码的可读性及维护性。Matz在设计Ruby时，就特别考量一般人容不容易了解(他说我们都是凡人，像Lisp是给神人用的)。这也是为什么你常常会听到Ruby的 ​​程式码自然简洁又漂亮。

Ruby也是目前做Domain-specific language(DSL)，特别是Internal DSL最为成功的程式语言。透过DSL，程式不但可以拥有非常好的可读性，也可以大幅增加生产力。成功的DSL函式库例如有：Rake建构工具、RSpec测试工具、Chef伺服器设定工具、Cucumber验收测试等。这些函式库正积极地影响我们对软体开发的想法。我们相信，还会有更多更有趣的DSL函式库出现。

CRUD指的是Create (新增)、Read (读取)、Update (更新)、Delete (删除)四种操作资料的基本方式。

$ cd demo
这个目录下包含了一个Rails专案基本会用到的目录结构和档案，让我们简单走访一下，输入ls (Windows读者请输入dir)显示出此目录下的档案：

档案/目录	用途
Gemfile	设定Rails应用程式会使用哪些Gems套件
README	专案说明：你可以用来告诉其他人你的应用程式是做什么用的，如何使用等等。
Rakefile	用来载入可以被命令列执行的一些Rake任务
app/	放Controllers、Models和Views档案，接下来的内容主要都在这个目录。
config/	应用程式设定档、路由规则、资料库设定等等
config.ru	用来启动应用程式的Rack伺服器设定档
db/	资料库的结构纲要
doc/	用来放你的文件
lib/	放一些自定的Module和类别档案
log/	应用程式的Log记录档
public/	唯一可以在网路上看到的目录，这是你的图档、JavaScript、CSS和其他静态档案摆放的地方
script/	放rails这个指令和放其他的script指令
test/	单元测试、fixtures及整合测试等程式
tmp/	暂时性的档案
vendor/	用来放第三方程式码外挂的目录

启动伺服器
Rails使用了一套叫做Bundler的工具可以帮助我们检查及安装这个Rails应用程式所有依存的套件，请输入：
$ bundle install
可以只输入bundle就是bundle install了。每次有修改Gemfile这个档案，都需要重新执行bundle

rails server 可以简写为rails s

使用Ubuntu作业系统的朋友，如果启动伺服器时出现Could not find a JavaScript runtime的错误，请编辑Gemfile这个档案加上一行gem 'therubyracer'，输入bundle install安装这个套件，然后再启动一次rails server即可。这是因为在Ubuntu作业系统上预设没有任何JavaScript直译器可以给Rails使用。你可以装Node.js或是安装therubyracer这个Ruby套件来获得JavaScript直译器。

要中断伺服器的话，请按Ctrl+C (若不灵光请改试Ctrl+Z )。在development开发模式的话，除了修改config或vender目录下的档案需要重新启动之外，其他修改通常不需要重新启动，修改的档案会自动重新载入。如果是production正式上线模式的话，修改任何档案都必须重新启动伺服器才会有效果。

<%和<%=不太一样，前者只执行不输出，像用来迭代的each和end这两行就不需要输出。而后者<%=里的结果会输出给浏览器。