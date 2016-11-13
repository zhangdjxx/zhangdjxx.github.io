---
layout: post
title: Python学习笔记（1）
published: true
---

今日起，正式开始学习脚本语言Python，并且在后续学习过程中使用Python来实现一些产品，为了更好做好知识沉淀，之后将会把Python的学习记录下来。

**安装**

版本：现有2.X及3.X两类版本，初学者建议选择前者，因为2.X的第三方库包更多些，2.X与3.X版本差异较少，且现在存在2to3的转化工具，过渡比较自然。如2.X的输出为：

    print "hello,world"

但是3.X的输出则是：

    print （"hello,world"）

直接在官网下载对应系统的安装版本，一直next，则可以顺利安装.

若未出现，右击我的电脑--属性--高级--环境变量--Path，添加Python目录（如;c:\\Python27），可安装成功；

**入门书籍**

-   [Python学习手册](http://www.amazon.cn/mn/detailApp/ref=as_li_ss_tl?_encoding=UTF8&tag=v06-23&linkCode=as2&asin=B004TUJ7A6&camp=536&creative=3132&creativeASIN=B004TUJ7A6)
-   [Python基础教程](http://www.amazon.cn/mn/detailApp/ref=as_li_ss_tl?_encoding=UTF8&tag=v06-23&linkCode=as2&asin=B003TSBAMM&camp=536&creative=3132&creativeASIN=B003TSBAMM)
-   [Python CookBook](http://www.amazon.cn/mn/detailApp/ref=as_li_ss_tl?_encoding=UTF8&tag=v06-23&linkCode=as2&asin=B003LPO4KS&camp=536&creative=3132&creativeASIN=B003LPO4KS)

**学习论坛**

-   **python-cn(华蟒用户组,CPyUG 邮件列表) 
    [https://groups.google.com/forum/?hl=zh-CN&fromgroups=\#!forum/python-cn](https://groups.google.com/forum/?hl=zh-CN&fromgroups=#!forum/python-cn)
    **
-   V2EX Python节点                                                       [http://www.v2ex.com/go/python](http://www.v2ex.com/go/python)
-   Stackoverflow                                                      [http://stackoverflow.com/](http://stackoverflow.com/)

**IDE(集成开发环境)总结和对比**

[【整理】【多图详解】如何在Windows下开发Python：在cmd下运行Python脚本，如何使用Python Shell（command line模式和GUI模式），如何使用Python IDE](http://www.crifan.com/how_to_do_python_development_under_windows_environment)

此处，专门整理了，各种Python的IDE。

**PyScripter**

    [【记录】使用Python的IDE：PyScripter](http://www.crifan.com/try_with_python_ide_pyscripter)

    [【已解决】PyScripter启动出错：Python could not be properly initialized. We must quit.](http://www.crifan.com/pyscripter_start_error_python_could_not_be_properly_initialized_we_must_quit) 

**Ulipd**

    [【记录】使用Python的IDE：Ulipad](http://www.crifan.com/try_with_python_ide_ulipad)

     其中遇到： 
    [【已解决】安装Ulipad后，选择启动Ulipad，结果无法启动](http://www.crifan.com/ulipad_after_install_finish_not_launch)

**Eclipse+PyDev**

Eclipse本身就是个IDE，之前主要用于Java方面的开发，后来，通过添加不同的插件，也支持其他很多语言的开发。

对于Python，就是PyDev插件。

所以完整的叫法其实是，Eclipse这个IDE本身，加上PyDev插件，支持用于Python开发。

详见： 
[【记录】使用Python的IDE：Eclipse+PyDev](http://www.crifan.com/try_with_python_ide_eclipse_pydev)

其中包括： 
[【教程】在Eclipse中安装PyDev](http://www.crifan.com/eclipse_install_plugin_pydev) 
[【教程】在Eclipse中配置刚安装好的PyDev插件](http://www.crifan.com/eclipse_configure_newly_installed_plugin_pydev) 
[【教程】在Eclipse中使用PyDev进行Python开发](http://www.crifan.com/eclipse_use_pydev_develop_python)

然后也有一些相关的优化和问题解决： 
[【已解决】把Eclipse中的PyDev中的Python代码中的很难看的中文换个好看点的字体](http://www.crifan.com/eclipse_pydev_change_ugly_zhcn_char_to_another_font) 
[【已解决】Eclipse+PyDev无法调试Python：Unexpected IO Exception in Pydev debugger](http://www.crifan.com/eclipse_pydev_python_unexpected_io_exception_in_pydev_debugger)

**Aptana Studio 3**

另外，顺带提到一点的是，有个Aptana Studio 3，其本身就是基于Eclipse的，针对Python，也就是用的PyDev，但是主要针对的是Web方面的支持。

详情可参考： 
[【记录】折腾IDE工具：Aptana Studio 3](http://www.crifan.com/try_dev_ide_aptana_studio_3)

其中遇到了： 
[【已解决】Aptana Studio 3中通过Auto Config配置PyDev中Python出错：java.io.IOException: Cannot run program "python": CreateProcess error=2, The system cannot find the file specified](http://www.crifan.com/apatana_studio_3_auto_config_pydev_error_java_io_ioexception_cannot_run_program_python_createprocess_error_2)

**Eric**

有空去试试，Eric，专门为QT开发而弄出来的IDE： 
[http://eric-ide.python-projects.org/index.html](http://eric-ide.python-projects.org/index.html)

**PyCharm**

另外也有一些[这里](http://zhidao.baidu.com/question/515267313.html)提到的： 
PyCharm （不是phcharm） 
[http://www.jetbrains.com/pycharm/](http://www.jetbrains.com/pycharm/) 
尤其适合用于web开发，比如django，gae等。 
不过是收费的。。。

**Sublime Text**

单独对于Sublime本身，其本质上只是个文本编辑器。

不了解的可以去参考：

[【crifan推荐】一款相对不错的文本编辑器：Sublime Text 2](http://www.crifan.com/recommend_a_relative_good_text_editor_sublime_2/)

不过呢，由于界面的确很好看，所以很多人用，然后有些人，发现也可以通过配置去支持在Sublime中运行Python代码。

所以，从这个角度来说，也可以把Sublime，归类为一种Python的IDE。

简单来说：

普通的Python开发，只是想选个功能和界面都不错的IDE的话，推荐用Eclipse+PyDev。

好处是，多去学习和了解Eclipse，因为其足够强大，也可以用其作为其他很多语言的IDE。

针对偏重某些应用领域的话：

-   如果主要用Python来做QT相关的开发，则推荐用Eric；
-   如果主要用于开发Web相关的，可以考虑PyCharm或者Aptana Studio 3

