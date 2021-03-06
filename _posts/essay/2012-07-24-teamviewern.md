---
layout: post
title: 远程登录利器—TeamViewer
published: true
---

最近工作要涉及2台笔记本，X201i用来处理公事，Acer一般用来处理私事。不过很多时候，事情很难严格区分，两台电脑处理的事情总会出现有很多重叠，最吃紧的是俩台笔记本不在一个地方。

上周每天晚上我还会热血沸腾地把X201i抬回居住地，但是这周突然觉得，对于上下班常常处于人流高峰期的我来说，简直是种折磨，索性开始寻找解决方案。排除了反反复复地拷贝外，现在大概方案主要是2个，一个是所有工作放在云端完成，另外就是在家远程控制放在公司的小黑。

前者暂时还没找到很好的载体满足我所有的需求，代码可以放在Github上，文档现在习惯用Google Docs云端编写，但是对于很多针对PDF的阅读笔记同步，资料的引用多少有点不便，索性就暂时选择了后者远程一下，短期解决所有的问题。

要简单实现远程登录是件非常容易的事情，使用windows远程登录界面就可以搞定，但是难题是由于小黑处于公司内网的IP域，使用win远程桌面的话，必须还需借助网管在路由器上做一些设定端口映射之类的设置才有办法连上，然后在[CoX](http://www.v2ex.com/member/CoX) 的倾情推荐下，开始使用GmbH公司开发的[TeamViewer](http://www.teamviewer.com/en/index.aspx?utm_expid=60202728-11&utm_referrer=http%3A%2F%2Fwww.teamviewer.com%2FzhCN%2Findex.aspx)，直接绕过各种内网，防火墙限制，直达目标。

[![](http://ww4.sinaimg.cn/bmiddle/66af2c95tw1dv8a102f0pj.jpg)](http://ww4.sinaimg.cn/bmiddle/66af2c95tw1dv8a102f0pj.jpg)

TeamViewer客户端用户分为注册帐号以及未注册用户，后者可以看成临时搭建的远程平台，前者更加适合我这类日后需要经常远程的钉子户。一个注册帐号可以添加N个需要经常需要远程的电脑，步骤也很简单，就像微博登录授权那么简易。

至于未注册用户，客户端会根据使用的PC的Mac地址分配给你唯一的ID，但是每次登录客户端时，会随机给你别人若要远程你电脑所需的密码，对于临时建立还是非常方便的。

俩者的逻辑深到本质，注册帐号其实是实现一个用户对自己N台电脑之间进行切换访问，未注册帐号则实现一个用户与另一个用户之间的远程访问。

今晚已经成功Access公司锁定的小黑，并且进行一些文件读写复制操作，内网访问（VPN也省掉了），因为暂时是纯粹的Test，就直接远程进行了关机，不过要实现远程开机，还要在小黑内安段木马绑定mac唤醒机器，不过纯粹hack式地耍弄技术了，并没有太多的实用之处。

至于TV的会议功能，暂时用不到，但是以后有需要，还是相当不错的选择。官网上还展示了TV的其他系列版本产品，其中TeamViewer Mobile尤其亮眼，想到8月初就可以用到手的Itouch和Galaxy Nexus户外控制室内的电脑，就莫名兴奋。下面是itouch 测试图。

[![](http://ww1.sinaimg.cn/bmiddle/66af2c95jw1dveyk8wcsvj.jpg)](http://ww1.sinaimg.cn/bmiddle/66af2c95jw1dveyk8wcsvj.jpg)

而，这也是我看好的方向，移动端不能代替我们日常生活中很多产品，但是一旦可以用轻轻一触就可以控制它们时，那该是多么带劲，多么无可预期，潜力无限！
