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

单页面应用可没有像现在这么复杂，我们在可以在一个 HTML 写好我们所需要的各个模板，data-role 表明这是个页面，用 id 来定义好相应的路由，入口就这么有了。

```
<div data-role="page" id="foo">
<a href="#foo">Back to foo</a>
```

加上原来的 jQuery Mobile 的 UI 即可。

可到底由于我学的知识是在书上学的，整整比市场落后了上个两三年。这时候，大部分的应用已经开始使用 Backbone 和 Angular.js，这些项目可以提供更好的应用开发体难。

 - Backbone提供了一个 Router
 - Mustache提供了模板
 - jQuery抽象了 DOM
 - Ajax 负责数据处理
 - LocalStorage 数据和状态

从 Backbone到 React 的经历。

Router:页面跳转
---

Route

Django：

```
url(r'^articles/2003/$', views.special_case_2003),
```

Laravel：

```
Route::get('posts/{post}/comments/{comment}', function ($postId, $commentId) {
    //
});
```

hashchange， window.location.hash

URL 设计 列表，详细

window.location.hash

History API

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
 
