# Wine的安装与使用 #

## Wine的安装 ##

### Ubuntu ppa源安装 ###

Wine的发展很快,软件仓库中的不是最新版本,测试请用ppa源安装或自行编译安装:

用下面一行命令可以安装ppa版本的最新的wine1.3和wine1.3-dbg
```
$ sudo add-apt-repository ppa:ubuntu-wine/ppa; sudo apt-get update; sudo apt-get install wine1.3 wine1.3-dbg
```
参见: http://www.winehq.org/download/

其中wine1.3-dbg是调试符号信息,安装后,程序崩溃或调试程序时可以看到相应的源代码,例如:
```
Wine-dbg>bt

Backtrace:

=>0 0x6834af10 IEWinMain(szCommandLine="", nShowWindow=0x1) 
[/home/fracting/wine-git/dlls/shdocvw/iexplore.c:1017] in shdocvw 
(0x0033fdc8)

  1 0x68324694 main+0xa3(argc=<couldn't compute location>, argv=
<couldn't compute location>) [/home/fracting/wine-
git/dlls/winecrt0/exe_main.c:48] in iexplore (0x0033fe48)


```

### 从源代码编译安装 ###
如果想要自己阅读/修改代码或者应用一些非官方补丁,就需要下载Wine的源代码

简单的过程如下:
```
$ git clone git://source.winehq.org/git/wine.git ~/wine-git

$ sudo apt-get build-dep wine

$ cd ~/wine-git

$ ./tools/wineinstall
```
这一步需要按提示输入root密码或sudo密码.

详情参见: http://wiki.winehq.org/GitWine


## Wine-gecko的安装 ##
Wine buitin IE 使用[gecko](http://goo.gl/IpwHk)作为内核

从源代码编译wine-gecko

待添加

参见:
wiki.winehq.org/BuildingWineGecko




## Wine的使用 ##
从终端启动应用程序
```
$ wine AppName.exe
```

## 使用winetricks安装程序 ##
使用winetricks安装mfc42
```
$ winetricks -q mfc42
```
使用winetricks安装vb6运行环境
```
$ winetricks -q vb6run
```


## wineprefix简介 ##
默认情况下,安装完Wine,主文件夹下不会有关于Wine的任何东西.

第一次运行wine应用程序,或者运行winecfg,或者运行wineboot(重启wine)等,

会在主文件夹下生成 .wine/ 隐藏文件夹,

.wine/下面有个drive\_c , 基本上模拟了windows系统分区的文件结构:

```
$ tree -L 1
.
|-- Program Files
|-- users
|-- windows
`-- winetrickstmp
```
通过Wine安装的程序都会放在这个文件夹的某个子目录下,跟Windows一样.

更多,参考:
http://wiki.jswindle.com/index.php/Wine_Prefixes

通过指定WINEPREFIX环境变量,可以在一个用户主文件夹内使用多个独立的等同于

~/.wine的文件夹,winetricks脚本中有大量可以参考的实例

参见: http://wiki.winehq.org/winetricks

## Wine builtin dll(内置dll)和native dll(原生dll) 简介 ##
builtin是指wine项目重新实现的开源的dll,
native是指从Microsoft Windows上拷贝的商业版本的dll

在使用Wine运行程序时,遇到的最多的问题就是某个builtin dll不管用,一般情况下,

直接复制native dll到 windows/system32 文件夹是没有用的,需要在winecfg(图形界面)

里设置指定要用native还是用builtin,或者使用 WINEDLLOVERRIDES 环境变量,

例如,
```
$ WINEDLLOVERRIDES="comdlg32,shell32=n,b" wine AppName.exe
```
上面这句表示,comdlg32和shell32这两个dll,优先使用native dll的,如果native dll不存在,就使用builtin dll的.

详细内容参见:http://ftp.winehq.org/pub/wine/docs/en/wineusr-guide.html#AEN309

wine的dll中,有一些是不能用native替换的,因为wine的底层dll和ms windows的底层dll不同.

这些包括:   kernel32.dll, gdi32.dll, user32.dll, and ntdll.dll, 如果尝试用图形界面的winecfg

修改这些dll的OVERRIDES属性会收到警告.

### 在Wine中注册dll ###
某些dll需要注册才能使用,只要运行以下命令就可以完成注册:
```
regsvr32 some.dll
```
常见的例子是网银的ActiveX控件,这些控件一般是以 .cab为扩展名,

可以用 cabextract 解压 .cab文件, 再用 regsvr32 注册解压得到的dll文件.


### Wine的buitin dll目前实现进度: ###
参见:

http://source.winehq.org/WineAPI/

http://www.winehq.org/status/dlls

http://www.winehq.org/winapi_stats

仅供参考,有些信息过时了,只有git下载的代码才是最新的


建议阅读Wine官方的文档:

http://wiki.winehq.org/Developers