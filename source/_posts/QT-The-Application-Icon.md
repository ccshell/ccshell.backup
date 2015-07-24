title: 在QT中应用程序的图标问题
date: 2015-07-24 14:23:04
tags:
- QT

---

在windows平台，参考QT的文档设置后，程序的图标不能显示。

> The application icon, typically displayed in the top-left corner of an application's top-level windows, is set by calling the QWindow::setWindowIcon() method.
> 
> In order to change the icon of the executable application file itself, as it is presented on the desktop (i.e., prior to application execution), it is necessary to employ another, platform-dependent technique.
> 
> Setting the Application Icon on Windows
> 
> First, create an ICO format bitmap file that contains the icon image. This can be done with e.g. Microsoft Visual C++: Select File|New, then select the File tab in the dialog that appears, and choose Icon. (Note that you do not need to load your application into Visual C++; here we are only using the icon editor.)
> 
> Store the ICO file in your application's source code directory, for example, with the name myappico.ico.
> 
> Then, assuming you are using qmake to generate your makefiles, you only need to add a single line to your .pro project file:
> 
> RC_ICONS = myappico.ico
> 
> Finally, regenerate your makefile and your application. The .exe file will now be represented by your icon in Explorer.
> 
> However, if you already have an .rc file, for example, with the name myapp.rc, which you want to reuse, the following two steps will be required. First, put a single line of text to the myapp.rc file:
> 
> IDI_ICON1               ICON    DISCARDABLE     "myappico.ico"
> 
> Then, add this line to your myapp.pro file:
> 
> RC_FILE = myapp.rc
> 
> If you do not use qmake, the necessary steps are: first, create an .rc file and run the rc or windres program on the .rc file, then link your application with the resulting .res file.

多次网络查询和阅读文档没有发现不对的地方，无奈只好找QT自带的例子进行比对。发现我们的项目在resource.h文件中有：

	#define IDI_ICON1                       101
QT的例子中可没定义对应的资源宏。于是注释掉这行后编译运行，图标可以显示出来了。