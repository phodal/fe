从零开发一个前端应用有多难？
===

工作一段时候后，总会经历要从零创建一个前端应用的经历。

需要相当多的探索

![ReFE](../images/refe.png)

RePractise
---

刚开始的时候，自己一点点的构建添加各种需要的东西。

后来，懒了，便找个模板，改吧，改吧，就用上了。

代码只是其中的一小代码，还需要设计一系列的流程。

如 workflow，

react、angular、vue.js ？

还需要考虑部署方案，自动部署，还是集成式？

![RePractise](../images/repractise.jpg)

而这些设计都不能脱离原始的需求，因此我们必须明白业务到底要的是什么系统。

项目准备
---

### 确认技术方案

react、angular、vue.js ？

### 搭建构建系统

webpack、rollup、tsc ？

gulp、grunt、npm ?

fastlane

### 架构设计

[stepping](https://github.com/phodal/stepping) 完成建模？

```
domain: 库存子域
  aggregate: 库存
    event: 库存已增加
    event: 库存已恢复
    event: 库存已扣减
    event: 库存已锁定
    command: 编辑库存
```

结合 Swagger 生成 Mock API

可这是后端的工作~~，2333。


实现功能
---

### 分析设计图

我的意思是：切图。

### 实现功能

对于数据处理来说，不同的时候，有不同的方式。

按优先级有所不同

 - 先需要从 Mockup 中写入需要的数据 —— 定死
 - 确认需要的接口内容
 - 更新接口到后台
 - 同步后台的接口

如一些 Related Fields 前端需要的可能是扁平的结果，但是未来可能需要更多的值 

### 编写测试

集成
---

### 与后台集成

### 设置 Toggle

上线
---

### 部署

### 上线

### 修 bug

最后，祝大家修 bug 愉快。
