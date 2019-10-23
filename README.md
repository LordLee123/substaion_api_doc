# substaion_api_doc
 API document for substation
API DOC FOR SUBSTATION
Data point name

测点名称

Category

种类

Read/ Write

读/写

Unit

单位

Description

描述

Secondary side supply temperature

二次供水温度

MUST

 

R

°C

Temperature of the secondary side circuit supply

二次侧热网供水温度

Secondary side return temperature

二次回水温度

MUST

 

R

°C

Temperature of the secondary side circuit return

二次侧热网回水温度

Secondary side supply pressure

二次供水压力

SHOULD

 

R

MPa

 

Secondary side return pressure

二次回水压力

SHOULD

 

R

Mpa

 

Primary side supply pressure

一次供水压力

SHOULD

R

MPa

 

Primary side return pressure

一次回水压力

SHOULD

R

Mpa

 

Secondary side supply temperature setpoint

二次供水温度设定值

MUST

R/W

°C

Temperature set to the controller for the secondary side supply. Note that this is not the same data point as the actual measurement. This set point is updated by Leanheat control. It should be also possible to read the current setpoint from the interface.

给控制器设定二次侧供水温度。

Primary side supply temperature

一次供水温度

MUST

R

°C

Primary side supply temperature measured at the substation.

在换热站里测量得到的一次侧供水温度

Primary side return temperature

一次回水温度

MUST

R

°C

Primary side return temperature at the substation.

在换热站里测量得到的一次侧回水温度

Outdoor temperature

室外温度

SHOULD

R

°C

Outdoor temperature from the temperature sensor. 

室温传感器测得的室外温度

Position of control valve 1/2/3 etc.

调节阀1/2/3……阀位

MUST

R

 %

Position of the control valve can be used in the predictive maintenance in detecting valve related problems.

调节阀阀位可以用于在预测维护中检测阀门的相关问题。

Control method

控制方式

MUST

R

-

The control method that the controller is following. Supported values:

 

-         “Leanheat”

-         “Local SCADA control”

二次供水温度设定值来自于何处，支持的方式有：

“Leanheat控制”

     “当地SCADA控制”

(修正:  1/0可控/不可控)

(correction: true/faluse  controlled/out of control)

Secondary side supply temperature setpoint calculated by local SCADA

由当地SCADA系统计算得到的二次供水温度设定值

SHOULD

R

°C

Secondary side supply temperature setpoint calculated by local SCADA

由当地SCADA系统计算得到的二次侧供水温度设定点

Secondary side supply water max temperature

二次最大供水温度

SHOULD

R

°C

Max allowed temperature for secondary side supply water.

二次侧供水温度允许的最大值

Secondary side supply water min temperature

二次最小供水温度

SHOULD

R

°C

Min allowed temperature for secondary side supply water.

二次侧供水温度允许的最小值

Total heating power

总热功率

MUST

R

kW

Heating power measured by the heat meter is needed for the best possible results. It provides also value to predictive maintenance.

需要热量表测得的热功率来对结果进行优化，同时也有利于预测性维护。

Total heating consumption

总热耗

MUST

R

MWh

Heating consumption measured by the heat meter is needed for the best possible results. It provides also value to predictive maintenance.

需要热量表测得的热耗来对结果进行优化，同时也有利于预测性维护。

Primary side flow rate

一次侧流量

MUST

R

m3/h

Flow rate measured by the heat meter.

热量表测得的流量

Frequency of circulation pump 1/2/3 etc.

循环泵1/2/3……频率

MUST

R

Hz

 

Secondary side flow rate

二次侧流量

SHOULD

 

R

m3/h

Flow rate measured by the flow meter.

热量表测得的流量

注：1）上表中MUST代表必须要有的采集参数；SHOULD代表最好能有的采集参数。如果现系统中没有相应的参数值，在通讯接口中要预留。

       2）上表中R代表Read，读；W代表Write，写。

 

整理字段说明

包含(Included )

字段名(英)

Data Point Name(english)

描述

Discription

单位

Unit

Time

采集时间

 

Jt_Station_Name

集团站点名称

 

Jt_Station_Number

集团站点编号

 

Jt_Crew_Name

集团机组名称

 

Jt_Crew_Number

集团机组编号

 

TwoGoTemp

Secondary side supply temperature

°C

TwoBackTemp

Secondary side return temperature

°C

TwoGoPress

Secondary side supply pressure

Mpa

TwoBackPress

Secondary side return pressure

Mpa

OneGoPress

Primary side supply pressure

Mpa

OneBackPress

Primary side supply pressure

Mpa

OneGoTemp

Primary side supply temperature

°C

OneBackTemp

Primary side return temperature

°C

ValveFeedBack

Position of control valve 1

%

ControlMethod

Control method

 

OnelHot

Total heating power

kW

OneTotalHot

Total heating consumption

MWh

OneFlow

Primary side flow rate

m3/h

TwoFlow

Secondary side flow rate

m3/h

预留

(Reserved)

OnelHotUnit

the unit of instaneous power

W/Kw/Mw/NULL

OneTotalHotUnit

the unit of accumulated energy

KwH/MwH/Gj/NULL

TwoGoTemp_SetValue

Secondary side supply temperature setpoint

°C

OutTemp

Outdoor temperature

°C

TwoGoTemp_ScadaValue

Secondary side supply temperature setpoint calculated by local SCADA

°C

TwoMaxGoTemp

Secondary side supply water max temperature

°C

TowMinGoTemo

Secondary side supply water min temperature

°C

PumpOneFre

Frequency of circulation pump 1

Hz

 

 

 

函数名称

GetStationNowData()

作用描述

得到换热站实时数据

参数

无

返回值

[{

                      "Time": "2018-4-20 09:08:00",

                      "Jt_Station_Name": "ji chang su she",

                      "Jt_Station_Number": "GRZ060000861",

                      "Jt_Crew_Name": "hang 2 hao lou xi tong",

                      "Jt_Crew_Number": "GJZ06000086101",

                      "TwoGoTemp": 38.68,

                      "TwoBackTemp": 28.18,

                      "TwoGoPress": 0.67,

                      "TwoBackPress": 0.45,

                      "OneGoPress": 0.78,

                      "OneBackPress": 0.48,

                      "OneGoTemp": 48.18,

                      "OneBackTemp": 18.18,

                      "ValveFeedBack": 90,

                      "ControlMethod": 1,

                      "OnelHot": 25.78,

                      "OneTotalHot": 12346.89,

                      "OneFlow": 4.57,

                      "TwoFlow": 5.89,

                       "OnelHotUnit ":NULL,

                       "OneTotalHotUnit ":NULL,

                      "TwoGoTemp_SetValue": -999999,

                      "OutTemp": -999999,

                      "TwoGoTemp_ScadaValue": -999999,

                      "TwoMaxGoTemp": -999999,

                      "TowMinGoTemo": -999999,

                      "PumpOneFre": -999999

}]

 

 

 

 

 

 

函数名称

SendCommand(string json)

作用描述

下发控制命令set down the setpoint

参数

[{

                      "Jt_Crew_Number": "GJZ06000086101",

                      "TwoGoTemp_SetValue": 56.78

}]

返回值

[{

                      "Jt_Crew_Number": "GJZ06000086101",

                      "BackResult": 1

}]

最多1分钟返回结果：

0   --不受控制

1  --控制器执行成功

2  --控制器执行失败

 

 

 

 

 

 

 

 

 

 

 

 

 

 

 

室内温湿度传感器接口

 

1.      上传及采样频率

5分钟采样, 一小时上传 12次采样数据。

 

URL

 Method

 数据格式

备注

https://gw.leanheat.fi/v1

 POST

JSON

产品环境，

接受 温度及湿度

数据

 

 

 

 

 

 

 

 

 

 

 
