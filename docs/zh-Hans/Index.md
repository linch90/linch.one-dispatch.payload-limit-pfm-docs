# 系统概述

航班限座是一款通过调用[SCAP](https://www.iata.org/en/publications/store/standard-computerized-airplane-performance--scap-/)标准的性能内核软件进行**航班限载运算**的系统。

## 演示数据源

1. **气象预报源**

   采用[openweathermap.org](https://openweathermap.org/)网站的[5 Day / 3 Hour Forecast](https://openweathermap.org/forecast5)接口，获取未来 5 天的 3 小时间隔的气象数据，作为性能计算的气象源。

   实际的气象预报源可根据航空公司的实际需求，进行具体对接。

2. **航班演示数据**

   采用[民用航空预先飞行计划管理系统](https://pre-flight.cn)的*国内*、_港澳台地区_、*国际*航班计划(当前航季: 2022 夏秋)，生成航班演示数据。

3. **机型与飞机演示数据**

   该数据为系统随机生成的数据，仅供系统演示，不可作为实际生产使用数据。

4. **航线固定油**

   该数据为系统随机生成的数据，仅供系统演示，不可作为实际生产使用数据。

5. **机型数据库**

   机型数据库为空客、庞巴迪、商飞进行[SCAP](https://www.iata.org/en/publications/store/standard-computerized-airplane-performance--scap-/)性能计算所必须的内核文件。

## 系统支持机型

系统目前可对下列机型型别进行运算：

1. 空客
   1. A320-214 [ CFM56-5B4 ]
   2. A320-271 [ PW1127G-JM ]
2. 庞巴迪
   1. CRJ900 [ CF34-8C5 ]
3. 商飞
   1. ARJ21-700ER [ CF34-10A ]

## 批量与单次运算

1.  批量运算

    系统支持对未来 5 天的航班进行批量航班限座运算(基于[**气象预报源**](#演示数据源))，制定航班限座通知书，提前做出航班限座决策。

2.  单次运算

    系统提供单次性能计算接口，输出最大起飞重量、最大着陆重量、V1、VR、V2 等数据，供其他业务系统对接。目前支持机型请参见[系统支持机型](#系统支持机型)
