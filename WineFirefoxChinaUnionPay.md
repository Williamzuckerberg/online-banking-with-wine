#Wine Firefox登陆中国银联

1. 安装最新版的Wine

2. 安装 firefox 5
```
$ winetricks -q firefox
```

3. 打开firefox
  * 图形界面方式: 在菜单中依次找  Wine/Programs/Mozilla Firefox/Firefox


  * 命令行方式:

```
   $ export WINEPREFIX=~/.local/share/wineprefixes/firefox
   $ cd WINEPREFIX
   $ cd drive_c/Program\ Files/Mozilla\ Firefox/
   $ wine firefox.exe
```

4. 在firefox中打开 about:config
> 设置 `dom.ipc.plugins.enabled` 为 false
这一步是对 [Bug 17273](http://bugs.winehq.org/show_bug.cgi?id=17273) - SetNamedPipeHandleState is a stub - affects flash on
FireFox 的workaround.

5. 打开 http://online.unionpay.com/static/help/detail_20.html#loc_137 , 根据提示安装插件

6. 重启 firefox, 就可以正常登陆中国银联了

转载请保留原始链接,此页面将随着Wine更新而更新.

http://code.google.com/p/online-banking-with-wine/wiki/WineFirefoxChinaUnionPay