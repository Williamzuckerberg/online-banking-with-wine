# 使用Wine Google Chrome 登陆中国银联 #

1. 参考 [WineChromeUsage](WineChromeUsage.md), 在Wine中安装Google Chrome

2. 参考 [WineChromeUsage](WineChromeUsage.md), 在Wine Google Chrome中安装中国银联登陆控件

加上 --no-sandbox --single-process参数启动 chrome.exe

```
$ cd ~/.wine/drive_c/users/$USER/Local\ AppData/Google/Chrome/Application
$ wine chrome.exe --no-sandbox --single-process
```

打开 http://online.unionpay.com/static/help/detail_20.html#loc_137 , 根据提示安装插件

3. 参考 [WineChromeUsage](WineChromeUsage.md), 加上 --no-sandbox 参数启动 chrome.exe, 打开 https://online.unionpay.com/ , 即可正常登陆中国银联

```
$ cd ~/.wine/drive_c/users/$USER/Local\ AppData/Google/Chrome/Application
$ wine chrome.exe --no-sandbox
```


转载请保留原始链接,本页面将随Wine更新而更新,欢迎补充和维护:

http://code.google.com/p/online-banking-with-wine/wiki/WineChromeUsage