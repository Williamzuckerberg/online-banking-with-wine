# 南京银行

# 摘要 #
## 个人网上银行 ##
  * 登录入口: https://ebank.njcb.com.cn:8001/perbank/logon.jsp
  * 在Wine Microsoft IE6 下
  * 在Wine builtin IE 下

## 个人网上银行贵宾版 ##
  * 登录入口：
  * 在Wine Microsoft IE6 下
  * 在Wine builtin IE 下

## 企业网上银行普及版 ##
  * 登录入口：
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，[网银]不支持Linux和Mac,若有需要请向 [网银] [投诉或建议] 。**

## 企业网上银行 ##
  * 登录入口：
  * **不建议使用任何未经工行官方测试的浏览器和操作系统**
  * **Linux和Mac系统比Windows更安全，更适合企业应用，[网银]不支持Linux和Mac,若有需要请向 [网银] [投诉或建议] 。**



# 控件列表 #
([如何获取控件?](getObject.md))


  * ### safeCommit ###
> URL: https://ebank.njcb.com.cn:8001/perbank/ocx/safe.cab#version=2,0,0,0
```
<object 
        classid="CLSID:A3CD7F74-93C9-4BC4-B892-CCDF1514F714" 
        codebase="/perbank/ocx/safe.cab#version=2,0,0,0" 
        id="safeCommit" 
        name="safeCommit" 
        style="HEIGHT: 0PX;WIDTH: 0PX">
</object>
```

  * ### doit ###
> URL: https://ebank.njcb.com.cn:8001/perbank/ocx/SignX.cab
```
<object 
        classid="CLSID:7AA0F60A-7F84-4233-9B84-15E0A9D6DCF1"         
        codebase="/perbank/ocx/SignX.cab" 
        id="doit" viewastext="" 
        width="200" height="40">
</object>
```

  * ### 密码输入框:safeInput ###
> URL: https://ebank.njcb.com.cn:8001/perbank/ocx/safe.cab#version=2,0,0,0

```
<object 
        classid="CLSID:ECCBA953-80E5-11D3-9285-0080ADB811C5" 
        codebase="/perbank/ocx/safe.cab#version=2,0,0,0" 
        id="safeInput" name="tranPwd" 
        width="800" height="20" style="HEIGHT: 20PX; WIDTH: 152PX">
</object>
```

  * ### [?] ###
> URL: https://

```

```
# 配置过程 #
```

```
# BUG 列表 #

  * ### 无法打开登录入口 ###
> http://bugs.winehq.org/show_bug.cgi?id=26476

> 状态: 未修复

> Workround: 暂无

  * ### 载入safeCommit和safeInput都会崩溃 ###
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



  * 短信客服