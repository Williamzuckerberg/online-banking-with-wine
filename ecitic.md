# 中信银行

# 摘要 #
## 个人网银 ##
  * 登录入口: https://e.bank.ecitic.com/perbank5/signIn.do
  * 在Wine Microsoft IE6 下
  * 在Wine builtin IE 下

## 白金社区 ##
  * 登录入口：https://e.bank.ecitic.com/perbank5/signInVip.do
  * 在Wine Microsoft IE6 下
  * 在Wine builtin IE 下

## 公司网银 ##
  * 登录入口：http://bank.ecitic.com/public/
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，[网银]不支持Linux和Mac,若有需要请向 [网银] [投诉或建议] 。**


# 控件列表 #
([如何获取控件?](getObject.md))

  * ### GuardID ###
> URL: https://e.bank.ecitic.com/perbank5/plugs/CNCBGuard.exe
```
<object
        id="GuardID" classid="clsid:1B06CC90-84FF-4A4C-83FC-1327A7C4A9A1">
</object>
```

  * ### CNCBChecker ###
> URL: https://e.bank.ecitic.com/perbank5/download/helpmate/HelpmateSetup.exe
```
<object 
        id="CNCBChecker" 
        classid="clsid:22C54CAA-B109-49A0-B788-2103F486CE96"         
        codebase="PerHelpMate.ocx">
</object>
```

  * ### EPCSP ###
> URL: https://
```
try {
		    var obj2 = "";
			obj2 = new ActiveXObject("CITICSCP.MidInterface.1");
			var tempObjHTML = tempObjHTML + '<OBJECT classid="clsid:4BFE8042-A780-452F-AF17-9A424BE31B02" name="EPCSP" width="0" height="0" id="EPCSP" ></OBJECT>';
		    document.getElementById("objectDivSafe").innerHTML = tempObjHTML; 
		} catch (e) {
			if(confirm("您目前的控件不支持启用保管箱功能，是否重新下载并安装保管箱控件？")){
				var winDsp = 'width='+(screen.availWidth-24)+',height='+(screen.availHeight-50)+',toolbar=no,menubar=no,titlebar=yes,scrollbars=yes,status=yes,' +
				'resizable=yes,location=no,left='+5+',top='+5+',screenx='+0+',screeny='+0;
				window.open( "/perbank5/pwd_show.htm", "secObject", winDsp );
			}
		}	
```

  * ### oEdit1,oEdit2,detecter,Init\_Tool\_FT,Init\_Tool\_GD,EPCSP ###
> URL: https://e.bank.ecitic.com/perbank5/plugs/CNCBSecPkg.exe

```
function controlPwdDisplay( isDiplay ){
	var logonPwdObj = document.getElementById("logonPwdId");
	var usbPwdObj = document.getElementById("usbPwdId");
	var objectDivObj = document.getElementById("objectDivId"); 
	var tempObjHTML = '';
	if( isDiplay ){
		tempObjHTML = '<OBJECT id="detecter" CLASSID="CLSID:2C48F48F-01A6-4593-A678-C7DA83C55719" codebase="SecCtl.cab#Version=1,4,0,0">';
		tempObjHTML = tempObjHTML + '<PARAM NAME="MonitorUsbkey" VALUE="1"/>';
		tempObjHTML = tempObjHTML + '<PARAM NAME="CertificateFilter" VALUE="C=CN, O=CFCA Operation CA, OU=CITICIB, OU=Customers|C=CN, O=CFCA Operation CA2, OU=CNCB, OU=Customers"/>';
		tempObjHTML = tempObjHTML + '<PARAM NAME="MonitorUsbkey" VALUE="1"/>';
		tempObjHTML = tempObjHTML + '</OBJECT>';
		tempObjHTML = tempObjHTML + '<OBJECT classid="clsid:C37F9D60-975D-41f2-A745-4DC934D319AA" id="Process_Protest" name="Process_Protest" height="0" width="0"></OBJECT>';
		tempObjHTML = tempObjHTML + '<OBJECT classid="clsid:399C2756-84D4-4AC5-9E86-288340334FB1" id="Init_Tool_FT" name="Init_Tool_FT" height="0" width="0"></OBJECT>';
		tempObjHTML = tempObjHTML + '<OBJECT classid="clsid:F7465932-3C3D-4da2-8541-406E07C369A9" id="Init_Tool_GD" name="Init_Tool_GD" height="0" width="0"></OBJECT>';
		//tempObjHTML = tempObjHTML + '<OBJECT classid="clsid:4BFE8042-A780-452F-AF17-9A424BE31B02" name="EPCSP" width="0" height="0" id="EPCSP" ></OBJECT>';
		objectDivObj.innerHTML=tempObjHTML; 
		logonPwdObj.innerHTML='<object id="oEdit1" class="inputOut_1" onfocus="InitValue(\'oEdit1\',12,6);" width="142" height="100" classid="clsid:CAB6E271-C9B9-4a85-96A0-1B3A19A4E6DE" codebase="keyboardprotection.cab#Version=1,1,0,0" viewastext="viewastext"></object>';
		usbPwdObj.innerHTML='<object id="oEdit2" class="inputOut_1" onfocus="InitValue(\'oEdit2\',12,6);" width="142" height="20" classid="clsid:CAB6E271-C9B9-4a85-96A0-1B3A19A4E6DE" codebase="keyboardprotection.cab#Version=1,1,0,0" viewastext="viewastext" onkeydown="if(event.keyCode==13) logon();"></object>';
		 
	}else{
		logonPwdObj.innerHTML='<input type="password" class="inputOut" size="22" readonly id="oEdit1">';
		usbPwdObj.innerHTML='<input type="password" size="22" class="inputOut" readonly id="oEdit2">';
		objectDivObj.innerHTML='';
	}
}


```
# 配置过程 #
```

```
# BUG 列表 #

  * ### 当页面含有弹出窗口时,只显示弹出窗口,不显示原页面 ###
> http://bugs.winehq.org/show_bug.cgi?id=26405

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
> [url](url.md)

> [url](url.md)

  * 电话服务

> 客服中心：	95558

> 信用卡中心：	4008895558
