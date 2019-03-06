@[TOC](关于黑苹果安装10.14 屏幕只显示部分区域过小问题的解决方法)
## 本人机器配置

处理器	英特尔 Core i7-6700 @ 3.40GHz 四核
主板	微星 B150M PRO-VD (MS-7996) ( 英特尔 Skylake-S - 100 Series/C230 Series 芯片组 Family - A148 )
内存	16 GB ( 三星 DDR4 2133MHz / 金邦 DDR4 2133MHz )
主硬盘	七彩虹 SL300 240GB ( 240 GB / 固态硬盘 )
显卡	AMD Radeon RX Vega 64 ( 8 GB / AMD )
显示器	IPS2480 ( 24 英寸  )
光驱	DiscSoft Virtual 蓝光光驱
声卡	瑞昱 ALC887 @ 英特尔 High Definition Audio 控制器
网卡	瑞昱 RTL8168/8111/8112 Gigabit Ethernet Controller / 微星

## 遇到的问题
1.一开始尝试使用ddmac对分区进行刷写，无奈总是失败，后来参考了网上的各种办法都解决不了，最后干脆重启即可。

2.无论使用懒人镜像还是官方原版镜像，进入安装界面之后都会遇到如下图的问题

如图
![屏幕问题](https://img-blog.csdnimg.cn/20190306175834570.jpeg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZqaDE5OTc=,size_16,color_FFFFFF,t_70)

这个问题导致我无法正确操作安装界面从而无法进行下一步。
## 解决方法1

无意中发现的，在此界面上不停按回车之后，选择左上角启动终端，执行以下命令

```
# shutdown -s now
```

之后电脑应该会进入休眠状态，按下电源开关，电脑就会启动，这时候分辨率恢复正常。可以继续安装。
但是我依然遇到了如下问题。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190306181415399.JPG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZqaDE5OTc=,size_16,color_FFFFFF,t_70)
显示 An error occured installling macOs。经过大佬的提醒，建议我不要安装变色龙处理过的懒人版，而是直接安装官方原版镜像。之后就安装成功了，但仅仅只是安装成功而已。
## 解决方法2
在上述过程安装成功后，我尝试进入苹果系统，但是很遗憾，这次连一点区域都不显示了，直接黑屏。经过我努力的爬贴，最终找到了一个解决方法。
这是十分重要的一步，打开bios，选择windows 操作系统的配置![在这里插入图片描述](https://img-blog.csdnimg.cn/20190306180727186.jpeg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZqaDE5OTc=,size_16,color_FFFFFF,t_70)
在里面勾选Windows 8.1/10 WHQL支持，之后重启。

![在这里插入图片描述](https://img-blog.csdnimg.cn/20190306180741627.jpeg?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZqaDE5OTc=,size_16,color_FFFFFF,t_70)

重启之后，你会很惊讶的发现显示正常了。
## 安装结果
这是我安装好之后的结果，支持双屏。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20190306181255534.JPG?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZqaDE5OTc=,size_16,color_FFFFFF,t_70)
我的clover配置：

https://github.com/fjh1997/hackintosh-clover

参考:
 [1]: clover显卡注入功能详解https://www.cnblogs.com/motoyang/p/5140594.html

