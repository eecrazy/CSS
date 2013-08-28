与第二版的差异
下面的列表列出了本书和第二版之间几乎所有的差异。（最重要的一个差异是，使用了“健壮参数”，其他都是小变动。）我列出这个列表是为了方便第二版的读者（或者熟悉 Rails 3.2 的读者）快速查看两版的不同之处。如果你没用过 Rails 3.2 请忽略这个列表。

列表的每一项后面都有一个链接，指向变动所在的章节或代码。

从 Rails 3.2 升级到 Rails 4.0（1.2.2 节）
显式引入 Capybara DSL（代码 3.10）
把 RSpec 的 .should 句法换成了 expect().to（3.2.1 节）
把 have_selector('title', ...) 换成了 have_title(...)（3.3.1 节）
更新操作所用的 HTTP 请求从 PUT 换成了 PATCH（旁注 3.3）
引入样式表和 JavaScript 脚本时指定了针对 Turbolinks 的参数（代码 3.26）
把 root to: 'path' 换成了 root 'path'（代码 5.24）
把 find_by_thing(...) 换成了 find_by(thing: ...)（6.1.4 节）
把 rake db:test:prepare 命令换成了 rake test:prepare（6.2.1 节）
撤掉 attr_accessible，换用“健壮参数”（7.3.2 节）
换用加密的记忆权标（8.2.1 节）
把 before_filter 换成了 before_action（代码 9.21）
使用 Capybara 的 match: :first 参数点击第一个匹配的链接（代码 9.43）
把 default_scope 的参数从 Hash 换成了 lambda（代码 10.11）
把 dup 换成了 to_a 方法（代码 10.12）
使用 XPath 测试按钮的状态变化（11.2.4 节）


Rails 是最早实现 REST 这个 Web 程序架构体系的框架之一
“使用 Google 搜索错误信息”的方法几乎总能搜到一篇相关的博客文章或讨论组的话题。
推荐你在 Try Ruby 上学习一些短小的交互式教程，然后还可以看一下 Rails for Zombies 这个免费的视频教程，看看 Rails 都能做些什么。
本书会使用“测试驱动开发（也叫“先测试后开发”）”理念，我认为这是使用 Rails 进行 Web 开发最好的方式，但这样也会增加难度和复杂度
Ryan Bates 的 RailsCasts：我是不是已经说过 RailsCasts了？真的，强烈推荐 RailsCasts。
性能是要在你的网站中优化，而不是在框架中，强大的 Rails 只是一个框架而已
在 Unix 系统中，一些命令要使用 sudo（超级用户的工作，“substitute user do”）执行

如果你在使用 RVM 时遇到了问题，可以运行以下的命令显示帮助信息：
$ rvm help
$ rvm gemset help

rails new first_app

文件/文件夹	说明
app/	程序的核心文件，包含模型、视图、控制器和帮助方法
app/assets	程序的资源文件，如 CSS、JavaScript 和图片
bin/	可执行文件
config/	程序的设置
db/	数据库文件


doc/	程序的文档
lib/	代码库文件
lib/assets	代码库包含的资源文件，如 CSS、JavaScript 和 图片
log/	程序的日志文件
public/	公共（例如浏览器）可访问的数据，如出错页面
script/rails	生成代码、打开终端会话或开启本地服务器的脚本
test/	程序的测试文件（在 3.1.2 节 中换用 spec/）
tmp/	临时文件
vendor/	第三方代码，如插件和 gem
vendor/assets	第三方代码包含的资源文件，如 CSS、JavaScript 和图片
README.rdoc	程序简介
Rakefile	rake 命令包含的任务
Gemfile	该程序所需的 gem
Gemfile.lock	一个 gem 的列表，确保本程序的复制版使用相同版本的 gem
config.ru	Rack 中间件的配置文件
.gitignore	git 忽略的文件类型


如果不为 gem 命令指定一个版本号，Bundler 会自动安装 gem 的最新版本

换句话说，>= 总会升级到最新版；~> 4.0.0 只会升级补丁版本的更新（例如从 4.0.0 到 4.0.1），而不会升级到次版本或主版本的更新（例如从 4.0 到 4.1）。不过，经验告诉我们，即使是补丁版本的升级也可能会产生错误，所以在本教程中我们基本上会为所有的 gem 指定明确的版本号。你可以使用任何 gem 的最新版本，还可以在 Gemfile 中使用 ~>（推荐高级用户使用），但我事先提醒你，这可能会导致本教程开发的程序表现异常。

使用Ubuntu作业系统的朋友，如果启动伺服器时出现Could not find a JavaScript runtime的错误，请编辑Gemfile这个档案加上一行gem 'therubyracer'，输入bundle install安装这个套件，然后再启动一次rails server即可。这是因为在Ubuntu作业系统上预设没有任何JavaScript直译器可以给Rails使用。你可以装Node.js或是安装therubyracer这个Ruby套件来获得JavaScript直译器。

你可能已经注意到了，在 Rails 应用程序的文件结构（如图 1.2）中有一个文件夹叫 app/，其中有三个子文件夹：models、views 和 controllers。这暗示 Rails 采用了 MVC 架构模式，这种模式强制地将“域逻辑（domain logic）”（也叫“业务逻辑（business logic）”）和图形用户界面（GUI）的输入、表现逻辑分开。在 Web 应用程序中，“域逻辑”的典型代表是“用户（users）”、“文章（articles）”和“产品（products）”等数据模型，GUI 则是浏览器中的网页

在 Rails 交互中，浏览器发送一个请求（request），网络服务器收到请求将其传送到 Rails 的控制器，然后决定下一步做什么。某些情况下，控制器会立即渲染视图（view）模板，生成 HTML 然后将结果发送回浏览器。对于动态网站来说，控制器会和模型（model）交互。模型是一个 Ruby 对象，表示网站中的一个元素（例如一个用户），并且负责和数据库通信。调用模型后，控制器再渲染视图并将生成的 HTML 代码返回给浏览器。

我们用 Unix 中的 ls 命令列出 app/controllers/ 文件夹中的内容，用 rm 命令删除这个文件夹。旗标 -rf 的意思是“强制递归”，无需得到确认就递归的删除所有文件、文件夹、子文件夹等。

我们就可以使用 checkout 命令切换到前一个提交记录来撤销这次改动（其中旗标 -f 意思是覆盖当前的改动）：

$ git checkout -f
$ git status

git branch，会将本地所有的分支列出来，分支名前面的星号（*）指明当前所在的分支。注意，git checkout -b modify-README 会创建一个新分支，然后切换到这个分支，modify-README 前面的星号证明了这一点

使用 git branch -d 删除这个从分支：

$ git branch -d modify-README

在开发过程中尽早、频繁的部署可以尽早的发现开发中的问题。在开发环境中极力解决问题之后再部署,等到发布日期到来时经常会导致严重的问题


bundle install --without production
指定 --without production 后本地环境就不会安装生产环境所需的 gem 了，对本例来说就只有 pg 一个 gem。（如果 Bundler 显示一个 readline 相关的错误，请把 gem rb-readline 加入 Gemfile。）因为我们添加的 gem 只针对生产环境，所以现在执行这个命令不会在本地安装任何 gem，但这一步却是必须的，因为我们要把 pg 和 Ruby 版本更新到 Gemfile.lock 中，这样 Heroku 才知道应用程序要使用的 Ruby 版本

git commit -a -m "Update Gemfile.lock for Heroku"

使用这样随机的域名，只有你将地址告诉别人他们才能访问你的网站。（顺便说一下，让你一窥 Ruby 的强大，以下是我用来生成随机域名的代码，很精妙吧。）

('a'..'z').to_a.shuffle[0..7].join

除了支持子域名，Heroku 也支持自定义域名。（事实上本书的网站20就放在 Heroku 上。如果你阅读的是本书的在线版，你现在就正在浏览一个托管在 Heroku 上的网站。）在 Heroku 文档 中可以查看更多关于自定义域名的信息以及其他 Heroku 相关的话题。

可以运行 rake -T db 来查看所有和数据库有关的任务：

$ bundle exec rake -T db
如果要查看所有的 Rake 任务，运行

$ bundle exec rake -T


HTTP 请求	URL	动作	目的
GET	/users	index	显示所用用户的页面
GET	/users/1	show	显示 ID 为 1 的用户页面
GET	/users/new	new	创建新用户的页面
POST	/users	create	创建新用户
GET	/users/1/edit	edit	编辑 ID 为 1 的用户页面
PATCH	/users/1	update	更新 ID 为 1 的用户
DELETE	/users/1	destroy	删除 ID 为 1 的用户

脚手架生成的 Users 资源相关代码虽然能够让你大致的了解一下 Rails，不过它也有一些缺陷：

没有对数据进行验证（validation）。User 模型会接受空的名字和不合法的 Email 地址而不会报错。
没有用户身份验证机制（authentication）。没有实现登录和退出功能，随意一个用户都可以进行任何的操作。
没有测试。也不是完全没有，脚手架会生成一些基本的测试，不过很粗糙也不灵便，没有对数据进行验证，不包含验证机制的测试，以及其他的需求。
没有布局。没有共用的样式和网站导航。
没有真正的被理解。如果你能读懂脚手架生成的代码就不需要阅读本书了。


HTTP 请求	URL	动作	目的
GET	/microposts	index	显示所有微博的页面
GET	/microposts/1	show	显示 ID 为 1 的微博页面
GET	/microposts/new	new	显示创建新微博的页面
POST	/microposts	create	创建新微博
GET	/microposts/1/edit	edit	编辑 ID 为 1 的微博页面
PATCH	/microposts/1	update	更新 ID 为 1 的微博
DELETE	/microposts/1	destroy	删除 ID 为 1 的微博

2.4 小结

现在我们已经结束了对一个 Rails 应用程序的分析，本章中开发的演示程序有一些好的地方也有一些有缺陷的地方。

好的地方

概览了 Rails
介绍了 MVC
第一次体验了 REST 架构
开始使用数据模型了
在生产环境中运行了一个基于数据库的 Web 程序
有缺陷的地方

没有自定义布局和样式
没有静态页面（例如“首页”和“关于”）
没有用户密码
没有用户头像
没登录功能
不安全
没实现用户和微博的自动关联
没实现“关注”和“被关注”功能
没实现动态列表
没使用 TDD
没有真的理解所做的事情
本书后续的内容会建立在这些好的部分之上，然后改善有缺陷的部分。


虽然 Rails 是被设计用来开发基于数据库的动态网站的，不过它也能胜任使用纯 HTML 创建的静态页面。其实，使用 Rails 创建动态页面还有一点好处：我们可以方便的添加一小部分动态内容。这一章就会教你怎么做。在这个过程中我们还会一窥自动化测试（automated testing）的面目，自动化测试可以让我们确信自己编写的代码是正确的。而且，编写一个好的测试用例还可以让我们信心十足的重构（refactor）代码，修改实现过程但不影响最终效果。

你还可以考虑学习 Code School 的 RSpec 课程，有为读者说这个课程解惑了很多 RSpec 疑问


因为我们会公开分享这个示例程序的源码，所以一定要修改“安全权标”。Rails 使用安全权标来加密会话。我们要把硬编码的字符串改为动态生成的（如代码 3.2）。（代码 3.2 中的代码现在看来是很高级的，但这是一个很严重的安全隐患，所以我觉得有必要尽早加入这段代码。）请确保使用了代码 1.7 所示的 .gitignore 文件，不把 .secret 纳入仓库。

代码 3.2：动态生成安全权标
config/initializers/secret_token.rb

接着我们要设置一下让 Rails 使用 RSpec 而不用 Test::Unit。这个设置可以通过 rails generate rspec:install 命令实现：

$ rails generate rspec:install


和第一个程序一样，我建议你更新一下 README 文件，更好的描述这个程序，还可以提供一些帮助信息，可参照代码 3.3。

代码 3.3：示例程序改善后的 README 文件
# Ruby on Rails Tutorial: sample application

This is the sample application for
the [*Ruby on Rails Tutorial*](http://railstutorial.org/)
by [Michael Hartl](http://michaelhartl.com/).
然后添加 .md 后缀将其更改为 Markdown 格式，再提交所做的修改：

$ git mv README.rdoc README.md
$ git commit -am "Improve the README"


当然我们也可以选择在这个早期阶段将程序部署到 Heroku：

$ heroku create
$ git push heroku master
$ heroku run rake db:migrate
在阅读本书的过程中，我建议你经常地推送并部署这个程序：

$ git push
$ git push heroku
$ heroku run rake db:migrate

这样你可在远端做个备份，也可以尽早的获知生成环境中出现的错误。如果你在 Heroku 遇到了问题，可以看一下生产环境的日志文件尝试解决：

$ heroku logs

在开始之前，如果使用 Git，最好别在主分支上开发，要新建一个从分支。如果你正使用 Git 做版本控制，应该执行下面的命令：

$ git checkout -b static-pages


我们使用了 --no-test-framework 选项禁止生成 RSpec 测试代码，因为我们不想自动生成，在 3.2 节会手动创建测试。同时我们还故意从命令行参数中省去了 about 动作，稍后我们会看到如何通过 TDD 添加它（3.2 节）。



注意，在代码 3.4 中，传入命令的控制器名使用的是驼峰式命名法，生成的控制器文件名使用的是蛇底式命名法，因此名为 StaticPages 的控制器对应的文件名为 static_pages_controller.rb。这只是一个约定，其实在命令行中使用蛇底式也可以，如下的命令

$ rails generate controller static_pages ...

同样会生成 static_pages_controller.rb 控制器文件。因为 Ruby 开发者使用驼峰式命名类名（参见 4.4 节），所以我喜欢用驼峰式引用控制器，当然这是个人喜好的问题。（因为 Ruby 文件习惯使用蛇底式名称，所以 Rails 生成器会调用 underscore 方法把驼峰式转换成蛇底式。）

顺便说一下，如果在生成代码时出现了错误，知道如何撤销操作就很有用了。旁注 3.2 中介绍了一些如何在 Rails 中撤销操作的方法。



旁注 3.2：撤销操作
即使再小心，在开发 Rails 应用程序过程中仍然可能犯错。幸运的是，Rails 提供了一些工具能够帮助你进行复原。

举例来说，一个常见的情况是，你想更改控制器的名字，这时你就要撤销生成的代码。生成控制器时，除了控制器文件本身之外，Rails 还会生成很多其他的文件（参见代码 3.4）。撤销生成的文件不仅仅要删除主要的文件，还要删除一些辅助的文件。（事实上，我们还要撤销对 routes.rb 文件自动做的一些改动。）在 Rails 中，我们可以通过 rails destroy 命令完成这些操作。一般来说，下面的两个命令是相互抵消的：

$ rails generate controller FooBars baz quux
$ rails destroy  controller FooBars baz quux
同样的，在第 6 章中会使用下面的命令生成模型：

$ rails generate model Foo bar:string baz:integer
生成的模型可通过下面的命令撤销：

$ rails destroy model Foo
（对模型来说我们可以省略命令行中其余的参数。当阅读到第六章时，看看你能否发现为什么可以这么做。）

对模型来说涉及到的另一个技术是撤销迁移。第 2 章已经简要的介绍了迁移，第 6 章开始会更深入的介绍。迁移通过下面的命令改变数据库的状态：

$ rake db:migrate
我们可以使用下面的命令撤销一个迁移操作：

$ rake db:rollback
如果要回到最开始的状态，可以使用：

$ rake db:migrate VERSION=0
你可能已经猜到了，将数字 0 换成其他的数字就会回到相应的版本状态，这些版本数字是按照迁移顺序排序的。

拥有这些技术，我们就可以得心的应对开发过程中遇到的各种混乱（snafu）了。


将来自 /static_pages/home 的请求映射到 StaticPages 控制器的 home 动作上。另外，当使用 get 时会将其对应到 GET 请求方法上，GET 是 HTTP（超文本传输协议，Hypertext Transfer Protocol）支持的基本方法之一（参见旁注 3.3）。在我们这个例子中，当我们在 StaticPages 控制器中生成 home 动作时，就自动的在 /static_pages/home 地址上获得了一个页面。访问 /static_pages/home 可以查看这个页面


旁注 3.3：GET 等
超文本传输协议（HTTP）定义了几个基本操作，GET、POST、PATCH 和 DELETE。这四个动词表现了客户端电脑（通常会运行一个浏览器，例如 Firefox 或 Safari）和服务器（通常会运行一个 Web 服务器，例如 Apache 或 Nginx）之间的操作。（有一点很重要需要你知道，当在本地电脑上开发 Rails 应用程序时，客户端和服务器是在同一个物理设备上的，但是二者是不同的概念。）受 REST 架构影响的 Web 框架（包括 Rails）都很重视对 HTTP 动词的实现，我们在第 2 章已经简要介绍了 REST，从第 7 章开始会做更详细的介绍。

GET 是最常用的 HTTP 操作，用来从网络上读取数据，它的意思是“读取一个网页”，当你访问 google.com 或 wikipedia.org 时，你的浏览器发出的就是 GET 请求。POST 是第二种最常用的操作，当你提交表单时浏览器发送的就是 POST 请求。在 Rails 应用程序中，POST 请求一般被用来创建某个东西（不过 HTTP 也允许 POST 进行更新操作）。例如，你提交注册表单时发送的 POST 请求就会在网站中创建一个新用户。剩下的两个动词，PATCH 和 DELETE 分别用来更新和销毁服务器上的某个东西。这两个操作比 GET 和 POST 少用一些，因为浏览器没有内建对这两种请求的支持，不过有些 Web 框架（包括 Rails）通过一些聪明的处理方式，看起来就像是浏览器发出的一样。

顺便说一下，在 Rails 之前的版本中，没有使用 PATCH，用的是 PUT，Rails 4 仍然支持 PUT，但 PATCH 能更好的表明 HTTP 请求的意图，所以最好在新版中使用 PATCH。

如果是普通的 Ruby 代码，这两个方法什么也做不了。不过在 Rails 中就不一样了，StaticPagesController 是一个 Ruby 类，因为它继承自 ApplicationController，它的方法对 Rails 来说就有特殊的意义了：访问 /static_pages/home 时，Rails 在 StaticPages 控制器中寻找 home 动作，然后执行该动作，再渲染相应的视图（1.2.6 节中介绍的 MVC 中的 V）。在本例中，home 动作是空的，所以访问 /static_pages/home 后只会渲染视图。那么，视图是什么样子，怎么才能找到它呢？

如果你再看一下代码 3.4 的输出，或许你能猜到动作和视图之间的对应关系：home 动作对应的视图叫做 home.html.erb。3.3 节将告诉你 .erb 是什么意思。看到 .html 你或许就不会奇怪了，它基本上就是 HTML（代码 3.7）。

代码 3.7：为“首页”生成的视图
app/views/static_pages/home.html.erb

<h1>StaticPages#home</h1>
<p>Find me in app/views/static_pages/home.html.erb</p>

这些静态内容的存在是为了强调一个很重要的事情：Rails 的视图可以只包含静态的 HTML。

在本章剩下的内容中，我们会为“首页”和“帮助”页面添加一些内容，然后补上 3.1 节中丢下的“关于”页面。然后会添加少量的动态内容，在每个页面显示不同的标题。

在继续下面的内容之前，如果你使用 Git 的话最好将 StaticPages 控制器相关的文件加入仓库：

3.2 第一个测试

本书采用了一种直观的测试应用程序表现的方法，而不关注具体的实现过程，这是 TDD 的一个变种，叫做 BDD（行为驱动开发，Behavior-driven Development）。我们使用的主要工具是集成测试（integration test）和单元测试(unit test)。集成测试在 RSpec 中叫做 request spec，它允许我们模拟用户在浏览器中和应用程序进行交互的操作。和 Capybara 提供的自然语言句法（natural-language syntax）一起使用，集成测试提供了一种强大的方法来测试应用程序的功能，而不用在浏览器中手动检查每个页面。（BDD 另外一个受欢迎的选择是 Cucumber，在 8.3 节中会介绍。）

TDD 的好处在于测试优先，比编写应用程序的代码还早。刚接触的话要花一段时间才能适应这种方式，不过好处很明显。我们先写一个失败测试（failing test），然后编写代码使这个测试通过，这样我们就会相信测试真的是针对我们设想的功能。这种“失败-实现-通过”的开发循环包含了一个心流，可以提高编程的乐趣并提高效率。测试还扮演着应用程序代码客户的角色，会提高软件设计的优雅性。

关于 TDD 有一点很重要需要你知道，它不是万用良药，没必要固执的认为总是要先写测试、测试要囊括程序所有的功能、所有情况都要写测试。例如，当你不确定如何处理某些编程问题时，通常推荐你跳过测试先编写代码看一下解决方法能否解决问题。（在极限编程中，这个过程叫做“探针实验（spike）”。）一旦看到了解决问题的曙光，你就可以使用 TDD 实现一个更完美的版本。

本节我们会使用 RSpec 提供的 rspec 命令运行测试。初看起来这样做是理所当然的，不过却不完美，如果你是个高级用户我建议你按照 3.6 节的内容设置一下你的系统。


3.2.1 测试驱动开发

在测试驱动开发中，我们先写一个会失败的测试，在很多测试工具中会将其显示为红色。然后编写代码让测试通过，显示为绿色。最后，如果需要的话，我们还会重构代码，改变实现的方式（例如消除代码重复）但不改变功能。这样的开发过程叫做“遇红，变绿，重构（Red, Green, Refactor）”。

我们先来使用 TDD 为“首页”增加一些内容，一个内容为 Sample App 的顶级标题（<h1>）。第一步要做的是为这些静态页面生成集成测试（request spec）：

$ rails generate integration_test static_pages
      invoke  rspec
      create    spec/requests/static_pages_spec.rb

3.2.2 添加页面

看过了上面简单的 TDD 开发过程，下面我们要用这个技术完成一个稍微复杂一些的任务，添加一个新页面，就是 3.1 节中没有生成的“关于”页面。通过每一步中编写测试和运行 RSpec 的过程，我们会看到 TDD 是如何引导我们进行应用程序开发的。


重构

现在测试已经变绿了，我们可以很自信的尽情重构了。我们的代码经常会“变味”（意思是代码会变得丑陋、啰嗦、大量的重复），电脑不会在意，但是人类会，所以经常重构让代码变得简洁是很重要的。这时候一个好的测试就显出其价值了，因为它可以降低重构过程中引入 bug 的风险。

我们的示例程序现在还很小没什么可重构的，不过代码无时无刻不在变味，所以我们的重构也不会等很久：在 3.3.4 节中就要忙于重构了。

3.3.1 测试标题的变化

我们计划修改“首页”、“帮助”页面和“关于”页面的标题，在每一页都有所变化。这个过程将使用视图中的 <title> 标签。大多数浏览器会在浏览器窗口的顶部显示标题的内容（Google Chrome 是个特例），标题对搜索引擎优化也是很重要的。我们会先写测试标题的代码，然后添加标题，最后使用布局（layout）文件进行重构，削除重复。


页面	URL	基本标题	变动部分
首页	/static_pages/home	"Ruby on Rails Tutorial Sample App"	"Home"
帮助	/static_pages/help	"Ruby on Rails Tutorial Sample App"	"Help"
关于	/static_pages/about	"Ruby on Rails Tutorial Sample App"	"About"
我们按照代码 3.18 的格式为三个静态页面都加上测试代码，结果参照代码 3.19。注意，测试中有很多重复，我们会在 5.3.4 节重构。

3.3.3 嵌入式 Ruby

本节到目前为止已经做了很多事情，我们通过 Rails 控制器和动作生成了三个可以通过句法验证的页面，不过这些页面都是纯静态的 HTML，没有体现出 Rails 的强大所在。而且，它们的代码充斥着重复：

页面的标签几乎（但不完全）是一模一样的
每个标题中都有“Ruby on Rails Tutorial Sample App”
HTML 结构在每个页面都重复的出现了

代码重复的问题违反了很重要的“不要自我重复”（Don’t Repeat Yourself, DRY）原则，本小节和下一小节将按照 DRY 原则去掉重复的代码。

不过我们去除重复的第一步却是要增加一些代码让页面的标题看起来是一样的。这样我们就可以更容易的去掉重复的代码了。

这个过程会在视图中使用嵌入式 Ruby（Embedded Ruby）。既然“首页”、“帮助”页面和“关于”页面的标题有一个变动的部分，那我们就利用一个 Rails 中特别的函数 provide 在每个页面设定不同的标题。通过将视图 home.html.erb 标题中的“Home”换成如代码 3.23 所示的代码，我们可以看一下实现的过程。

我们第一次使用了嵌入式 Ruby，简称 ERb。（现在你应该知道为什么 HTML 视图文件的扩展名是 .html.erb 了。）ERb 是为网页添加动态内容使用的主要模板系统

还要注意一下，默认的 Rails 布局文件包含几行特殊的代码：

<%= stylesheet_link_tag ... %>
<%= javascript_include_tag "application", ... %>
<%= csrf_meta_tags %>
这些代码会引入应用程序的样式表和 JavaScript 文件（asset pipeline 的一部分）；Rails 中的 csrf_meta_tags 方法是用来避免“跨站请求伪造”（cross-site request forgery，CSRF，一种网络攻击）的。

其实还有另外一个受欢迎的模板系统叫 Haml，我个人很喜欢用，不过在这样的初级教程中使用不太合适。↩

如果要成为一个 Rails 专家，你就要更深入的掌握 Ruby 了。本书会为你在成为专家的路途上奠定一个坚实的基础。如 1.1.1 节中说过的，读完本书后我建议你阅读一本专门针对 Ruby 的书，例如《Ruby 入门》、《The Well-Grounded Rubyist》或《Ruby 之道》。

注意，上面的方法都没有修改 a 的值。如果你想修改数组的值要使用对应的“炸弹（bang）”方法（之所以这么叫是因为这里的感叹号经常都读作“bang”）：

>> a
=> [42, 8, 17]
>> a.sort!
=> [8, 17, 42]
>> a
=> [8, 17, 42]
你还可以使用 push 方法向数组中添加元素，或者使用等价的 << 操作符：

>> a.push(6)                  # 把 6 加到数组结尾
=> [42, 8, 17, 6]

前面我们用 split 把字符串分割成字符串，我们还可以使用 join 方法进行相反的操作：

>> a
=> [42, 8, 17, 7, "foo", "bar"]
>> a.join                       # 没有连接符
=> "428177foobar"
>> a.join(', ')                 # 连接符是一个逗号和空格
=> "42, 8, 17, 7, foo, bar"

虽然 0..9 是一个合法的 Range，不过上面第二个表达式告诉我们调用方法时要加上括号。

Range 经常被用来获取一组数组元素：

>> a = %w[foo bar baz quux]         # %w 创建一个元素为字符串的数组
=> ["foo", "bar", "baz", "quux"]
>> a[0..2]
=> ["foo", "bar", "baz"]
Range 也可使用字母：

>> ('a'..'e').to_a
=> ["a", "b", "c", "d", "e"]

块可以多于一行，也经常是多于一行的。本书中我们会遵照一个常用的约定，当块只有一行简单的代码时使用花括号形式；当块是一行很长的代码，或者多行时使用 do..end 形式：
>> (1..5).each do |number|
?>   puts 2 * number
>>   puts '--'
>> end

上面的代码用 number 代替了 i，我想告诉你的是任何变量名都可以使用。

>> 3.times { puts "Betelgeuse!" }   # 3.times 后跟的块没有变量
"Betelgeuse!"
"Betelgeuse!"
"Betelgeuse!"
=> 3
>> (1..5).map { |i| i**2 }          # ** 表示幂
=> [1, 4, 9, 16, 25]
>> %w[a b c]                        # 再说一下，%w 可以创建元素为字符串的数组
=> ["a", "b", "c"]
>> %w[a b c].map { |char| char.upcase }
=> ["A", "B", "C"]
>> %w[A B C].map { |char| char.downcase }
=> ["a", "b", "c"]

上面的代码说明，map 方法返回的是在数组或 Range 的每个元素上执行块中代码后的结果。
('a'..'z').to_a.shuffle[0..7].join

目前为止我们的键用的都是字符串，但在 Rails 中用 Symbol 当键却很常见。Symbol 看起来像字符串，只不过没有包含在一对引号中，而是在前面加一个冒号。例如，:name 就是一个 Symbol。你可以把 Symbol 看成没有约束的字符串：9

Symbol 是 Ruby 特有的一个数据类型，其他语言很少用到，初看起来感觉很奇怪，不过 Rails 经常用到它，所以你很快就会习惯的。

第二个命令把 hashrocket 形式的键值对变成了键后跟着一个冒号然后再跟着一个值的形式：

这种结构更好的沿袭了其他语言（例如 JavaScript）中 Hash 的表现方式，在 Rails 社区中也越来越受欢迎。这两种方式现在都在使用，所以你要能识别它们。
这种 Hash 中有 Hash 的形式（或称为 Hash 嵌套）在 Rails 中大量的使用


与数组和 Range 一样，Hash 也可以响应 each 方法。例如，一个名为 flash 的 Hash，它的键是两个条件判断，:success 和 :error：

>> flash = { success: "It worked!", error: "It failed." }
=> {:success=>"It worked!", :error=>"It failed."}
>> flash.each do |key, value|
?>   puts "Key #{key.inspect} has value #{value.inspect}"
>> end
Key :success has value "It worked!"
Key :error has value "It failed."

注意，数组的 each 方法后面的块只有一个变量，而 Hash 的 each 后面的块接受两个变量，key 和 value。所以 Hash 的 each 方法每次遍历都会以一个键值对为基本单位进行。

>> puts (1..5).to_a.inspect    # 输出一个数组字面量形式
[1, 2, 3, 4, 5]
>> puts :name, :name.inspect
name
:name
>> puts "It worked!", "It worked!".inspect
It worked!
"It worked!"
顺便说一下，因为使用 inspect 输出对象的方式经常使用，为此还有一个专门的快捷方式，p 方法：

>> p :name             # 等价于 puts :name.inspect
:name


<%= stylesheet_link_tag "application", media: "all",
                                       "data-turbolinks-track" => true %>
我们现在基本上可以理解这行代码了。在 4.1 节中简单的提到过，Rails 定义了一个特殊的函数用来引入样式表，下面的代码

stylesheet_link_tag "application", media: "all",
                                   "data-turbolinks-track" => true
就是对这个函数的调用。不过还有几个奇怪的地方。第一，括号哪儿去了？因为在 Ruby 中，括号是可以省略的，下面的两行代码是等价的：

# Parentheses on function calls are optional.
stylesheet_link_tag("application", media: "all",
                                   "data-turbolinks-track" => true)
stylesheet_link_tag "application", media: "all",
                                   "data-turbolinks-track" => true

还有，为什么 data-turbolinks-track 这个键值对使用旧句法？因为如果是新新句法，写成

data-turbolinks-track: true
就会尝试创建一个 Symbol :data-turbolinks-track，但是因为包含了连字符，所以这个 Symbol 是不合法的。所以就只能使用旧句法，写成

"data-turbolinks-track" => true
最后，为什么下面这两行代码

stylesheet_link_tag "application", media: "all",
                                   "data-turbolinks-track" => true
为什么可以这么写，中间有空格也可以？当然可以，Ruby 不关心有没有换行。[^1-10]我之所以把代码拆成两行，是要保持每行代码不超过 80 列。[^1-11]

所以我们就看到了这样一行代码

stylesheet_link_tag "application", media: "all",
                                   "data-turbolinks-track" => true


它调用了 stylesheet_link_tag 函数，传进两个参数：一个是字符串，指明样式表的路径；另一个是 Hash，包含两个元素，指明媒介类型，并启用 Turbolink 功能(Rails 4 的新功能，本书的后续草稿会深入介绍)。因为使用的是 <%= %>，函数的执行结果会通过 ERb 插入模板中，如果你在浏览器中查看网页的源代码就会看到引入样式表所用的 HTML（参见代码 4.7）。（你可能会在 CSS 的文件名后看到额外的字符，例如 ?body=1。这是 Rails 加入的，可以确保 CSS 修改后浏览器会重新加载它。）

代码 4.7：引入 CSS 的代码生成的 HTML
<link data-turbolinks-track="true" href="/assets/application.css" media="all"
rel="stylesheet" />
如果你打开 http://localhost:3000/assets/application.css 查看 CSS 的话，会发现是空的（除了一些注释）。在第 5 章中我们会看介绍如何添加样式。

4.4.3 修改内置的类

虽然继承是个很强大的功能，不过在回文判断的例子中，如果能把 palindrome? 加入 String 类就更好了，这样（除了其他对象外）我们就可以在字符串字面量上调用 palindrome? 方法了。现在我们还不能直接调用：

>> "level".palindrome?
NoMethodError: undefined method `palindrome?\' for "level":String
有点令人惊讶的是，Ruby 允许你这么做，Ruby 中的类可以被打开进行修改，允许像我们自己这样的普通人添加一些方法：12

>> class String
>>   # 如果字符串和自己反转后相等则返回 true
>>   def palindrome?
>>     self == self.reverse
>>   end
>> end
=> nil
>> "deified".palindrome?
=> true

（我不知道哪一个更牛：Ruby 允许向内置的类中添加方法，或“deified（神化，奉为神明）”是个回文。）

可以修改内置的类是个很强大的功能，不过功能强大意味着责任也大，如果没有一个很好的理由，向内置的类中添加方法被认为是不好的习惯。Rails 自然有很好的理由，例如，在 Web 应用程序中我们经常要避免变量是空白（blank）的，像用户名之类的就不应该是空格或空白，所以 Rails 为 Ruby 添加了一个 blank? 方法。因为 Rails 控制台会自动加载 Rails 添加的扩展功能，我们可以看一下示例（在 irb 就不可以）：

>> "".blank?
=> true
>> "      ".empty?
=> false
>> "      ".blank?
=> true
>> nil.blank?
=> true
我们可以看到，一个包含空格的字符串不是空的（empty），却是空白的（blank）。还要注意，nil 也是空白的。因为 nil 不是字符串，所以上面的代码说明了 Rails 其实是把 blank? 添加到 String 的基类 Object 上的。我们会在 8.2.1 节中介绍一些 Rails 扩展 Ruby 类的例子。）

从第 7 章开始，我们会使用 Hash 初始化对象，这种技术叫做“mass assignment”，在 Rails 中很常用。

如果帮助函数是针对某个特定控制器的，你应该把它放进该控制器相应的帮助文件中。例如，为 StaticPages 控制器创建的帮助函数一般放在 app/helper/static_pages_helper.rb 中。在这个例子中，我们会把 full_title 这个帮助函数用在网站内所有的网页中，针对这种情况 Rails 提供了一个特别的文件：app/helper/application_helper.rb。↩ 	

其实这里还有一个地方我们还不能理解，那就是 Rails 是怎么把这些联系在一起的：把 URI 映射到动作上，full_title 帮助函数可以在视图中使用，等。这是个很有意思的话题，我建议你以后好好的了解一下，不过使用 Rails 并不需要完全了解 Rails 的运作机理。（若想更深入的了解 Rails，我推荐阅读 Obie Fernandez 的《Rails 3 之道》。）↩

块是闭包（closure），知道这一点对资深编程人员可能会有点帮助。闭包是一种匿名函数，其中附带了一些数据。

没有了约束的好处是，Symbol 很容易进行比较，字符串要按照字母一个一个的比较，而 Symbol 只需进行一次操作。这就使得 Symbol 成为 Hash 键的最佳选择

关于 Ruby 类和 self 关键字，请阅读 RailsTips 上的《Class and Instance Variables in Ruby》一文

你没必要知道继承关系中的每个类。我也不知道它们都是干什么的，而我从 2005 年就开始使用 Ruby on Rails 进行开发了。这可能意味着了以下两个问题中的一个，第一，我是个废柴，第二，你不需要知道所有的内在知识也能成为熟练的 Rails 开发者。我们当然都希望是第二点!

从 Rails 3.1 开始到最新的 Rails 4，静态文件可以存放在三个标准的目录中，各有各的用途：

app/assets：存放当前应用程序用到的资源文件
lib/assets：存放开发团队自己开发的代码库用到的资源文件
vendor/assets：存放第三方代码库用到的资源文件
你可能猜到了，上面的目录中都会有针对不同资源类型的子目录。例如：

$ ls app/assets/
images javascripts stylesheets
现在我们就可以知道 5.1.2 节中 custom.css.scss 存放位置的用意：因为 custom.css.scss 是应用程序本身用到的，所以把它存放在 app/assets/stylesheets 中。

预处理器引擎

准备好资源文件后，Rails 会使用一些预处理器引擎来处理它们，通过清单文件将其合并，然后发送给浏览器。我们通过扩展名告诉 Rails 要使用哪个预处理器。三个最常用的扩展名是：Sass 文件的 .scss，CoffeeScript 文件的 .coffee，ERb 文件的 .erb。我们在 3.3.3 节介绍过 ERb，5.2.2 节会介绍 Sass。本教程不需要使用 CoffeeScript，这是一个很小巧的语言，可以编译成 JavaScript。（RailsCast 中关于 CoffeeScript 的视频是个很好的入门教程。）

Sass 是一种编写 CSS 的语言，从多方面增强了 CSS 的功能。本节我们会介绍两个最主要的功能，嵌套和变量。
嵌套

样式表中经常会定义嵌套元素的样式，例如，在代码 5.6 中，定义了 .center 和 .centr h1 两个样式：

.center {
  text-align: center;
}

.center h1 {
  margin-bottom: 10px;
}
使用 Sass 可将其改写成

.center {
  text-align: center;
  h1 {
    margin-bottom: 10px;
  }
}


其中 LOGO 的 id #logo 出现了两次，一次是单独出现的，另一次是和 hover 伪类一起出现的（鼠标悬停其上时的样式）。如果要嵌套第二个样式，我们需要引用父级元素 #logo，在 SCSS 中，使用 & 符号实现：

#logo {
  float: left;
  margin-right: 10px;
  font-size: 1.7em;
  color: #fff;
  text-transform: uppercase;
  letter-spacing: -1px;
  padding-top: 9px;
  font-weight: bold;
  line-height: 1;
  &:hover {
    color: #fff;
    text-decoration: none;
  }
}


变量

Sass 允许我们自定义变量来避免重复，这样也可以写出更具表现力的代码。例如，代码 5.7 和代码 5.14 中都重复使用了同一个颜色代码：

h2 {
  .
  .
  .
  color: #999;
}
.
.
.
footer {
  .
  .
  .
  color: #999;
}


因为像 $lightGray 这样的变量名比 #999 更具说明性，所以为没有重复使用的值定义变量往往也是很有用的。Bootstrap 框架定义了很多颜色变量，Bootstrap 页面中有这些变量的 LESS 形式。这个页面中的变量使用的是 LESS 句法，而不是 Sass 句法，不过 bootstrap-sass gem 为我们提供了对应的 Sass 形式。二者之间的对应关系也不难猜出，LESS 使用 @ 符号定义变量，而 Sass 使用 $ 符号。在 Bootstrap 的变量页面我们可以看到为淡灰色定义的变量：

@grayLight: #999;
也就是说，在 bootstrap-sass gem 中会有一个对应的 SCSS 变量 $grayLight。我们可以用它换掉自己定义的 $lightGray 变量：

h2 {
  .
  .
  .
  color: $grayLight;
}
.
.
.
footer {
  .
  .
  .
  color: $grayLight;
}

网站中链接的路由和 URL 地址的映射关系

页面	URL	对应的路由
“首页”	/	root_path
“关于”	/about	about_path
“帮助”	/help	help_path
“联系”	/contact	contact_path
“注册”	/signup	signup_path
“登录”	/signin	signin_path


首先要编写集成测试，可以通过下面的命令生成：

$ rails generate integration_test user_pages

你可能想知道为什么要使用 footer 标签和 .footer class。理由就是，这样的标签对于人类来说更容易理解，而那个 class 是因为 Bootstrap 里在用，所以不得不用。如果愿意的话，用 div 标签代替 footer 也没什么问题

译者注：一般不建议在 CSS 中使用颜色名称，因为不同的浏览器和不同的系统对同一个颜色的渲染有所不同，没有使用十六进制的颜色代码准确

旁注 6.1：为什么要自己开发用户验证系统
基本上所有的 Web 应用程序都会需要某种登录和用户验证系统。所以 Web 框架大都有很多验证系统的实现方案，Rails 当然也不例外。用户验证及授权系统有很多，包括 Clearance、Authlogic、Devise 和 CanCan（还有一些不是专门针对 Rails 的基于 OpenID 和 OAuth 开发的系统）。所以你肯定就会问，为什么还要重复制造轮子，为什么不直接用现有的解决方案，而要自己开发呢？

首先，实践已经证明，大多数网站的用户验证系统都要对第三方代码库做一些定制和修改，这往往比重新开发一个验证系统的工作量还大。再者，现有的方案就像一个“黑盒”，你无法了解其中到底有些什么功能，而自己开发的话就能更好的理解实现的过程。而且，Rails 最近的更新（参见6.3 节），使开发验证系统变得很简单。最后，如果后续开发要用第三方代码库的话，因为自己开发过，所以你可以更好的理解其实现过程，便于定制功能。


和之前一样，如果你一直使用 Git 做版本控制，现在最好为本章创建一个从分支：

$ git checkout master
$ git checkout -b modeling-users
（第一个命令是要确保处在主分支，这样创建的 modeling-users 从分支才会基于 master 分支的当前状态。如果你已经处在主分支的话，可以跳过第一个命令。）

在 Rails 中，数据模型的默认数据结构叫做模型（model，MVC 中的 M，参见1.2.6 节）。Rails 为解决数据持久化提供的默认解决方案是，使用数据库存储需要长期使用的数据。和数据库交互默认的代码库是 Active Record1。Active Record 提供了一系列的方法，可直接用于创建、保存、查询数据对象，而无需使用关系数据库所用的结构化查询语言（structured query language， SQL）2。Rails 还支持数据库迁移（migration）功能，允许我们使用纯 Ruby 代码定义数据结构，而不用学习数据定义语言（data definition language, DDL）。Active Record 把你和数据库层完全隔开了。本教程开发的应用程序在本地使用的是 SQLite 数据库，部署后使用 PostgreSQL 数据库（由 Heroku 提供，参见 1.4 节）。这就引入了一个更深层次的话题，那就是在不同的环境中，即便使用的是不同类型的数据库，我们也无需关心 Rails 是如何存储数据的。

（注意，和生成控制器的命令习惯不同，模型的名字是单数：控制器是 Users，而模型是 User。）我们提供了可选的参数 name:string 和 email:string，告诉 Rails 我们需要的两个属性是什么，以及各自的类型（两个都是字符串）。你可以把这两个参数与代码 3.4 和代码 5.29 中的动作名称对比一下，看看有什么不同。

代码 6.1 中的 generate 命令带来的结果之一是创建了一个数据库迁移文件。迁移是一种精确修改数据库结构的方式，可以根据需求修改数据模型。本例中 User 模型的迁移文件是直接通过 generate model 命令生成的。迁移文件会创建 users 表，包含两个列，即 name 和 email，如代码 6.2 所示。（我们会在 6.2.5 节以及 6.3 节介绍如何手动创建迁移文件。）

注意一下迁移文件名的前面有个时间戳（timestamp），这是该文件被创建时的时间。早期迁移文件名的前缀是个递增的数字，在协作团队中如果多个编程人员生成了相同序号的迁移文件就可能会发生冲突。除非两个迁移文件在同一秒钟生成这种小概率事件发生了，否则使用时间戳基本可以避免冲突的发生。迁移文件的代码中有一个名为 change 的方法，这个方法定义要对数据库做什么操作。代码 6.2 中，change 方法使用 Rails 提供的 create_table 方法在数据库中新建一个表，用来存储用户数据。create_table 后跟着一个块，指定了一个块参数 t（代表这个表对象）。在块中，create_table 方法通过 t 对象创建了 name 和 email 两个列，均为 string 类型。4这里使用的表名是复数形式（users），不过模型名是单数形式（User），这是 Rails 在用词上的一个约定，即模型表现的是单个用户的特性，而数据库表却存储了很多用户。块中最后一行 t.timestamps 是个特殊的方法，它会自动创建两个列，created_at 和 updated_at，这两个列分别记录创建用户的时间戳和更新用户数据的时间戳。（6.1.3 节会介绍使用这两个列的例子。）这个迁移文件表示的完整数据模型如图 6.2 所示。

大多数迁移，包括本教程中的所有迁移，都是可逆的，也就是说可以通过一个简单的 Rake 命令“向下迁移”，撤销之前的迁移操作，这个命令是 db:rollback：

$ bundle exec rake db:rollback

（另外还有一个撤销迁移的方法请查看旁注 3.2。）这个命令会调用 drop_table 方法把 users 表从数据库中删除。我们之所以可以这么做，是因为 change 方法知道 create_table 的反操作是 drop_table，所以回滚时就会直接调用 drop_table 方法。对于一些无法自动逆转的操作，例如删除列，就不能依赖 change 方法了，我们要分别定义 up 和 down 方法。关于迁移的更多内容请查看 Rails 指南。

在第 7 章中会介绍，虽然一般习惯把创建和保存分成如上所示的两步分别操作，不过 Active Record 也允许我们使用 User.create 方法把这两步合成一步：

>> User.create(name: "A Nother", email: "another@example.org")
#<User id: 2, name: "A Nother", email: "another@example.org", created_at:
"2013-03-11 01:05:24", updated_at: "2013-03-11 01:05:24">
>> foo = User.create(name: "Foo", email: "foo@bar.com")
#<User id: 3, name: "Foo", email: "foo@bar.com", created_at: "2013-03-11
01:05:42", updated_at: "2013-03-11 01:05:42">
注意，User.create 的返回值不是 true 或 false，而是返回创建的用户对象，可直接赋值给变量（例如上面第二个命令中的 foo 变量）.

create 的反操作是 destroy：

>> foo.destroy
=> #<User id: 3, name: "Foo", email: "foo@bar.com", created_at: "2013-03-11
01:05:42", updated_at: "2013-03-11 01:05:42">
奇怪的是，destroy 和 create 一样，返回值是销毁的对象。我不觉得什么地方会用到 destroy 的返回值。更奇怪的事情是，销毁的对象还在内存中：

>> foo
=> #<User id: 3, name: "Foo", email: "foo@bar.com", created_at: "2013-03-11
01:05:42", updated_at: "2013-03-11 01:05:42">
那么我们怎么知道对象是否真的被销毁了呢？对于已经保存而没有销毁的对象，怎样从数据库中获取呢？要回答这些问题，我们要先学习如何使用 Active Record 查找用户对象。

 查找用户对象

Active Record 为查找对象提供了好几种方法。我们要使用这些方法来查找刚创建的第一个用户，同时也验证一下第三个用户（foo）是否被销毁了。先看一下还存在的用户：

>> User.find(1)
=> #<User id: 1, name: "Michael Hartl", email: "mhartl@example.com",
created_at: "2013-03-11 00:57:46", updated_at: "2013-03-11 00:57:46">
我们把用户的 id 传递给 User.find 方法，Active Record 会返回 id 为1 的用户对象。

下面来看一下 id 为 3 的用户是否还在数据库中：

>> User.find(3)
=> #ActiveRecord::RecordNotFound: Couldn't find User with ID=3
因为在 6.1.3 节中销毁了第三个用户，所以 Active Record 无法在数据库中找到，抛出了一个异常，说明在查找过程中出现了问题。因为 id 不存在，所以 find 方法才会抛出 ActiveRecord::RecordNotFound 异常。9

除了 find 方法之外，Active Record 还支持指定属性来查找用户：

>> User.find_by_email("mhartl@example.com")
=> #<User id: 1, name: "Michael Hartl", email: "mhartl@example.com",
created_at: "2013-03-11 00:57:46", updated_at: "2013-03-11 00:57:46">
find_by_email 方法是 Active Record 根据 users 表中的 email 列自动定义的（你可能猜到了，Active Record 还定义了 find_by_name 方法）。从 Rails 4.0 开始，通过属性查找记录推荐的做法是使用 find_by 方法，属性值以 Hash 形式传入：

>> User.find_by(email: "mhartl@example.com")
=> #<User id: 1, name: "Michael Hartl", email: "mhartl@example.com",
created_at: "2013-03-11 00:57:46", updated_at: "2013-03-11 00:57:46">
因为我们会把 Email 地址当成用户名使用，所以在实现用户登录功能时，这种查找用户的方式会很有用（参见第 7 章）。你也许会担心如果用户数量过多，使用 find_by 的效率不高。事实的确如此，我们会在 6.2.5 节介绍这个问题，以及解决方法，即使用数据库索引。

最后我们还要介绍几个常用的用户查找方法。首先是 first 方法：

>> User.first
=> #<User id: 1, name: "Michael Hartl", email: "mhartl@example.com",
created_at: "2013-03-11 00:57:46", updated_at: "2013-03-11 00:57:46">
很明显，first 会返回数据库中的第一个用户。还有 all 方法：

>> User.all
=> [#<User id: 1, name: "Michael Hartl", email: "mhartl@example.com",
created_at: "2013-03-11 00:57:46", updated_at: "2013-03-11 00:57:46">,
#<User id: 2, name: "A Nother", email: "another@example.org", created_at:
"2013-03-11 01:05:24", updated_at: "2013-03-11 01:05:24">]
all 方法会返回一个数组，包含数据库中的所有用户。



 更新用户对象

创建对象后，一般都会进行更新操作。更新有两种基本的方式，其一，我们可以分别为各属性赋值，在 4.4.5 节中就是这么做的：

>> user           # Just a reminder about our user's attributes
=> #<User id: 1, name: "Michael Hartl", email: "mhartl@example.com",
created_at: "2013-03-11 00:57:46", updated_at: "2013-03-11 00:57:46">
>> user.email = "mhartl@example.net"
=> "mhartl@example.net"
>> user.save
=> true
注意，最后一个命令是必须的，我们要把改动写入数据库。我们可以执行 reload 命令来看一下没保存的话是什么情况。reload 命令会使用数据库中的数据重新加载对象：

>> user.email
=> "mhartl@example.net"
>> user.email = "foo@bar.com"
=> "foo@bar.com"
>> user.reload.email
=> "mhartl@example.net"

更新数据的第二种常用方式是使用 update_attributes 方法：

>> user.update_attributes(name: "The Dude", email: "dude@abides.org")
=> true
>> user.name
=> "The Dude"
>> user.email
=> "dude@abides.org"
update_attributes 方法可接受一个指定对象属性的 Hash 作为参数，如果操作成功，会执行更新和保存两个命令（保存成功时返回值为 true）。注意，如果任何一个数据验证失败了，例如存储记录时需要密码（会在 6.3 节实现），update_attributes 操作就会失败。如果要更新单个属性，请使用 update_attribute，这样就能跳过验证限制了：

>> user.update_attribute(:name, "The Dude")
=> true
>> user.name
=> "The Dude"


用户数据验证

6.1 节创建的 User 模型现在已经有了可以使用的 name 和 email 属性，不过功能还很简单：任何字符串（包括空字符串）都可以使用。名字和 Email 地址的格式显然要复杂一些。例如，name 不应该是空白的，email 应该符合 Email 地址的特定格式。而且，我们要把 Email 地址当成用户名用来登录，那么某个 Email 地址在数据库中就应该是唯一的。

总之，name 和 email 不是什么字符串都可以接受的，我们要对二者可接受的值做个限制。Active Record 是通过数据验证机制（validation）实现这种限制的。本节，我们会介绍几种常用的数据验证：存在性、长度、格式和唯一性。在 6.3.4 节还会介绍另一种常用的数据验证：二次确认。7.3 节会看到，如果提交了不合要求的数据，数据验证机制会显示一些很有用的错误提示信息。

上述代码使用了 pending 方法，提示我们应该编写一些真正有用的测试。我们可以准备一个空“测试数据库”然后运行 User 模型的测试看一下现在的情况：

$ bundle exec rake db:migrate
$ bundle exec rake test:prepare
$ bundle exec rspec spec/models/user_spec.rb
*


Finished in 0.01999 seconds
1 example, 0 failures, 1 pending

Pending:
  User add some examples to (or delete)
  /Users/mhartl/rails_projects/sample_app/spec/models/user_spec.rb
  (Not Yet Implemented)
在大多数系统中，有待实现的测试都会显示为黄色，介于通过（绿色）和失败（红色）之间。

这是我们第一次看到创建“测试数据库”的正确命令：

$ bundle exec rake test:prepare

这个命令会把“开发数据库” db/development.sqlite3 中的数据模型复制到“测试数据库” db/test.sqlite3 中。（执行迁移后很多人经常都会忘记执行这个 Rake 任务。而且，“测试数据库”经常会损坏，需要还原。如果测试出现了莫名其妙的问题，可以执行 rake test:prepare 看能否解决。）
我们会按照提示的建议，编写一些 RSpec 测试用例，如代码 6.5 所示。

代码 6.5：针对 :name 和 :email 属性的测试
spec/models/user_spec.rb

require 'spec_helper'

describe User do

  before { @user = User.new(name: "Example User", email: "user@example.com") }

  subject { @user }

  it { should respond_to(:name) }
  it { should respond_to(:email) }
end
before 块，在代码 5.28 中用过，会在各测试用例之前执行块中的代码，本例中这个块的作用是为 User.new 传入一个合法的初始 Hash 参数，创建 @user 实例变量。接下来的

subject { @user }
把 @user 设为这些测试用例默认的测试对象。在 5.3.4 节中设定的测试对象是 page 变量。

代码 6.5 中的两个测试用例对 name 和 email 属性的存在性进行了测试：

it { should respond_to(:name) }
it { should respond_to(:email) }
其实，这两个测试用例使用的是 Ruby 的 respond_to? 方法，这个方法可以接受一个 Symbol 参数，如果对象可以响应指定的方法或属性就返回 true，否则返回 false：

$ rails console --sandbox
>> user = User.new
>> user.respond_to?(:name)
=> true
>> user.respond_to?(:foobar)
=> false
为 User 模型添加新方法或新属性时可以采用这种测试方式，而且使用这种方式还能清晰的列出 User 实例对象可以响应的所有方法。

因为我们前面已经执行 rake test:prepare 命令准备好了“测试数据库”，所以测试应该是通过的：

$ bundle exec rspec spec/
验证存在性

存在性验证算是最基本的验证了，它只是检查给定的属性是否存在。本节我们就会确保在用户存入数据库之前，名字和 Email 地址字段都是存在的。7.3.3 节会介绍如何把这个限制应用在创建用户的注册表单中。

我们先来编写检查 name 属性是否存在的测试。虽然 TDD 的第一步是写一个失败测试（参见 3.2.1 节），不过此时我们还没有完全理解数据验证是怎么实现的，无法编写合适的测试，所以我们暂时先把数据验证加进来，在控制台中实操一下，理解一下验证机制。然后我们会把验证代码注释掉，编写失败测试，再把注释去掉，看一下测试是否还是可以通过的。这么做对这样简单的测试来说可能有点小题大做，不过我见过很多“简单”的测试并没有检查真正要测试的内容。要保证测试检测真正需要检测的内容，最好谨慎一点。（这种加注释的方法在为没有测试的应用程序编写测试时也经常用到。）

验证 name 属性是否存在的方法是使用 validates 方法，传入 presence: true 参数，如代码 6.6 所示。参数 presence: true 是只有一个元素的可选 Hash 参数。我们在 4.3.4 节中介绍过，如果方法的最后一个参数是 Hash 的话，可以省略 Hash 的花括号。（如 5.1.1 节中提到的，这样的可选 Hash 在 Rails 中很普遍。）

验证 name 属性的存在性
app/models/user.rb

class User < ActiveRecord::Base
  validates :name, presence: true
end
代码 6.6 看起来很神奇，其实 validates 只不过是一个方法而已。加上括号后等效的代码如下：

class User < ActiveRecord::Base
  validates(:name, presence: true)
end


格式验证

对 name 属性的验证只需做一些简单的限制就好，任何非空、长度小于 51 个字符的字符串就可以。不过 email 属性则需要更复杂的限制。目前我们只是拒绝空的 Email 地址，本节我们要限制 Email 地址符合常用的形式，类似 user@example.com 这种。

这里我们用到的测试和验证不是十全十美的，只是刚刚好可以接受大多数的合法 Email 地址，并拒绝大多数不合法的 Email 地址。我们会先对一些合法的 Email 集合和不合法的 Email 集合进行测试。我们使用 %w[] 来创建集合，集合中的元素都是字符串形式，如下面的控制台会话所示：

我们把这个正则表达式定义为常量 VALID_EMAIL_REGEX，Ruby 中的常量都是以大写字母开头的。

VALID_EMAIL_REGEX = /\A[\w+\-.]+@[a-z\d\-.]+\.[a-z]+\z/i
validates :email, presence: true, format: { with: VALID_EMAIL_REGEX }
使用上面的代码可以确保只有匹配这个正则表达式的 Email 地址才是合法的。（因为 VALID_EMAIL_REGEX 以大写字母开头，是个常量，所以其值是不能改变的。）

那么，这个正则表达式是怎么编写出来的呢？正则表达式中的文本匹配模式是由简练的语言编写的（很多人会觉得很难读懂），学习如何编写正则表达式是一门艺术，为了便于理解，我会把 VALID_EMAIL_REGEX 拆分成几块来讲解（如表格 6.1所示）。11要想认真学习正则表达式，我推荐使用 Rubular 正则表达式编辑器（如图 6.4），这个工具在学习的过程中是必备的。12Rubular 网站的界面很友好，便于编写所需的正则表达式，网站中还有一个便捷的快速语法参考。我建议你使用 Rubular 来理解表格 6.1中的正则表达式片段。读的再多也不比不上在 Rubular 中实操几次。（注意：如果你在 Rubular 中输入代码 6.14 中用到的正则表达式，要把 \A 和 \z 去掉。）

表格 6.1：拆分代码 6.14 中匹配 Email 地址的正则表达式

表达式	含义
/\A[\w+\-.]+@[a-z\d\-.]+\.[a-z]+\z/i	完整的正则表达式
/	正则表达式开始
\A	匹配字符串的开头
[\w+\-.]+	一个或多个字母、加号、连字符、或点号
@	匹配 @ 符号
[a-z\d\-.]+	一个或多个小写字母、数字、连字符或点号
\.	匹配点号
[a-z]+	一个或多个小写字母
\z	匹配字符串结尾
/	结束正则表达式
i	不区分大小写

顺便说一下，在官方标准中确实有一个正则表达式可以匹配所有的合法 Email 地址，但没必要使用这么复杂的正则表达式，代码 6.14 中使用的正则表达式就很好，甚至可能比官方的更好。13不过，上面的正则表达式有一个缺陷，能匹配 foo@bar..com 这种有连续点号的地址。修正这个瑕疵的方法会留作练习，参见 6.5 节。

现在，测试应该都可以通过了。（其实，对合法 Email 地址的测试一直都是可以通过的，因为正则表达式很容易出错，进行合法 Email 格式测试只是为了检测 VALID_EMAIL_REGEX 是否可用。）那么就只剩一个限制要实现了：确保 Email 地址的唯一性。

唯一性验证

确保 Email 地址的唯一性（这样才能作为用户名），要使用 validates 方法的 unique 参数。提前说明，实现的过程中存在一个很大的陷阱，所以不要轻易的跳过本小节，要认真的阅读。

和之前一样，先来编写测试。之前的模型测试，只是使用 User.new 在内存中创建一个对象，而做唯一性测试则要把数据存入数据库中。14对相同 Email 地址的（第一个）测试如代码 6.15 所示。



唯一性验证的不足

现在还有一个小问题，在此衷心的提醒你：唯一性验证无法真正保证唯一性。

不会吧，哪里出了问题呢？下面我来解释一下。

Alice 用 alice@wonderland.com 注册；
Alice 不小心按了两次提交按钮，连续发送了两次请求；
然后就会发生下面的事情：请求 1 在内存中新建了一个用户对象，通过验证；请求 2 也一样。请求 1 创建的用户存入了数据库，请求 2 创建的用户也存入了数据库。
结果是，尽管有唯一性验证，数据库中还是有两条用户记录的 Email 地址是一样的。
相信我，上面这种难以置信的过程是可能会发生的，只要有一定的访问量，在任何 Rails 网站中都可能发生。幸好解决的办法很容易实现，只需在数据库层也加上唯一性限制。我们要做的是在数据库中为 email 列建立索引，然后为索引加上唯一性限制。

为 email 列建立索引就要改变数据库模型，在 Rails 中可以通过迁移实现（参见 6.1.1 节）。在 6.1.1 节 中我们看到，生成 User 模型时会自动创建一个迁移文件（参见代码 6.2），现在我们是要改变已经存在的模型结构，那么使用 migration 命令直接创建迁移文件就可以了：

$ rails generate migration add_index_to_users_email

为了保证 Email 地址的唯一性，还要做些修改：存入数据库之前把 Email 地址转换成全小写字母的形式，因为不是所有数据库适配器的索引都是区分大小写的。17 为此，我们要使用回调函数（callback），在 Active Record 对象生命周期的特定时刻调用（参阅 Rails API 中关于回调函数的文档）。本例中，我们要使用的回调函数是 before_save，在用户存入数据库之前强行把 Email 地址转换成全小写字母形式，如代码 6.20 所示。

代码 6.20：把 Email 地址转换成全小写形式，确保唯一性
app/models/user.rb

class User < ActiveRecord::Base
  before_save { self.email = email.downcase }
  .
  .
  .
end
在代码 6.20 中，before_save 后跟有一个块，块中的代码调用了字符串的 downcase 方法，把用户的 Email 地址转换成小写字母形式。这些代码有些深度，此时你只需相信这些代码可以达到目的就行了。如果你有所怀疑，可以把代码 6.16 中的唯一性验证代码注释掉，创建几个 Email 地址一样的用户，看一下存储时得到的错误信息。（8.2.1 节 还会用到这个技巧，到时会使用推荐的“方法引用”约定。）编写针对代码 6.20 的测试会留作练习，参见 6.5 节。

至此，上面 Alice 遇到的问题就解决了，数据库会存储请求 1 创建的用户，不会存储请求 2 创建的用户，因为它违反了唯一性限制。（在 Rails 的日志中会显示一个错误，不过无大碍。其实我们可以捕获抛出的 ActiveRecord::StatementInvalid 异常，不过本教程不会涉及异常处理。）为 email 列建立索引同时也解决了 6.1.4 节中提到的 find_by_email 的效率问题（参阅旁注 6.2）。

旁注 6.2：数据库索引
创建数据库列时，要考虑是否会用这个列进行查询。例如，代码 6.2 中的迁移，创建了 email 列，第 7 章中实现的用户登录功能，会通过提交的 Email 地址查询对应的用户记录。按照现有的数据模型，使用 Email 地址查找用户的唯一方式是遍历数据库中所有的用户记录，对比提交的 Email 地址和记录中的 email 列，看看是否一致。在数据库的术语中，这叫做“全表扫描（full-table scan）”，对一个有上千用户的网站而言，这可不是一件轻松的事。

为 email 列建立索引则可以解决这个问题。我们可以将数据库索引比拟成书籍的索引。如果要在一本书中找出某个字符串（例如 "foobar"）出现的所有位置，我们需要翻看书中的每一页。但是如果有索引的话，只需在索引中找到 "foobar" 条目，就能看到所有包含 "foobar" 的页码。数据库索引基本上也是这种原理。

加上安全密码

本节我们要加入用户所需的最后一个常规属性：安全密码，用来验证用户的身份。实现的方式是，用户记着自己的密码，而在数据库中存储着加密后的密码。稍后我们还会加入基于密码的用户身份验证机制，第 8 章会利用这个机制实现用户登录功能。

验证用户身份的方法是，获取用户提交的密码，进行加密，再和数据库中存储的加密密码对比，如果二者一致，用户提交的就是正确的密码，用户的身份也就验证了。我们要对比的是加密后的密码，而不是原始的密码文本，所以验证用户身份时不用在数据库中存储用户的密码，这样可以规避一个很大的安全隐患。

安全密码机制基本上是由 Rails 中一个单独的方法 has_secure_password 实现的（自 Rails 3.1 开始使用）。因为后续的内容都是基于这个方法的，所以很难循序渐进的讲解。从 6.3.2 节开始，我建议尽早的加入 has_secure_password 方法，然后每编写一个测试就注释掉这个方法，这样才能正确的使用 TDD。（视频往往能更好的表现一个循序渐进的开发过程，所以为了能更好的理解这一块，有兴趣的读者可以考虑观看本教程的配套视频。

 密码和密码确认

如图 6.1 中的构思图所示，我们希望用户进行密码确认，这在网络中是很普遍的做法，可以减小误输入带来的风险。虽然在控制器层可以实现这个想法，不过在模型层实现更好，Active Record 可以确保密码确认万无一失。为此，我们要把 password 和 password_confirmation 两列加入 User 模型，在记录存入数据库之前比较这两列的值是否一样。和之前见过的属性不一样，password 是虚拟的属性，只是临时存在于内存中，而不会存入数据库中。

我们先编写检查是否可以响应 password 和 password_confirmation 方法的测试，如代码 6.24 所示。

再次用到了 let 方法，还用到了 specify 方法。specify 是 it 方法的别名，如果你觉得某个地方用 it 读起来怪怪的，就可以换用 specify。本例中，“it should not equal wrong user”读起来很顺，不过“user: user with invalid password should be false”有点累赘，换用“specify: user with invalid password should be false”感觉就好些。

旁注 6.3：let 方法
我们可以使用 RSpec 提供的 let 方法便捷的在测试中定义局部变量。let 方法的句法看起来有点怪，不过和变量赋值语句的作用是一样的。let 方法的参数是一个 Symbol，后面可以跟着一个块，块中代码的返回值会赋给名为 Symbol 代表的局部变量。也就是说：

let(:found_user) { User.find_by(email: @user.email) }
定义了一个名为 found_user 的变量，其值等于 find_by 的返回值。在这个测试用例的任何一个 before 或 it 块中都可以使用这个变量。使用 let 方法定义变量的一个好处是，它可以记住（memoize）变量的值。（memoize 是个行业术语，不是“memorize”的误拼写。）对上面的代码而言，因为 let 的备忘功能，found_user 的值会被记住，因此不管调用多少次 User 模型测试，find_by 方法只会运行一次。

旁注 7.1：Rails 的三个环境
Rails 定义了三个环境，分别是“生产环境”、“开发环境”和“测试环境”。Rails 控制台默认使用的是“开发环境”：

$ rails console
Loading development environment
>> Rails.env
=> "development"
>> Rails.env.development?
=> true
>> Rails.env.test?
=> false
如前所示，Rails 对象有一个 env 属性，属性上还可以调用各环境对应的布尔值方法，例如，Rails.env.test?，在“测试环境”中的返回值是 true，而在其他两个环境中的返回值则是 false。

如果需要在其他环境中使用控制台（例如，在“测试环境”中进行调试），只需把环境名称传递给 console 命令即可：

$ rails console test
Loading test environment
>> Rails.env
=> "test"
>> Rails.env.test?
=> true
Rails 本地服务器和控制台一样，默认使用“开发环境”，不过也可以在其他环境中运行：

$ rails server --environment production
如果要在“生产环境”中运行应用程序，先要提供生产环境数据库。在“生产环境”中执行 rake db:migrate 命令可以生成“生产环境”所需的数据库：

$ bundle exec rake db:migrate RAILS_ENV=production
（我发现在控制台、服务器和迁移命令中指定其他环境的方法不一样，这可能会产生混淆，所以我特意演示了三个命令的用法。）

顺便说一下，把应用程序部署到 Heroku 后，可以使用如下的命令进入远端的控制台：

$ heroku run console
Ruby console for yourapp.herokuapp.com
>> Rails.env
=> "production"
>> Rails.env.production?
=> true
Heroku 是用来部署网站的平台，自然会在“生产环境”中运行应用程序。

第 7 章已经实现了注册新用户的功能，本章我们要为已注册的用户提供登录和退出功能。实现登录功能之后，就可以根据登录状态和当前用户的身份定制网站的内容了。例如，本章我们会更新网站的头部，显示“登录”或“退出”链接，以及到个人资料页面的链接；在第 10 章中，会根据当前登录用户的 id 创建关联到这个用户的微博；在第 11 章，我们会实现当前登录用户关注其他用户的功能，实现之后，在首页就可以显示被关注用户发表的微博了。

实现登录功能之后，还可以实现一种安全机制，即根据用户的身份限制可以访问的页面，例如，在第 9 章中会介绍如何实现只有登入的用户才能访问编辑用户资料的页面。登录系统还可以赋予管理员级别的用户特别的权限，例如删除用户（也会在第 9 章中实现）等。