结合前端框架 Lettuce
----

[https://github.com/phodal/lettuce](https://github.com/phodal/lettuce)

> Lettuce 是一个轻巧的移动开发学习框架。

## Lettuce Usage(用法)

### Class(类)

```javascript
var L = new lettuce();
var zero = function(){};
var sub = new L.Class(zero);
```

### Template(模板)

```javascript
var L = new lettuce();
var data = {
    "title": "JavaScript Templates"
};
var result = L.Template.tmpl("<h3>{%=o.title%}</h3>\n!@#$%^&*()-=",
data);
```

### Router(路由)

```javascript
var L = new lettuce();
var check = L.Router
            .add(/#about/,log)
            .add(/#what/, log)
            .add(/#why/, log)
            .load();;
```

### Effect(效果)

#### 淡出

```javascript
L.FX.fadeOut(document.getElementById('content'), {
    duration: 2000, complete: function () {
    }
});
```

#### 淡入

```javascript
L.FX.fadeIn(document.getElementById('content'), {
    duration: 2000, complete: function () {
    }
});
```

### Promise

```javascript
function late(n) {
    var L = new lettuce();
    var p = new L.Promise();
    return p;
}
late(100).then(
).then(
).done();
```

### Ajax

```javascript
lettuce.get('/bower.json', function(result){
    equal(result["name"], "lettuce");
    done();
})
```

```javascript
lettuce.post("http://127.0.0.1:5000/some", "something", function(data){
    console.log(data)
})
```

### AMD

``RequireJS Config``

```javascript
require.config({
  baseUrl: 'app',
  paths: {
    lettuce: 'lib/lettuce'
  }
});
```

``App.js``

```javascritp
define(['lettuce'],
  function (Lettuce) {
    var lettuce = new Lettuce();
  };
});    
```

## Single Page Application Example(单页面应用)

1.new a instance

```javascript
var L = new lettuce();
```
2.define data

```javascript
var data = {
    about: "Template",
    what: "This about A Mobile Framework For Romantic",
    why: "Why is a new Framework"
};
```

3.create function for router

```javascript
var aboutPage = function(){
    var aboutPage = new L.SimpleView();
    var templates = L.Template.tmpl("<h3>{%=o.about%}</h3>", data);
    return aboutPage.render(templates, "results");
};
var whyPage = function(){
    var whyPage = new L.SimpleView();
    var templates = L.Template.tmpl("<h3>{%=o.why%}</h3>", data);
    return whyPage.render(templates, "results");
};
```

4.Add router

```javascript
L.Router
    .add(/#about/, about)
    .add(/#why/, why)
    .load();
```

## ShowCase

- 一个情人节礼物:
  [http://valentine.phodal.com/](http://valentine.phodal.com/)
- 官网: [http://lettuce.phodal.com/](http://lettuce.phodal.com/)

