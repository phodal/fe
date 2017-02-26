我的职业是前端工程师
===

2017 年 1 月份，看完村上春树的新书《我的职业是一个小说家》，我便萌发了写一个《我的职业是前端工程师》系列文章的想法——以个人视角来看前端领域的各种技术。整个系列的文章大概有 15 篇左右，从我是如何成为一个前端工程师，到各种前端框架的知识。

关注我的微信公众号（扫描下面的二维码或搜索 Phodal）.

![QRCode](http://articles.phodal.com/qrcode.jpg)

目录
---

*   [我要成为一个前端设计师](#我要成为一个前端设计师)
    *   [漂亮的前台](#漂亮的前台)
    *   [我要成为一个前端设计师](#我要成为一个前端设计师-1)
    *   [关于《我的职业是前端工程师》](#关于我的职业是前端工程师)
*   [入门不是应该很简单吗？](#入门不是应该很简单吗)
    *   [前端之路](#前端之路)
    *   [我的前端入门](#我的前端入门)
        *   [我的第一个网站](#我的第一个网站)
        *   [Copy/Paste from Cookbook](#copypaste-from-cookbook)
        *   [开发工具](#开发工具)
        *   [jQuery 是最好用的](#jquery-是最好用的)
*   [学习前端只需要三个月【语言篇】](#学习前端只需要三个月语言篇)
    *   [JavaScript 语言的变化](#javascript-语言的变化)
        *   [JavaScript](#javascript)
        *   [ES6+](#es6)
        *   [TypeScript](#typescript)
    *   [小结](#小结)
*   [如何选择合适的前端框架，告别选择恐惧症](#如何选择合适的前端框架告别选择恐惧症)
    *   [前端的选择恐惧症](#前端的选择恐惧症)
        *   [技术选型：不仅仅受技术影响](#技术选型不仅仅受技术影响)
        *   [上线时间影响框架](#上线时间影响框架)
        *   [锤子定律：你需要更大的视野](#锤子定律你需要更大的视野)
    *   [前端框架一览](#前端框架一览)
        *   [jQuery, 使用生态解决问题](#jquery-使用生态解决问题)
        *   [Backbone.js，脊椎连接框架](#backbone.js脊椎连接框架)
        *   [Angular，一站式提高生产力](#angular一站式提高生产力)
        *   [React，组件化提高复用](#react组件化提高复用)
        *   [Vue.js，简单也是提高效率](#vue.js简单也是提高效率)
        *   [小结](#小结-1)
    *   [总结](#总结)
*   [前端工程师必会的六个调试技能](#前端工程师必会的六个调试技能)
    *   [我的调试入门](#我的调试入门)
    *   [基本调试技巧：实时调试](#基本调试技巧实时调试)
        *   [实时调试样式](#实时调试样式)
        *   [实时调试代码](#实时调试代码)
    *   [移动设备调试](#移动设备调试)
        *   [模拟真机：设备模拟器](#模拟真机设备模拟器)
        *   [真机调试：Device Inspect](#真机调试device-inspect)
    *   [网络调试](#网络调试)
        *   [网络调试](#网络调试-1)
        *   [使用插件](#使用插件)
    *   [小结](#小结-2)
*   [如何以正确的姿势练习，深化前端知识](#如何以正确的姿势练习深化前端知识)
    *   [前端项目的练习过程](#前端项目的练习过程)
        *   [Output is Input](#output-is-input)
        *   [练习框架、技术的时机](#练习框架技术的时机)
    *   [练习的过程](#练习的过程)
    *   [练习框架、技术的技巧](#练习框架技术的技巧)
        *   [使用模板](#使用模板)
        *   [做点什么应用](#做点什么应用)
        *   [编写一个博客应用](#编写一个博客应用)
        *   [输入和总结](#输入和总结)
    *   [其它](#其它)
        *   [关于练手项目](#关于练手项目)
*   [移动开发](#移动开发)
*   [前端基础知识](#前端基础知识)
    *   [准备工作](#准备工作)
    *   [编写一个简单的 HTML](#编写一个简单的-html)
    *   [漂亮的 CSS](#漂亮的-css)
    *   [JavaScript 居然是小三](#javascript-居然是小三)

TODO
---

 - Predix: 为什么前端没有前途？
 - 模板引擎
 - API 使用 与 设计 ？
 - 混合应用设计？
 - 构建系统？？？？
 - 如何做好 SEO ？
 - 如何设计响应式布局？
 - 如何理解/构建 MVC 框架？
 - 如何理解/构建 SPA 应用？

参考：[https://github.com/phodal/awesome-growth](https://github.com/phodal/awesome-growth)
---


 - 基础
   * HTML / CSS
   * JavaScript
   * DOM
 - 中级篇 
   * 数据格式（如JSON、XML）
   * RESTful API交互（如jQuery Ajax，Fetch API，ReactiveX）
   * 正则表达式
   * HTML语义化
   * 命令行
   * Node.js
   * DIV / CSS
   * SCSS / SASS 
   * 矢量图形 / 矢量图形动画（如SVG）
   * 单页面应用
 - 高级篇
   * ES6 / TypeScript 
   * CSS3
   * 面向对象编程
   * 函数式编程
   * MVC / MVVM / MV*
   * 安全性（如跨域）
   * 授权（如HTTP Basic、JWT等等）
 - 工程化
   * 代码质量（如JSLint / ESLint / TSLint / CSLint）
   * 代码分析（如Code Climate）
   * 测试覆盖率
   * 构建系统（gulp、grunt、webpack等等）
   * 自动构建（脚本）
 - 兼容性
   *  跨浏览器测试 （Chrome，IE，Firefox，Safari等等）
   *  跨平台测试（Windows、GNU/Linux，Mac OS等等）
   *  跨设备测试（Desktop，Android，iOS，Windows Phone）
   *  跨版本测试（同一个浏览器的不同版本）
 - 前端特定
   * CSS / CSS3 动画
   * JavaScript 动画
   * Web字体嵌入
   * Icon 字体
   * 图形和图表
   *  CSS Sprite（如glue）
   * DOM操作（如jQuery、React等等）
   * 模板引擎（如JSX、Handlebars、JSP、Mustache等等）
 - 软件工程
   * 版本管理（如git、svn） 
   * 包管理（如npm、bower）
   * 依赖管理
   * 模块化（如CommonJS、WebPack）
 - 调试
   * 浏览器调试
   * Debug工具
   * Wireshark / Charles抓包
   * 远程设备调试（如Chrome Inspect Devices）
 - 测试
   * 单元测试
   * 服务测试
   * UI测试
   * 集成测试
 - 性能与优化
   * PageSpeed / Yslow 优化
   * 加载优化（如gzip压缩、缓存等等）
   * 性能测试（特别是移动Web）
   * 可用性
   * 压缩（如Minify、Uglify、CleanCSS等等）
 - 设计
   * 切页面
   * 线框图（Wireframe）
   * 响应式设计
   * 网格布局（Grid Layout）
   * Flexbox布局
 - SEO
   * Sitemap（站点地图）
   * 内部链接建设
   * MicroData / MicroFormat
   * 页面静态内容生成
   * H1、H2、H3和strong使用
   * Title、Description优化
   * 页面静态内容生成

LICENSE
---

[![Phodal's Article](http://brand.phodal.com/shields/article-small.svg)](https://www.phodal.com/) [![Phodal's Book](http://brand.phodal.com/shields/book-small.svg)](https://www.phodal.com/)


© 2017 [Phodal Huang](https://www.phodal.com). This code is distributed under the Creative Commons Attribution-Noncommercial-No Derivative Works 3.0  License. See `LICENSE` in this directory.

[待我代码编成，娶你为妻可好](http://www.xuntayizhan.com/blog/ji-ke-ai-qing-zhi-er-shi-dai-wo-dai-ma-bian-cheng-qu-ni-wei-qi-ke-hao-wan/)
