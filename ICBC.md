#工行网银测试结果

# 摘要 #
## 个人网上银行 ##
  * 登录入口: https://mybank.icbc.com.cn/icbc/enperbank/index.jsp
  * 在Wine Microsoft IE6 下可以正常登录,可以查询账户,但不能使用捷德u盾 .
  * 在Wine builtin IE 下仍不能正常登录.

## 个人网上银行贵宾版 ##
  * 登录入口： https://vip.icbc.com.cn/icbc/enperbank/index.jsp

## 企业网上银行普及版 ##
  * 登录入口： https://corporbank-simp.icbc.com.cn/icbc/normalbank/index.jsp
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，但工行网银尚不支持Linux和Mac,若有需要请向工行[投诉或提议](http://code.google.com/p/online-banking-with-wine/wiki/ICBC#投诉渠道)。**

## 企业网上银行 ##
  * 登录入口： https://corporbank.icbc.com.cn/
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，但工行网银尚不支持Linux和Mac,若有需要请向工行[投诉或提议](http://code.google.com/p/online-banking-with-wine/wiki/ICBC#投诉渠道)。**



# 控件列表 #
([如何获取控件?](getObject.md))


  * ### 密码输入框:safeEdit1 ###
> URL: https://mybank.icbc.com.cn/icbc/newperbank/AxSafeControls.cab#version=1,0,0,13
```
<object
        id="safeEdit1" classid="CLSID:73E4740C-08EB-4133-896B-8D0A7C9EE3CD" 
        codebase="/icbc/newperbank/AxSafeControls.cab#version=1,0,0,13" 
        width="145" height="21"
        onkeyup="getfocus1(&quot;KeyPart&quot;)">
</object>
```

  * ### 验证码输入框:KeyPart ###
> URL: https://mybank.icbc.com.cn/icbc/newperbank/AxSafeControls.cab#version=1,0,0,13
```
<object 
        id="KeyPart" classid="CLSID:73E4740C-08EB-4133-896B-8D0A7C9EE3CD"
        codebase="/icbc/newperbank/AxSafeControls.cab#version=1,0,0,13"       
        width="40" height="28" 
        onkeyup="if(window.event.keyCode==13) mySubmit();">
</object>
```

  * ### safeSubmit1 ###
> URL: https://mybank.icbc.com.cn/icbc/newperbank/AxSafeControls.cab#version=1,0,0,13
```
<object 
        id="safeSubmit1" classid="CLSID:8D9E0B29-563C-4226-86C1-5FF2AE77E1D2"
        codebase="/icbc/newperbank/AxSafeControls.cab#version=1,0,0,7"
        style="HEIGHT: 0px; WIDTH: 0px" viewastext="">
</object>
```

  * ### objectForDetectPlugin ###
> URL: https://mybank.icbc.com.cn/icbc/NetSign.dll

```
try{		
    document.all.safeSubmit1.reset();
}
catch(Exception){
    document.getElementById("axsafetip").innerHTML = "<table bgcolor=\"#ffffcc\" cellspacing=\"0\" cellpadding=\"0\"><td><font color=\"#FF6600\">如果无法输入密码，请根据ie弹出提示进行控件安装。</font></td></tr></table>"
}

function hasInstallNetSign12(){
    var CLSID=""; 	
    var pluginDiv = document.createElement("<div id=\"pluginDiv\" style=\"display:none\"></div>") 	
    document.body.insertBefore(pluginDiv); 	
    pluginDiv.innerHTML = '<object id="objectForDetectPlugin" classid="CLSID:'+ '62B938C4-4190-4F37-8CF0-A92B0A91CC77' +'"></object>'; 	
    try {
        if(eval("objectForDetectPlugin." + "base64Out") == undefined) {
            pluginDiv.removeNode(true);//删除pluginDiv及其所有的子元素 		
        }
        else {				
            pluginDiv.innerHTML = '<object id="objectForDetectPlugin" classid="CLSID:'+ '62B938C4-4190-4F37-8CF0-A92B0A91CC77' +'" codebase="/icbc/NetSign.dll#version=1,2,2,9"></object>'; 
        } 	
    } 	
    catch(e){
    } 
}
```
# 配置过程 #

  1. 安装mfc42
```
$ winetricks -q mfc42
```
  1. 复制[scarddlg.dll](http://goo.gl/1rgdT)
```
$ cp scarddlg.dll ~/.wine/drive_c/windows/system32
```
  1. 安装安全控件
```
$ wget --timestamping 'https://mybank.icbc.com.cn/icbc/newperbank/AxSafeControls.cab#version=1,0,0,13'
$ cabextract AxSafeControls.cab
$ regsvr32 InputControl.dll SubmitControl.dll
```
# BUG 列表 #

  * ### 安装安全控件需要 scarddlg.dll , Wine 尚未实现这个dll . ###
> 仅需要一个空的dll就可以骗过安装程序.

> http://bugs.winehq.org/show_bug.cgi?id=26026

> 状态: 未修复

> Workround: 复制scarddlg.dll到system32文件夹

  * ### Wine buitin IE 打开工行登录页面会崩溃(0字节网页) ###
> http://bugs.winehq.org/show_bug.cgi?id=25999

> 状态: 已经提交补丁,等待官方收录

> Workround: [下载mshtml.dll.so](http://code.google.com/p/online-banking-with-wine/downloads/detail?name=mshtml.dll.so&can=2&q=#makechanges)
  * ### ~~Wine buitin IE 打开工行登录页面会崩溃~~ ###
> ~~与上一个bug不同,这个暂时原因不明,尚在排查当中~~

> 状态: 已修复

> 2011-3-13更新:已查明,IE打开含有超过3个控件的页面会崩溃

> 2011-3-13更新2: 已修复

> http://bugs.winehq.org/show_bug.cgi?id=26391

  * ### ~~无法显示工行登录页面的控件, 原因是Wine buitin IE 不支持大写的CLSID~~ ###
> http://bugs.winehq.org/show_bug.cgi?id=26000

> 状态: 将在下一版本的wine-gecko中修复

> 2011-3-11更新: [Wine Gecko 1.2.0 RC1](http://www.winehq.org/pipermail/wine-devel/2011-March/089187.html) 已修复

> Workround: 暂无

  * ### 无法显示图片验证码 ###
```
https://mybank.icbc.com.cn/servlet/com.icbc.inbs.person.servlet.Verifyimage2?randomKey=1299899662433135571&imageAlt=Refresh%20verification%20code
```
```

<img src="/servlet/com.icbc.inbs.person.servlet.Verifyimage2?disFlag=2&randomKey=1299899662433135571" 
border="0" 
onclick="parent.refreshVerifyimage();return false;" 
style="CURSOR: hand" 
alt="Refresh verification code"/>
</div>
</html>
```

> 状态: 排查中
> http://bugs.winehq.org/show_bug.cgi?id=26392

  * ### 无法使用u盾 ###
> http://bugs.winehq.org/show_bug.cgi?id=25820

> 状态: 未修复, 等待 Wine1.4支持Windows原生USB驱动

> Workround: 暂无

  * ### ~~加载控件时调用不存在的函数 msvcrt.dll.snwprintf\_s 引起崩溃~~ ###
> http://code.google.com/p/winetricks/issues/detail?id=9

> 状态: 已修复

  * ### builtin IE 无法执行Activex控件中的函数 ###
> http://bugs.winehq.org/show_bug.cgi?id=26546

> 状态: 未修复


# 投诉渠道 #

**任何第三方测试结果都无法保证绝对可靠，也无法对任何意外负责，建议每一个需要在Linux或Mac平台上使用网银的用户,如果有条件可以选择,请尽量用脚投票,选择上海浦发银行等支持跨平台的网银,可以参考[网上银行兼容性列表](http://goo.gl/Itab7)选择适合自己的银行;若无法选择,请不要放弃向银行投诉，争取银行的官方支持。**


  * 在线投诉
> [个人客户投诉登记表](http://www.icbc.com.cn/ICBC/%E5%AE%A2%E6%88%B7%E6%8A%95%E8%AF%89/%E4%B8%AA%E4%BA%BA%E5%AE%A2%E6%88%B7%E6%8A%95%E8%AF%89%E7%99%BB%E8%AE%B0%E8%A1%A8.htm)

> [单位客户投诉登记表](http://www.icbc.com.cn/ICBC/%E5%AE%A2%E6%88%B7%E6%8A%95%E8%AF%89/%E5%8D%95%E4%BD%8D%E5%AE%A2%E6%88%B7%E6%8A%95%E8%AF%89%E7%99%BB%E8%AE%B0%E8%A1%A8.htm)

  * 电话服务

24小时全国电话服务热线：95588

24小时贵宾服务专线：400-66-95588（面向财富卡、理财金卡、白金卡及信用卡金卡客
户，目前已在除上海、浙江和广东以外的全国各地区开通）

  * 短信客服

发送手机短信“LTK+咨询内容”至95588