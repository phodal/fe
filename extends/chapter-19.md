单页面应用的后台渲染
===

我已经想不到一个好的关于前端分享的主题了，于是联想到最近想要做的一件事，就想到了这个标题。或许这是一个好的主题，又或许这不是一个好的主题。但是至少我可以Share一下我的经验：

- 基于Mustache模板引擎的前后台渲染。
- 基于PreRender方式的Angular.js应用的后台渲染
- 服务端渲染的React

开始之前，我希望即使你们需要后台渲染，你们也应该前后端分离！由**后台**来提供API数据，前端用自己的后台来渲染页面。听上去有点绕，简单的来说就是不要把大量的业务逻辑放前台来，只把显示逻辑放在前台上。这样一来，即使有一天我们换了新的前端，如移动应用，那么我们的后台也是可用的。。

## 为什么需要前后端分离？

这是一个很古老的话题，对于大公司来说就是部门大了，需要拆分。因此开始之前，先提一下“康威定律”：

> Organizations which design systems are constrained to produce designs which are copies of the communication structures of these organizations.

换成中文，即：**设计系统的组织，其产生的设计和架构等价于组织间的沟通结构**。上图

![Conway](http://articles.phodal.com/separation/conway.jpg)

这张图可以解释相当多的软件开发过程中的问题，而我们知道软件开发的主要问题是沟通问题。组织结构影响了我们的沟通结构，进而影响了我们的软件系统结构。好吧，我承认可能离题有点远。不过，我想说的是组织结构可能不允许我们做出一些好的系统架构。

如我们在《[RePractise前端篇: 前端演进史](http://mp.weixin.qq.com/s?src=3&timestamp=1467515714&ver=1&signature=z1onJvKn4TSrUmXm384CQUF1IZBVsLShsQ4DpmumN6xY0Gm5RR9XKdbf6ELzdRqg-mxdtxceTg-4-KrhYHZQC6wiSEWsP64vh0sl2Je4G16hnS6MsuZaD-u01HAENCSKuw3mQL-F2Gc5WYvti9SQlw==)》中提到的那样：我们已经有了一个桌面版网页，然后我们打造了一个APP。然而，总有些客户想在手机上浏览但是又不想下APP，我们就需要一个移动版。为什么会这样？因为用户已经被养成了这样的习惯，大部分的网站提到了桌面版、移动版、APP。要维护这样的三个不同的系统，对于大部分的业务公司来说成本太高了。

于是，大部分公司来说解决方案就是 后台 + 大前端 （桌面前端、移动Web、手机APP）。Angular和React就是为了解决这样的问题，而出现了不同的解决方案——基于Angular.js的混合应用框架Ionic、以及React Native。不过在当前，我对React Native的共用UI还是持观望态度。有人可能会提到Vue和Weex，但是我觉得并没有那么好用。或许是因为我接触React比较早，我觉得Vue的语法四不像。

在这样的情形下，我们只需要几个后台开发人员和几个前端开发人员就可以完成系统的设计了。这种前端开发人员就是最近几年人们“最想要”的。

## 前后台渲染同一模板

我接触的第一个SPA应用是一个基于Spring  MVC和Backbone的移动网站，但是它比一般的SPA应该要复杂——由于SEO的缘故，它需要支持后台渲染。

当搜索引擎通过URL访问我们的网站的时候，我们就需要返回相应的HTML。这意味着我们需要在后台有对应的模板引擎来支持，而由于SPA的性质又决定了，这需要使用一个纯前端的模板引擎。因此，我们并不能使用两个模板引擎来做这件事，维护两套模板注定会是一件痛苦的事，并且当时还没有React这种模板引擎在。不过，后来我们发现维护两种不同的渲染方式也是一件痛苦的事。因此，我们就会有了类似于下图的架构：

![Spring MVC Backbone](http://articles.phodal.com/separation/spring-backbone.png)

我们在后台使用Spring MVC作为基础架构、Mustache作为模板引擎，和使用JSP作为模板引擎相比没有多大的区别——由Controller去获取对应的Model，再渲染给用户。多数时候搜索引擎都是依据Sitemap来进行索引的，所以我们的后台很容易就可以处理这些请求。同样的当用户访问相应的页面的时候，也返回同样的页面内容。当完成页面渲染的时候，就交由Backbone来处理相应的逻辑了。换句话来说，从这时候它就变成了一个单页面应用。

尽管这是一个三年年前开始的项目，但是在今天看来，这种做法仍然相应地有趣： 大部分的单页面应用只有一个首页，并由HTTP服务器（如Nginx）、Web框架（如Express、Koa）对路由做一些处理，可以让用户通过特定地URL访问特定地页面。而我们需要保证所有的用户访问地都是真实的页面，既然JavaScript没有加载完，用户也能看到完整的页面。

在这个项目里，最大的挑战就是如何保证后台渲染和前台渲染的业务逻辑是一样的。如当我们想要针对不同的产品显示不同的内容时，我们就需要在JavaScript中赋予一些逻辑，我们还需要在Java在有同样的逻辑。相比于在同一个代码里有桌面版、移动版来说，逻辑有更加复杂的趋势——因为在这种情况下，我们只需要维护两个不同的模板即可。而在SPA的情况下，我们要维护**两套逻辑**。后来，这个框架交由下文中的React与响应式设计重写。

在今天你仍然可以使用这样的方式来渲染，JDK 1.8自带了嵌入式JavaScript引擎Nashorn，完成支持ECMAScript 5.1规范以及一些扩展。

## PreRender方式

在我们重新设计系统的时候，曾经考虑过类似的做法。将我们的所有页面渲染成静态的HTML，然后用爬虫抓取我们的所有页面，再上传到AWS即可。当时我们咨询了其他小组的做法，其中有一个小组正是采用了这种PreRender的方式——在本地运行起一个Server，由PhantomJS来渲染页面，再保存为对应的HTML。

PreRender就是预先渲染好HTML，并针对于爬虫返回特定的HTML。（PS：不过作为一个很有经验的SEO开发人员，我一点不喜欢这种作法。要知道Google有时候会模拟成真实的用户，不带有爬虫的那些参数和标志，去访问页面。如果你返回给Google的两个页面差异太大——可能是你忘记更新了频率，那么Google可能就会认为你在**作弊**。）

![PreRender](http://articles.phodal.com/separation/angular-prerender.jpg)

对于一般用户来说就不会返回后台渲染的结果了：

![Angular PreRender](http://articles.phodal.com/separation/angular-phantomjs-prereder.jpg)

和上面的第一种情况相比，这种作法可以大大减少服务器地负担，并且可以直接交由CDN就可以了。这时我们只需要考虑要渲染哪些页面即可，对于数据量比较少的网站来说这是一个不错的做法，但是多了就不一样了。

对于我们来说，有两个问题：一个是速度的问题，他们有上万条数据就需要近一天左右的时间来生成（渲染时间长），而我们有上百万条数据。二是数据的实时问题，我们的产品数据每天都会更新一次。
## React

对于使用React的开发人员来说，要处理后台渲染就是一种更简单的事，毕竟React中提供了一个方法叫 renderToString()。我们所要做的就是用Express或者Koa对路由进行处理，然后返回对应的内容即可：

![React Server Side Render](http://articles.phodal.com/separation/react-server-side-render.png)

然后，剩下的事都可以交由React来解决，就是这么简单。

因为在这个时候我们在前后台使用的都是JavaScript，我们可以在这个地方直接实现对数据库的操作，就会出现我们在开头说到的前后台分离的问题。这样做并不合理，后台只应该返回我们所需要的数据，并且它可以随时被其他语言替换掉。
