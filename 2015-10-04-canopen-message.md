#CanOpen报文及Labview应用报告#

韩思阳
2015-10-04

##1. NI CanOpen Library

NI自身提供了CanOpen库，目前更新到[NI-Industrial Communications for CANopen 15.0 - Real-Time OS, Windows](http://www.ni.com/download/ni-industrial-communications-for-canopen-15.0/5438/en/)，该库以封装好的vi格式给出了基本操作的调用，包括：

* Create
* NMT Write
* SDO Read
* SDO Write
* SDO Batch Write
* RPDO Write
* TPDO Read
* ......

支持电机基本操作的*第三方库*有：

* [Maxon motor自己提供支持Labview的库](http://sine.ni.com/nips/cds/view/p/lang/zhs/nid/209755)
* [支持NI9881模块的Ingenia运动控制库](http://sine.ni.com/nips/cds/view/p/lang/zhs/nid/210877)

##2. CanOpen简要组成概述
针对Canopen报文的分析以阅读的datasheet*CiA Draft Standard Proposal 402 CANopen Device Profile Drives and Motion Control*为主要来源，它对运动控制范畴进行了较为详细的定义。

SDO通用的报文格式为

|--命令字--|--主索引--|--从索引--|--数据--|

主索引即为*对象字典(Object Dictionary)*的值

PDO包括

PDO通讯参数：COB-ID、传输类型、禁止时间、定时器周期

PDO映射参数

##3.电机运动及控制主要相关报文
###3.1 电机运动方式

* PROFILE POSITION MODE
* HOMING MODE
* POSITION CONTROL FUNCTION
* NTERPOLATED POSITION MODE
* PROFILE VELOCITY MODE
* PROFILE TORQUE MODE
* VELOCITY MODE

---
索引: 6040h
子索引: 0
映射名称: 控制字
数据长度: 16 U
R/W: R/W
备注:控制通讯状态，例如启动、停止等
---
索引: 6040h
子索引: 0
映射名称: 控制字
数据长度: 16 U
R/W: R/W
备注:控制通讯状态，例如启动、停止等
---

|索引        |子索引           |映射名称  | 数据长度 | R/W | 备注 |
| ----- | -- | :---------------| :--------------:| :---:|:--------------------------------------------------------------------------|
| 6040h | 0 | 控制字 | 16 U | R/W |  控制通讯状态，例如启动、停止等|
| 6041h | 0 | 状态字 | 16 U | RO |  读取当前设备状态，例如启动、停止等|
| 6060h | 0 | 控制模式 | 8Integer | R/W |  调节控制模式，例如速度、位置、转矩等控制模式|
| 6061h | 0 | 控制模式状态 | 8Integer | Ro |  读取控制模式状态，例如速度、位置、转矩等控制模式|
