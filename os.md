这是一个简单的操作系统知识纪录，没有复杂的格式要求，需要记得知识点之类的，只是将自己觉得重要的东西记录下来，看看能不能产生什么想法

# 定义
the operating system is the one program running at all times on the computer—usually called the kernel.


系统的标准库函数封装了内核调用，所以编写程序时不需要再特意编写了
****
# Chapter one--basic organization and overview of computer system
*	harware
*	os
*	app programs
*	users


## User view
单用户系统，多用户协作系统，工作站和服务器，移动终端（触屏），无用户界面设备（智能家居）
## System view
一个和硬件关系紧密的程序，资源分配器
一个用于管理用户程序的执行的程序，防止电脑不当操作以及错误

硬件中断：通过系统总线向cpu发送一个中断信号
软件中断：通过执行系统调用引发中断

在中断服务之后，保存的返回地址被加载到程序计数器中，并且中断的计算恢复，就好像没有发生中断一样

![](C:\Users\Administrator\Desktop\markdown\os\1534774135.png)
