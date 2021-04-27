# 模组相关问题

**1. 采用蓝牙模组的设备，绑定时APP端无法找到设备热点，但采用硬件测试工具可以绑定**

?> 答：是由于设备底板与蓝牙模块的握手协议缺少13 帧和14帧。13帧表示模块和设备都休眠，同时模块降低发送广播报文频率；14帧表示模块和设备都休眠



**2. WIFI模组的设备FOTA过程中模块传送升级包给设备底板的结束时间未知**

?> 答：模块接收到设备发送的升级指令后，设备底板发送E5帧到模块，获取固件包（升级包），此时模块会回应E6帧给设备，并发送固件包，但模块不校验升级包大小，所以模块不知道什么时候固件包传输结束，模块只要接收到设备底板E5帧，就会回应E6帧。

**3. 电脑板网络功能开发过程中，E++协议中的FF后面加55的问题**

?> 答：如果传输数据的时候有与帧头FFH相同的数值，则在此数值后面传输一个数值为55H的数据。此数据不计入帧长，但是需要计算入校验和。如果是校验和为FFH，则只是在校验和之后传输一个55H，不计入帧长，也不计算入校验和。

例如：

原本需要传输的数据为：FF FF 0D 01 02 03 04 05 06 02 6D 01 05 FF FF 95。

0D为帧长，是以下数据的个数01 02 03 04 05 06 02 6D 01 05 FF FF 95。

95为校验和，其计算方法为0D+01+02+03+04+05+06+02+6D+01+05+FF+FF=295H，取低字节数据95H。

实际需要传输的数据为：FF FF 0D 01 02 03 04 05 06 02 6D 01 05 FF 55 FF 55 3F。

帧长不变，校验和加两个55H，变为3F。

**4. 电脑板网络功能开发，当模块进入低功耗模式，电脑板不能给模块发送数据**

?> 答：模块进入低功耗模式后，为了避免误唤醒模块，使模块退出低功耗模式，定义电脑板不能给模块发送数据。




