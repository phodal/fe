你应该知道的单页面应用的五要素 
===

刚开始写一些企业、商业代码的时候，从 jQuery 开始写起的，然后就是 jQuery Mobile 来做单页面应用。

对于工作来说，我更希望的是一个完整的解决方案。

对于编程体验来说，我喜欢一点点的去创造一些轮子。

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
 
