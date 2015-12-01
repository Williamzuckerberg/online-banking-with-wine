~~中国工商银行飞天二代U盾 ICBC\_FT\_UShield2\_Install.exe 可能是最容易wine的,依赖的.sys驱动文件最少.~~

更新: 除了 SafeSign\_ICBC\_Per.exe , 其他几种u盾驱动都不需安装额外的.sys驱动文件

```

$ ls
SafeSign_ICBC_Per.exe


BHDCInstall_per.exe  
ICBC_MH_UShield2_Install.exe
GemPCkey_personal.exe         
ICBC_TDR_UShield2_Install.exe
goldpac_personal_2006.exe     
ICBC_FT_UShield2_Install.exe
ICBC_LCD_PerNet.exe

```

更新2: 待确认: u盾驱动怎么会完全没有 .sys 文件? 需要到windows下安装检验一下.

PCSC-Lite
http://pcsclite.alioth.debian.org/

更新3:
winedump用法:
```
$ winedump dump -j import BHDCInstall_per.exe  
```

更新4:
wine 7z 可以解压大部分的exe安装文件,Linux native 7z则问题比较多.
```
$ winetricks -q 7zip
$ WINEPREFIX=$HOME/.local/share/wineprefixes/7zip/ \
wine ~/.local/share/wineprefixes/7zip/drive_c/Program\ Files/7-Zip/7z.exe e \
something.exe
```