严重待编辑,欢迎参与!

在Linux平台和Mac平台上通过wine buitin IE使用网银 .



Wine 1.3.9 开始支持ActiveX控件

~~2011年计划发布的 Wine 1.4 将支持Windows原生USB驱动, 这为在Linux上使用U盾提供了可能.~~

参见: [http://wiki.winehq.org/WineReleaseCriteria](http://goo.gl/Ckffn)

本项目的目的是,在Linux或Mac平台上,使用Wine测试网银兼容性,向Wine项目及时汇报bug,若有可能还可以提交补丁.

如果您想帮助测试,请查看[待测试网银列表](http://goo.gl/DwjOv)

  * [待测试网银列表](ListForTest.md)
    * [工商银行](ICBC.md)
    * [招商银行](cmbchina.md)
    * [中信银行](ecitic.md)
    * [农业银行](95599.md)
    * [交通银行](95559.md)
    * [上海农商银行](srcb.md)
    * [顺德农商银行](sdebank.md)
    * [南京银行](njcb.md)
    * [北京农村商业银行](bjrcb.md)
    * [北京银行](bankofbeijing.md)
    * [中国银行](boc.md)
    * [兴业银行](cib.md)
    * [广东发展银行](gdb.md)
    * [中国邮政储蓄银行](psbc.md)
    * [深圳发展银行](sdb.md)
    * [中国光大银行](cebchina.md)
    * [恒丰银行](96569.md)
    * [浙商银行](czbank.md)
    * [平安银行](pingan.md)
    * [上海银行](bankofshanghai.md)
    * [杭州银行](hzbank.md)
    * [徽商银行](hsbank.md)
    * [成都银行](bocd.md)

[Wine使用入门](http://goo.gl/WRkAr)

为什么bug report对于wine如此重要?

为什么要用 [Wine buitin IE](http://wiki.winehq.org/Gecko) 而不用 Wine MSIE ?

如何为wine报告一个bug?

查看当前已经收集的 [bug列表](buglist.md)

如何调试

声明:

本项目是一个非营利项目,由志愿者对国内网银进行测试,任何测试结果都不保证可靠,本项目不对在Wine平台上使用网银出现的任何意外损失负责任.建议每一个需要在Linux或Mac平台上使用网银的用户,如果有条件可以选择,请尽量用脚投票,选择上海浦发银行等支持跨平台的网银,可以参考 [网上银行兼容性列表](http://goo.gl/Itab7) 选择适合自己的银行;若无法选择,请不要放弃向银行投诉，争取银行的官方支持。

其他:

Windows上, 使用np-activex 已经可以支持部分依赖ActiveX的网银
参见:
[在chrome上使用ActiveX控件 (Windows)](http://goo.gl/BWoBD)



关于Wine的商业版:CrossOver


欢迎任何感兴趣的人加入项目,希望可以集中力量,避免重复劳动.
有兴趣的朋友请联系
```
fracting <at> gmail <dot> com
```

欢迎加入网银讨论组[openbanks-discuss](http://groups.google.com/group/non-ie-online-banking),讨论网银相关的技术问题: http://groups.google.com/group/non-ie-online-banking

