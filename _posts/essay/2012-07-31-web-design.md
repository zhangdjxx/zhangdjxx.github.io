---
layout: post
title: 响应式设计
published: true
---

前几日一直在折腾如何让网页在不同设备，尤其是分辨率不同的PC上可以尽可能不受干扰地显示出来。开始的思路比较小白，想着写个浏览器调用device分辨率的函数，但是后来看到关于Twitter开源前端框架Bootstrap介绍后，才知道自己一直在找的应该是网页响应性设计（Responsive Web design）。

其实我之前的做法多少有些原始，相比于现在市场逐渐复杂多样的设备而言，多少有些吃力不讨好，Morten Hjerde和他的同事们曾对2005至2008年市场中的400余种移动设备进行了统计：

[![](http://ww4.sinaimg.cn/bmiddle/66af2c95jw1dvf0ynowoej.jpg)](http://ww4.sinaimg.cn/bmiddle/66af2c95jw1dvf0ynowoej.jpg)

实际上当我们把关注点聚焦在网页内容与浏览器上时，响应式设计才是更好的选择。

现在大概掌握有三种主流响应性设计方案，即同比例缩减元素，调整页面布局和显示或隐藏内容。 0.同比例缩减元素---针对图片 缩减元素主要考虑网页中的图片，实现图片根据浏览器的变化而发生改变，主要思路有2个，一是采用弹性图片，或者采用响应式图片。 前者，实现代码：`img{max-width:100%}`css中定义即可。 思路主要是开始设置图片maxwidth，若浏览器边缘小于图片宽度，图片自动同比例缩小。但是劣势也很明显，由于网页加载是最原始的图片，会降低下载速度及浪费空间（尤其PC端到移动端时），小设备上图片分辨率会显得过高。

后者，实现代码：[JavaScript文件](https://github.com/filamentgroup/Responsive-Images)（responsiveimgs.js&.htaccess&一些demo）。 思路主要是responsiveimgs.js会检测当前设备的屏幕分辨率，如果是大屏幕设备，则向页面head部分中添加BASE标记，并将后续的图片、脚本和样式表加载请求定向到一个虚拟路径"/rwd-router"。当这些请求到达服务器端，.htaccess文件会决定这些请求所需要的是原始图片还是小尺寸的"响应式图片"，并进行相应的反馈输出，优势是选择屏幕下载合适的图片（andriod类似有max-minddle-small图的选择），不过也有相应的劣势，不支持现在旧浏览器，会将原图下载下来。

也有希望图片在ipod&ipad中不做自动收缩的处理，即不出现x轴滚动条，根据苹果官方文档，添加以下代码即可： \<meta name="viewport" content="width=device-width; initial-scale=1"\>

1.调整页面结构布局---针对总体 主要是采用用独立样式表或CSS media query或javascript进行页面的总体布局。 \#独立样式表\# 默认主样式表来定义页面的主要结构元素，比如\#wrapper、\#content、\#sidebar、\#nav等的默认布局方式，以及一些全局性的配色和字体方案，通过一个子级样式表来继承主样式表的设定，并专门针对某些布局结构进行样式覆写。

# Media Queries

CSS2&CSS3 media query通吃版 1.制定多个样式表，然后通过media属性进行设备检测选择css； 页面通过屏幕呈现(非打印一类)，并且屏幕宽度不超过480px，则加载shetland.css样式表 2. 更有效率的做法是，将多个media queries整合在一个样式表文件中。

CSS3 media query min-width&max-width，min-device-width&max-device-width新属性很靠谱，可以好好的调试运用。 多个media queries整合在单一样式表中进行编码的句法: @media screen and (min-width: 600px) {.hereIsMyClass {width: 30%;float: right;}}

上面代码中定义的类(hereIsMyClass)只有在浏览器或屏幕宽度超过600px时才会有效。 @media screen and (max-width: 600px) {.aClassforSmallScreens {clear: both;font-size: 1.3em;}} 而这段代码的作用则相反：aClassforSmallScreens类只有在浏览器或屏幕宽度小于600px时才会有效。

对于Ipad（需要经常进行翻转，相应速度要快），但不适用于iphone（以使用min-device-width和max-device-width来变通实现，硬件大小固定） 对于iPad来说，orientation属性尤其有用。它的值可以是landscape(横屏)或portrait(竖屏)。 @media screen and (orientation: landscape) {.iPadLandscape {width: 30%;float: right;}} or @media screen and (orientation: portrait) {.iPadPortrait {clear: both;}}

# Javascript

某些旧设备无法完美支持CSS3的media query时，它可以作为后备支援。幸运的是，已经有专门的JS库来帮助旧浏览器(IE 5+，Firefox 1+，Safari 2等)支持CSS3的media queries。使用方法很简单，下载css3-mediaqueries.js并在你的页面中调用它。

2.显示或隐藏内容----针对文字 对于手机类设备，可以隐藏掉大块文字内容区，而只显示一个简单的导航结构，其中的导航元素可以指向详细内容页面，其中下面是默认的主样式表，要隐藏掉链接导航部分(sidebar-nav)，因为默认样式适用的设备屏幕会足够大，足够显示包括两个侧边栏在内的所有内容。 \#content{width: 54%;float: left;margin-right: 3%;} \#sidebar-left{width: 20%;float: left;margin-right: 3%; } \#sidebar-right{width: 20%;float: left;} .sidebar-nav{display: none;}

下面是用于小屏幕移动设备的样式表代码。现在，要隐藏掉两个侧边栏，并使sidebar-nav显示出来。借助JavaScript，当用户点击sidebar-nav中的链接时，对应的侧边栏可以恢复显示。当然，触发恢复显示的方式有很多种，即可以通过JS改变侧边栏的display属性值，也可以为其添加额外的布局样式。 \#content{width: 100%;} \#sidebar-left{display: none;} \#sidebar-right{display: none;} .sidebar-nav{display: inline;}
