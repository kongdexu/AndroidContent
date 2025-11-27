# Android系统架构

![image](assets/image-20251126155142-atceih9.png "系统架构图")

## Linux Kernel:

　　	Linux内核层：Android平台的基础是Linux内核，最终都是调用底层Linux内核来执行具体功能。

- 启动Kernel的swapper进程（pid=0）：用于初始化进程管理，加载Display, Camera Driver, Binder Driver等相关工作
- 启动kthreadd进程（pid=2）：Linux的系统守护进程，会创建内核工作线程kworder。**kthreadd进程是所有内核进程的鼻祖**

　　‍

## Hardware Abstraction Layer(HAL)

　　	硬件抽象层：HAL包含多个库模块，其中每个模块都为特定类型的硬件组件实现一组接口，比如WIFI/蓝牙模块，当框架API请求访问设备硬件时，Android系统将为该硬件加载相应的库模块

　　‍

## Android Runtime & Native Libraries（系统库）

　　	ART：通过执行DEX文件可在设备运行多个虚拟机，DEX文件是一种转为Android设计的字节码格式文件，经过优化使用的内存很少。ART的主要功能包括：预先（AOT）和即时（JIT）编译，优化垃圾回收（GC），以及调试相关的支持

　　	Native：系统库主要包括init进程fork的用户空间守护进程等。启动init进程（pid=1），是Linux的用户进程，**init进程是所有用户进程的鼻祖**

　　‍

## Framework

　　	应用框架层：framework为APP层提供系统API，包含Zygote，System server， Media Server进程等

- Zygote进程：由init进程fork生成
- System Server进程：由Zygote进程fork而来，**是Zygote孵化的第一个进程，** 负责启动和管理整个java framework，包含ActivityManager，WindowManager等服务。
- Media Srever进程：由init进程fork而来，负责启动和管理整个C++framework，包含AudioFlinger， CameraService等

　　‍

## APP层

　　	应用层：所有的APP进程都是由Zygote进程fork生成的， Zygote进程fork的第一个APP进程是Launcher，这是用户看到的桌面。每个APP至少运行在一个进程上

　　‍
