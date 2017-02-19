学会这几个前端调试技能，助力提高三倍开发效率
===

我还是一个野生程序员的时候，不会 Debug，只会傻傻地写一句句 std::count。即使是在今天，有些时候我也会这样做：打一个 console.log，然后看看结果是不是和预期的一样。如果不是和预期一样，就修改一下代码，刷新一下浏览器。这得亏是 JavaScript 是一门动态语言，可以很快的看到运行的结果。


我的调试入门
---

我是在大学里学会 Debug 的，当时在为一个支持在线调试的芯片写程序。对于嵌入式开发而言，不同的芯片都会有不同的 IDE。有的 IDE 可以支持调试，有的则不行；有的 IDE 则连基本的语法高亮都没有。

对于不支持在线调试的芯片来说，没有屏幕也就不能使用 printf 来输出结果。只能通过 SD 卡里的文件系统来写入日记，再计算机上读取日记来分析。这只的是一件麻烦的事，对于没有 SD 卡的开发板来说，还需要腾出几个脚本接上 SD 卡。也有些芯片是不能使用 SD 卡的，这时你就只能靠你的想象力来调试了。

这只是基本的调试。。

有一些则可以支持更高级的调试。

Intellij Idea, Debugger, ``evaluate expression``，即评估表达式。

而这些，都在 Chrome、Safari 这些现代的浏览器上有，

在编写代码的时候，你可以边实现功能

基本调试技巧
---

![认识一下调试窗口](../images/basic-inspect.png)

### Inspect

### Network

### Console

移动设备调试
---

### Emulation

Network, Repsponsive

### Device Inspect

``chrome://inspect/``

![Inspect Devices](../images/inspect-devices.jpg)

同理，对于 Safari 浏览器来说也是一样的：

Safari, Debug Device

除此，如果正在开发的应用是混合应用，Safari 也可以对此进行调试。

![Safari Simulator](../images/safari-hybird.jpg)

性能调试
---

Timelie, Profiles, Application

插件扩展
---

### Postman

https://github.com/phodal/toolbox

### PageSpeed

### React


