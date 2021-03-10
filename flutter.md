# Flutter笔记
## 前言
>Flutter是谷歌的移动UI框架，可以快速在iOS和Android上构建高质量的原生用户界面。 Flutter可以与现有的代码一起工作。在全世界，Flutter正在被越来越多的开发者和组织使用，并且Flutter是完全免费、开源的。

![image](https://user-images.githubusercontent.com/52229845/110598713-06ee1380-81bd-11eb-8931-a0de4215541d.png)
## 面世
Flutter是Google在2015年推出的移动UI框架，可快速在iOS和Android上构建高质量的原生用户界面。
Flutter第一次亮相于2015年5月Dart开发者峰会上，初始名字叫做“Sky”，后更名为Flutter，Flutter使用Dart语言开发，Dart是Google于2011年推出的新的计算机编程语言。
![image](https://user-images.githubusercontent.com/52229845/110599724-1f126280-81be-11eb-8371-e752b8f36732.png)

## 特点
### 快速开发
由于Flutter选用了Dart作为其开发语言，Dart既可以是AOT（Ahead Of Time）编译，也可以是JIT（Just In Time）编译，其JIT编译的特性使Flutter在开发阶段可以达到亚秒级有状态热重载，从而大大提升了开发效率。
### 性能优越
使用自带的高性能渲染引擎（Skia）进行自绘，渲染速度和用户体验堪比原生。
### 富有表现力的精美UI
Flutter内置众多精美的Material Design和Cupertino（iOS风格）小部件，开发者可快速构建精美的用户界面，以提供更好的用户体验。

## 框架

如下图所示为Flutter系统架构图，可以看出Flutter框架分为三层：Framework层、Engine层和Embedder层。

### Framework层：
由Dart来实现，包含众多安卓Material风格和iOS Cupertino风格的Widgets小部件，还有渲染、动画、绘图和手势等。Framework包含日常开发所需要的大量API，普通应用开发熟悉这些API的使用基本OK了，不过很多特殊场景的控件需要自己根据实际情况进行自定义。Framework层的源码地址：https://github.com/flutter/flutter/tree/master/packages/flutter/lib

### Engine层：
由C/C++实现，是Flutter的核心引擎，主要包括Skia图形引擎、Dart运行时环境Dart VM、Text文本渲染引擎等；如果想深入了解Flutter原理，建议阅读该层的源代码。源代码地址：https://github.com/flutter/engine

### Embedder层：
主要处理一些平台相关的操作，如渲染Surface设置、本地插件、打包、线程设置等。
![image](https://user-images.githubusercontent.com/52229845/110599499-e4a8c580-81bd-11eb-8811-2f6bfe7f95ef.png)
## 原理
无论是iOS还是安卓都是提供一个平台的View给Flutter层，页面内容渲染交由Flutter层自身来完成，所以其相对React Native等框架性能更好。Flutter中图形渲染流程：
![image](https://user-images.githubusercontent.com/52229845/110599965-613ba400-81be-11eb-99e7-e55a9a0ccaef.png)
大致流程如下：

>1. GPU的Vsync信号同步到UI线程
>2. UI线程使用Dart来构建抽象的视图结构
>3. 视图结构在GPU线程中进行图层合成
>4. 合成后的视图数据提供给Skia图形引擎处理成GPU数据
>5. 数据再通过OpenGL或Vulkan提供给GPU进行渲染

## 
