#在Wine中安装和使用Google Chrome


# 准备工作 #

  * 安装最新开发版的Wine

# 安装Google Chrome的两种方法 #

## 方法一 ##

  * 下载 ChromeSetup.exe

https://www.google.com/chrome?platform=win&hl=en

  * 安装 Google Chrome

```
$ wine ChromeSetup.exe
```

## 方法二 ##

  * 下载 ChromeStandaloneSetup.exe

https://www.google.com/chrome/index.html?platform=win&hl=en&standalone=1

  * 安装 Google Chrome

```
$ wine ChromeStandaloneSetup.exe
```

# 启动Wine Google Chrome的方法 #

```
$ cd ~/.wine/drive_c/users/$USER/Local\ AppData/Google/Chrome/Application
$ wine chrome.exe --no-sandbox
```

加上 --no-sandbox 参数是对 [Bug 21232](http://bugs.winehq.org/show_bug.cgi?id=21232)的workaround

# 在Wine Google Chrome中安装插件的方法 #

加上 --no-sandbox --single-process 参数启动chrome.exe, 就可以从Chrome App Store正常安装扩展. 安装完成之后, 可以重启chrome.exe加上 --no-sandbox 参数正常使用Chrome的其他功能



```
$ cd ~/.wine/drive_c/users/$USER/Local\ AppData/Google/Chrome/Application
$ wine chrome.exe --no-sandbox --single-process
```

加上 --single-process 参数是对 [Bug 27248](http://bugs.winehq.org/show_bug.cgi?id=27248)的workaround


# 已知问题 #

  * 小子号字体抗锯齿没有打开: [Bug 29240](http://bugs.winehq.org/show_bug.cgi?id=29240)

解决方法一: 反转这个补丁,重新编译Wine: http://source.winehq.org/git/wine.git/?a=commit;h=4ce3af3fad1dfacfe39a441054586707f848038f

其他解决方法待添加,欢迎反馈.


# Known bugs #

  * [Bug 21232](http://bugs.winehq.org/show_bug.cgi?id=21232) Chrome can't load any webpage unless --no-sandbox is used
  * [Bug 27248](http://bugs.winehq.org/show_bug.cgi?id=27248) cannot unpack `*`.crx (extensions or themes) in Chrome unless --single-process is used
  * [Bug 29240](http://bugs.winehq.org/show_bug.cgi?id=29240) Anti-aliasing not working for all fonts


转载请保留原始链接,本页面将随Wine更新而更新,欢迎补充和维护:

http://code.google.com/p/online-banking-with-wine/wiki/WineChromeUsage