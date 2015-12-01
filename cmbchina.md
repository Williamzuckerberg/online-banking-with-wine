# 招商银行

# 摘要 #
## 个人银行大众版 ##
  * 登录入口: https://pbsz.ebank.cmbchina.com/CmbBank_GenShell/UI/GenShellPC/Login/Login.aspx
  * 在Wine Microsoft IE6 下 : 正常显示ActiveX控件, 暂无帐号进行进一步测试
  * 在Wine builtin IE 下 : 无法显示ActiveX控件

## 个人银行专业版 ##
  * 登录入口： http://www.cmbchina.com/cmbpb/v36/pb.htm
  * 在Wine Microsoft IE6 下
  * 在Wine builtin IE 下 `

## i理财大众版 ##
  * 登录入口： https://pbsz.ebank.cmbchina.com/CmbBank_GenShell/UI/GenShellPC/NetBankAcc/Login.aspx
  * 在Wine Microsoft IE6 下
  * 在Wine builtin IE 下 `

## 电子商务专业版 ##
  * 客户端: http://szdl.cmbchina.com/download/PBBS/PBBusinessSetup.exe
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，[网银]不支持Linux和Mac,若有需要请向 [网银] [投诉或建议] 。**

## 企业银行U-BANK ##
  * 登录入口： http://www.cmbchina.com/corporate/firmbank/
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，[网银]不支持Linux和Mac,若有需要请向 [网银] [投诉或建议] 。**



# 控件列表 #
([如何获取控件?](getObject.md))

  * ### NetBankUser\_Ctrl ###

```
<object 
        id="NetBankUser_Ctrl" 
        classid="clsid:0CA54D3F-CEAE-48AF-9A2B-31909CB9515D"
        codebase="https://site.cmbchina.com/download/CMBEdit.cab#version=1,2,0,1" 
        width="100px" height="20px">
</object>
```

  * ### DebitCardNo\_Ctrl ###

```
<object 
        id="DebitCardNo_Ctrl" 
        classid="clsid:0CA54D3F-CEAE-48AF-9A2B-31909CB9515D" 
        codebase="https://site.cmbchina.com/download/CMBEdit.cab#version=1,2,0,1" 
        width="160px" height="20px"></object>
```

  * ### DebitCardQueryPwd\_Ctrl ###

```
<object 
        id="DebitCardQueryPwd_Ctrl" 
        classid="clsid:0CA54D3F-CEAE-48AF-9A2B-31909CB9515D"         
        codebase="https://site.cmbchina.com/download/CMBEdit.cab#version=1,2,0,1" 
        width="100px" height="20px">
</object>
```

  * ### IdNo\_Ctrl ###

```
<object 
        id="IdNo_Ctrl" 
        classid="clsid:0CA54D3F-CEAE-48AF-9A2B-31909CB9515D" 
        codebase="https://site.cmbchina.com/download/CMBEdit.cab#version=1,2,0,1" 
        width="160px" height="20px">
</object>
```

  * ### 密码输入框:DebitCardQueryPwd\_Ctrl ###

> URL: https://site.cmbchina.com/download/CMBEdit.cab

```
<object
        id="DebitCardQueryPwd_Ctrl"
        classid="clsid:0CA54D3F-CEAE-48AF-9A2B-31909CB9515D"
        codebase="https://site.cmbchina.com/download/CMBEdit.cab#version=1,2,0,1"
        width="180px" height="20px"> 
</object>
```

  * ### BookNo\_Ctrl ###

```
<object 
        id="BookNo_Ctrl" 
        classid="clsid:0CA54D3F-CEAE-48AF-9A2B-31909CB9515D" 
        codebase="https://site.cmbchina.com/download/CMBEdit.cab#version=1,2,0,1" 
        width="160px" height="20px">
</object>
```


# 配置过程 #
```

```
# BUG 列表 #

  * ### 密码输入框无法显示 ###
> http://bugs.winehq.org/show_bug.cgi?id=26027

> 状态: 未修复

> Workround: 暂无

  * ### [bug](bug.md) ###
> http://bugs.winehq.org/show_bug.cgi?id=[]

> 状态: 未修复

> Workround: 暂无

  * ### [bug](bug.md) ###
> http://bugs.winehq.org/show_bug.cgi?id=[]

> 状态: 未修复

> Workround: 暂无

  * ### [bug](bug.md) ###
> http://bugs.winehq.org/show_bug.cgi?id=[]

> 状态: 未修复

> Workround: 暂无

  * ### [bug](bug.md) ###
> http://bugs.winehq.org/show_bug.cgi?id=[]

> 状态: 未修复

> Workround: 暂无

# 投诉渠道 #

**任何第三方测试结果都无法保证绝对可靠，也无法对任何意外负责，建议每一个需要在Linux或Mac平台上使用网银的用户,如果有条件可以选择,请尽量用脚投票,选择上海浦发银行等支持跨平台的网银,可以参考[网上银行兼容性列表](http://goo.gl/Itab7)选择适合自己的银行;若无法选择,请不要放弃向银行投诉，争取银行的官方支持。**


  * 在线投诉
> [在线客服](https://forum.cmbchina.com/pcs/Service.aspx?hdType=Normal&hdToken=%3C%3fxml+version%3d%221.0%22+encoding%3d%22gb2312%22%3f%3E%3CToken%3E%3CIDType%3E8%3C/IDType%3E%3CID%3E%3C/ID%3E%3CCardIDList%3E%3C/CardIDList%3E%3CName%3E%3C/Name%3E%3CFrom%3EE%3C/From%3E%3CSystime%3E20110318+20:23:48%3C/Systime%3E%3CVerify_Type%3EHMAC_SHA1%3C/Verify_Type%3E%3CVerify%3EB%2bTZxKzRhK/pfOOGreDoPK4edGA%3d%3C/Verify%3E%3C/Token%3E)

> _欢迎使用招商银行网上客户服务_

> _非常抱歉，本系统只支持IE浏览器。_


  * 电话服务
> 95555