# 上海农商银行

# 摘要 #
## 个人网上银行 ##
  * 登录入口: https://ebank.srcb.com:446/pweb/pbperbank
  * 在CrossOver Microsoft IE6 下 : 控件可以显示,不能登录(总是提示密码必须为六位)
  * 在Wine builtin IE 下 : 控件可以显示
  * 没有帐号,暂不能进一步测试

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
  * ### 密码输入框:powerpass ###
> URL: https://ebank.srcb.com:446/pweb/ocx/shrcb/IBSToolSetup.exe

> URL:

```
<object id="powerpass" 
        codebase="ocx/SRCBPwdEnter_V1.CAB#version=1,0,0,53" 
        classid="clsid:C89D4F25-9EC4-4742-8C4A-1DB9A3AE58E4" 
        width="150" height="22" 
        style="width:150px;height:22px">
</object>
```

  * ### 验证码输入框:[.md](.md) ###
> URL: https://
```
<object 
  
</object>
```

  * ### [?] ###
> URL: https://
```
<object 
  
</object>
```

  * ### [?] ###
> URL: https://

```

```
# 配置过程 #
```
winetricks -q mfc42

```
# BUG 列表 #

  * ### Wine buitin IE 无法打开 https://ebank.srcb.com:446/pweb/pbperbank ###
> http://bugs.winehq.org/show_bug.cgi?id=26467

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

> 24小时客服热线

> 021-962999

> 40069629999


  * 短信客服