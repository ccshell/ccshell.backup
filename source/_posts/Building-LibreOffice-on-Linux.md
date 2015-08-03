title: Linux下编译Libreoffice
date: 2015-08-03 09:44:44
tags:
- Libreoffice

---
项目比较大，编译时间比较长。建议代码放在至少有30G剩余空间的磁盘位置。
# 编译环境
最简单的方式使用系统提供的编译支持进行环境配置。
在Debian/Ubuntu中：

    $ sudo apt-get build-dep libreoffice
在Fedora中：

    $ sudo yum-builddep libreoffice
# 配置和编译
简单编译可以使用：

    $ #进入项目根目录
    
    $ ./autogen.sh #检查编译环境，生成编译配置文件
    
    $ make #编译
推荐使用如下命令进行配置：

    $ ./autogen.sh --disable-report-builder --disable-vba --disable-odk \
    --disable-opengl --disable-opencl --disable-dbus --disable-sdremote \
    --disable-sdremote-bluetooth --disable-tdeab --disable-firebird-sdbc \
    --disable-randr --disable-postgresql-sdbc --disable-lotuswordpro \
    --disable-collada --disable-scripting-beanshell --disable-kdeab \
    --with-lang=zh-CN --without-java --without-help \
    --disable-gstreamer-0-10 
可以将如上代码放入脚本文件中。
可以使用：

    $ ./autogen.sh --help
查看支持哪些选项。
编译完成后可以直接在项目根目录下启动程序：

    $ instdir/program/soffice --writer
# 加速编译
用**ccache缓存**编译器生成的结果，这可以节省重新编译项目时的时间。
使用系统库中的包就可以装好ccache。
在Debian/Ubuntu中：

    $ apt-cache search ccache #查找相应的包
    
    $ sudo apt-get install ccache #安装相应的包
在Fedora中：

    $ yum search ccache #查找相应的包
    
    $ yum install ccache #安装相应的包
装好后默认就可以使用了。建议做如下配置：

    $ ccache --max-size 32G #修改ccache使用32G的缓存空间
如果磁盘空间紧张可以启用ccache的压缩缓存。在用户的.bashrc中添加：

    $ export CCACHE_COMPRESS=1
用**Icecream做分布式编译**，需要有多台机器可以访问，且需要一台机器做服务器（做调度）。Libreoffice对Icecream做了内建支持，使用系统库中的包就可以装好icecream。只需要在配置时./autogen.sh后再附加上：

    --enable-icecream
配置时默认会查找**/opt/icecream/**下的编译器，系统包安装其到了/usr/sbin/，为此需要建立一个符号链接

    $ sudo ln -s /usr/sbin/ /opt/icecream
服务器的机器需要**手动启用调度程序**，也可以将下行放入自启动脚本中：

    $ icecc-scheduler -d
客户端程序默认就启动了守护程序，如果没有启动可以直接执行：

    $ iceccd -d





