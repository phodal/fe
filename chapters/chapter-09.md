你应该知道的单页面应用的五要素 
===

> 这几年里，单页面应用的框架令人应接不暇，各种新的概念也层出不穷。从过去的 jQuery Mobie、Backbone 到今天的 Angular 2、React、Vue 2，除了版本号不同，他们还有很多的相同之处。

刚开始写商业代码的时候，我使用的是 jQuery。使用 jQuery 来实现功能很容易，找到一个相应的 jQuery 插件，再编写相应的功能即可。对于单页面应用亦是如此，寻找一个相辅助的插件就可以了，如 jQuery Mobile。

尽管在今天看来，jQuery Mobile 已经不适合于今天的多数场景了。这个主要原因是，当时的用户对于移动 Web 应用的理解和今天是不同的。他们觉得移动 Web 应用就是针对移动设备而订制的，移动设备的 UI、更快的加载速度等等。而在今天，多数的移动 Web 应用，几乎都是单页面应用了。

过去，即使我们想创建一个单页面应用，可能也没有一个合适的方案。而在今天，可选择的方案就多了（PS：参见《第四章：学习前端只需要三个月【框架篇】》）。每个人在不同类型的项目上，也会有不同的方案，没有一个框架能解决所有的问题

 - 对于工作来说，我更希望的是一个完整的解决方案。
 - 对于编程体验来说，我喜欢一点点的去创造一些轮子。

当我们**会用的框架越多的时候， 所花费的时间抉择也就越多**。而单页面应用的都有一些相同的元素，对于这些基本元素的理解，可以让我们更快的适合其他框架。

单页面应用的演进
---

我接触到单页面应用的时候，它看起来就像是**将所有的内容放在一个页面上么**。只需要在一个 HTML 写好所需要的各个模板，并在不同的页面上 data-role 表明这是个页面（基于 jQuery Mobile）——每个定义的页面都和今天的移动应用的模式相似，有 header、content、footer 三件套。再用 id 来定义好相应的路由。

```
<div data-role="page" id="foo"> 
...
</div>
```

这样我们就在一个 HTML 里返回了所有的页面了。随后，只需要在在入口处的 href 里，写好相应的 ID 即可。

```
<a href="#foo">跳转到foo</a>
```

当我们点击相应的链接时，就会切换到 HTML 中相应的 ID。这种简单的单页面应用基本上就是一个离线应用了，只适合于简单的场景，可是它带有单页面应用的基本特性。而复杂的应用，则需要从服务器获取数据。然而早期受限于移动浏览器性能的影响，只能从服务器获取相应的 HTML，并替换当前的页面。

在这样的应用中，我们可以看到单页面应用的基本元素： **页面路由**，通过某种方式，如 URL hash 来说明表明当前所在的页面，并拥有从一个页面跳转到另外一个页面的入口。

当移动设备的性能越来越好时，开发者们开始在浏览器里渲染页面。


当移动设备的性能越来越好时，开发者们开始在浏览器里渲染页面：

 - 使用 jQuery 来做页面交互
 - 使用 jQuery Ajax 来从服务端获取数据 
 - 使用 Backbone 来负责路由及 Model
 - 使用 Mustache 作为模板引擎来渲染页面
 - 使用 Require.js 来管理不同的模板
 - 使用 LocalStorage 来存储用户的数据 

通过结合这一系列的工具，我们终于可以实现一个复杂的单页面应用。而这些，也就是今天我们看到的单页面应用的基本元素。我们可以在 Angular  应用、React 应用、Vue.js 应用 看到这些基本要素的影子，如：Vue Router、React Router、Angular 2 RouterModule 都是负责路由（页面跳转及模块关系）的。在 Vue 和 React 里，它们都是由辅助模块来实现的。因为 React 只是层 UI 层，而 Vue.js 也是用于构建用户界面的框架。

路由：页面跳转与模块关系
---

要说起路由，那可是有很长的故事。当我们在浏览器上输入网址的时候，我们就已经开始了各种路由的旅途了。

1. 浏览器会检查有没有相应的域名缓存，没有的话就会一层层的去向 DNS服务器 寻向，最后返回对应的服务器的 IP 地址。
2. 接着，我们请求的网站将会将由对应 IP 的 HTTP 服务器处理，HTTP 服务器会根据请求来交给对应的应用容器来处理。
3. 随后，我们的应用将根据用户请求的路径，将请求交给相应的函数来处理。最后，返回相应的 HTML 和资源文化

当我们做后台应用的时候，我们只需要关心上述过程中的最后一步。即，将对应的路由交给对应的函数来处理。这一点，在不同的后台框架的表现形式都是相似的。

如 Python 语言里的 Web 开发框架 Django 的 URLConf，使用正规表达式来表正

```
url(r'^articles/2003/$', views.special_case_2003),
```

而在 Laravel 里，则是通过参数的形式来呈现

```
Route::get('posts/{post}/comments/{comment}', function ($postId, $commentId) {
    //
});
```

虽然表现形式有一些差别，但是总体来说也是差不多的。而对于前端应用来说，也是如此，**将对应的 URL 的逻辑交由对应的函数来处理**。

React Router 使用了类似形式来处理路由，代码如下所示：	
```
 <Route path="messages" component={MessageList} />
 <Route path="messages/:id" component={MessageDetail} />
```


当页面跳转到 messages 的时候，会将控制权将给 MessageList 组件来处理。

当页面跳转到 messages/fasfasf-asdfsafd 的时候，将匹配到这二个路由，并交给 MessageDetail 组件 来处理。而路由中的 id 值，也将作为参数 MessageDetail 组件来处理。

相似的，而 Angular 2 的形式则是：

```
{ path: 'messages',      component: MessageListComponent },
{ path: 'messages/:id',      component: MessageDetailComponent },
```

相似的，这里的 HeroDetailComponent 是一个组件，path 中的 id 值将会传递给 HeroDetailComponent 组件。

从上面来看，尽管表现形式上有所差异，但是其行为是一致的：使用规则引擎来处理路由与函数的关系。稍有不同的是，后台的路由完全交由服务器端来控制，而前端的请求则都是在本地改变其状态。

并且同时在不同的前端框架上，他们在行为上还有一些区别。这取决于我们是否需要后台渲染，即刷新当前页面时的表现形式。

 - 使用 Hash （#）或者  Hash Bang （#!） 的形式。即 # 开头的参数形式，诸如 [ued.party/#/messages](http://ued.party/#/messages)。当我们访问 messages/12 时，URL 的就会变成 [ued.party/#/messages/12](http://ued.party/#/messages/12)
 - 使用新的 HTML 5 的 history API。用户看到的 URL 和正常的 URL 是一样的。当用户点击某个链接进入到新的页面时，会通过 history 的 pushState 来填入新的地址。当我们访问 messages/12 时，URL 的就会变成 [ued.party/messages/12](http://ued.party/messages/12)。当用户刷新页面的时候，请通过新的 URL 来向服务器请求内容。

幸运的是，大部分的最新 Router 组件都会判断是否支持 history API，再来决定先用哪一个方案。


事件监听与状态管理
---

异步

事件

消息

状态

Service，LocalStorage, Redux

数据获取与鉴权
---

Ajax FETCH

展示
---

DOM
View

模板引擎，修改元素


组件化
---

UI 组件化

Require.js

WebPack ES6 

代码模块化
 
