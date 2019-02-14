灯光控制系统
==
*本次作品在实际生活中，已有成熟的商业设备，此作品仅为参加学校电子电路设计竞赛所用。*

·基本要求
--
>随着工业的发展、科技的进步，我们生活中的许多事物逐步步入了自动化、智能化、
便捷化的行列。
因此，灯光遥控装置本着以安全、节能、舒适、高效的目的，使用红外遥控控制、
声控、定时控制、旋钮电位器控制及手机、电脑联网控制灯光，其能够产生立体感、层
次感，营造出舒适的环境，有利人们的身心健康，提高工作效率，同时，还能够应用户
要求，进行调整，改变发光模式，提供个性化的照明方案。
灯光遥控装置还具备多种模式，在与互联网连接后，用户可随时随地通过联网设备
控制系统，为满足用户的不同需求，本产品还可以与智能闹钟、智能台灯等智能设备交
互，能够极大程度地方便用户，满足用户需求。
>


>(1)自主设计流水灯电路的显示设备。流水灯电路
逻辑为：调节旋钮电位器（不局限于旋钮电位
器，机械调节输入即可，本功能只能有唯一的
机械输入设备），顺时针旋转，流水灯燃亮数
量从0盏逐步增加到至少8盏，逆时针旋转逐步
熄灭至0盏:  
 (2) &nbsp;使用红外遥控控制实现(1)项功能:    
 (3) &nbsp;(1)项、(2)项功能相互兼容。    
 (4) &nbsp;使用手机遥控控制实现基本部分的(1)项功能，
且三种遥控控制方式互相兼容；    
(5) &nbsp;增加功能，调节输入设备，使流水灯电路在不
同显示模式下变换；  
(6) &nbsp;&nbsp;增加功能，通过使用输入设备，用点阵模拟画
板，使用旋钮调节画板亮度，实现绘画板功能
（对显示设备任意点光源进行设置）；
>

·设计思路
--
&nbsp;&nbsp;&nbsp; &nbsp;总体以ATMEGA328P-PU为控制单元，构建最小系统。根据芯片手册，需要两个22pf的电容和16M晶振，方可成功起振。  
&nbsp;&nbsp;&nbsp; &nbsp;题目主要要求对多个Led灯光实现控制，单片机IO口个数并不能满足大量Led单独控制的要求，所以在这里采用了74HC595芯片作为IO扩展芯片，方法为将单片机IO作为串行输出到74HC595后再并行输出。这样可以实现以少数IO口控制大量Led。此方法相较于矩阵扫描，优点在于可以在编程的时候简单的实现对单个Led的控制。    
&nbsp;&nbsp;&nbsp; &nbsp;对于灯光亮度的控制，此处采用MOS管作为供电控制。其一是因为74HC595的带载能力并不强，无法驱动多个Led；其二是因为MOS管开关性能好，可以通过PWM实现亮度控制。通过一个IO控制所有Led供电的MOS实现亮度控制功能，再由74HC595芯片实现控制灯光亮暗的功能。   
 &nbsp; &nbsp; &nbsp;对于手机控制的要求，可以通过介绍的ESP8266芯片，搭配自建的物联网平台实现控制，配合Siri或者小爱同学可以语音控制。

原理图及PCB设计
--
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/3D-PCb.png)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/PCB.png)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/Schematic.png)  

作品照片
--
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_0001.JPG)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_0002.JPG)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_0003.JPG)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_9996.JPG)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_9997.JPG)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_9998.JPG)  
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/HER_9999.JPG)  

欢迎关注我的个人公众号
![](https://github.com/h1997l1997/Lighting-control-system/blob/master/qrcode.jpg)
