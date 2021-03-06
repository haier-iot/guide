

# 智家APP（Portal）

!> **更新时间**：{docsify-updated}  

## 模板场景是否可启用

> 基本信息

?> **接入地址：** `/iftttscene/component/getById`</br>
**HTTP Method：** POST

**接口描述**

```
{
    "retCode":"00000",
    "retInfo":"成功",
    "data":
        {
            "9c6716fa26da44ce8163951d650db839":false,
            "f96b7bb579544a7da192a4999ed712da":false,
            "0293edff46354369a7214ced4f53e7a5":false,
            "e8f531ca3fa54598b1fa7323c68f87f5":false,
            "f351aefb23e04465940ccfdc59e77b15":false
        }
}

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|

**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
productCodeList|string[]|必须|&nbsp;|&nbsp;|item 类型: string|
sceneIdList|string[]|必须|&nbsp;|&nbsp;|item 类型: string|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode|string|必须|&nbsp;|返回码|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object[]|必须|&nbsp;|返回数据|item 类型: object|

## 获取型号支持的功能信息


> 基本信息

?> **接入地址：** `/https://api.haigeek.com/adc/scenePortal/cmpt/getModelPropList`</br>
**HTTP Method：** POST

**接口描述**

```
入参：
{
"componentId": "3019f113965989d5435be2e252c37505",
"functionId": "bf8d58f02b9bc0888b3e3a06044632c4",
"functionVal":"",
"productCodeList": ["AA9ZQ3015AA"]
}出参：
{
"retCode": "00000",
"retInfo": "成功",
"data": [{
"id": "bf8d58f02b9bc0888b3e3a06044632c4",
"midtypeCode": "140ee",
"typeId": "201892472082410014ee1f59c420c50000001678a5ce52b5095cfdb58f0d1440",
"model": "KFR-26GW/15DDA22AU1套机",
"productCode": "AA9ZQ3015AA",
"propClass": "message",
"propName": "event3",
"description": "事件3",
"functionName": "event3",
"functionDesc": "事件3",
"propFixer": "设置为",
"readable": true,
"writable": false,
"whenLabel": true,
"thenLabel": false,
"propSort": 2,
"ifNeedAuth": "2",
"ifLabel": "0",
"props": [{
"propClass": "null",
"propName": "setIntValue",
"propSort": 0,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "setMode",
"propSort": 1,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "setHMS",
"propSort": 2,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "setMS",
"propSort": 3,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "setFloatValue",
"propSort": 4,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "onOffStatus",
"propSort": 5,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "currentTemperature",
"propSort": 6,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "stringTest",
"propSort": 7,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "onOffLight",
"propSort": 8,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "maxIntValue",
"propSort": 9,
"ifLabel": "0",
"exchangeType": "0"
},
{
"propClass": "null",
"propName": "setYMD",
"propSort": 10,
"ifLabel": "0",
"exchangeType": "0"
}]
}]
}

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|
clientId|XXXXXXXX-XXXXXXXXXXXX|是|&nbsp;|&nbsp;|
appVersion|XX.XX.XX.XXXXX|是|&nbsp;|&nbsp;|
sequenceId|sdfsadf|是|&nbsp;|&nbsp;|
accessToken|TGT30O0ODH35RYSY2KUI7LALCJRI90|是|&nbsp;|&nbsp;|
language|zh-cn|是|&nbsp;|&nbsp;|
timezone|+8|是|&nbsp;|&nbsp;|
sign|${sign}|是|&nbsp;|&nbsp;|
timestamp|${timestamp}|是|&nbsp;|&nbsp;|
appId|MB-UZHSH-0000|是|&nbsp;|&nbsp;|
appName	|adc|是|&nbsp;|&nbsp;|
appKey	|f50c76fbc8271d3261e1f6b5973f54585|是|&nbsp;|6bda204e2fa884c175fde09f185ec790|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
componentId|string|必须|&nbsp;|组件id|&nbsp;|
functionId|string|必须|&nbsp;|功能id|&nbsp;|
functionVal|string|必须|&nbsp;|&nbsp;|&nbsp;|
productCodeList|string|必须|&nbsp;|产品编码列表|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                  ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ id|string|必须|&nbsp;|id|&nbsp;|
``` ```├─ midtypeCode|string|必须|&nbsp;|中类编码|&nbsp;|
``` ```├─ prodtypeCode|string|必须|&nbsp;|产品类型编码|&nbsp;|
``` ```├─ typeId|string|必须|&nbsp;|typeId|&nbsp;|
``` ```├─ model|string|必须|&nbsp;|型号|&nbsp;|
``` ```├─ productCode|string|必须|&nbsp;|成品编码|&nbsp;|
``` ```├─ propClass|string|必须|&nbsp;|属性类别|&nbsp;|
``` ```├─ propName|string|必须|&nbsp;|属性标识名称|&nbsp;|
``` ```├─ description|string|必须|&nbsp;|属性标识显示名称|&nbsp;|
``` ```├─ functionName|string|必须|&nbsp;|属性功能标识名称|&nbsp;|
``` ```├─ functionDesc|string|必须|&nbsp;|属性功能标识描述|&nbsp;|
``` ```├─ propFixer|string|必须|&nbsp;|属性修饰词|&nbsp;|
``` ```├─ propValType|string|必须|&nbsp;|取值类型|&nbsp;|
``` ```├─ variants|string|必须|&nbsp;|取值范围|&nbsp;|
``` ```├─ defaultValue|string|必须|&nbsp;|默认值|&nbsp;|
``` ```├─ propVal|string|必须|&nbsp;|取值|&nbsp;|
``` ```├─ readable|string|必须|&nbsp;|是否可读|&nbsp;|
``` ```├─ writeType|string|必须|&nbsp;|写类型|&nbsp;|
``` ```├─ attrLabel|string|必须|&nbsp;|模型/模板 （创建硬件 高级模式选模板，标准模式选模型）|&nbsp;|
``` ```├─ whenLabel|string|必须|&nbsp;|是否作为条件|&nbsp;|
``` ```├─ thenLabel|string|必须|&nbsp;|是否作为动作|&nbsp;|
``` ```├─ propSort|string|必须|&nbsp;|排序|&nbsp;|
``` ```├─ ifNeedAuth|string|必须|&nbsp;|是否需要授权 1 需要授权 2 不需要授权。|&nbsp;|
``` ```├─ props|object[]|必须|&nbsp;|&nbsp;|item 类型: object|
```   ```├─ propClass|string|必须|&nbsp;|属性类别|&nbsp;|
```   ```├─ propName|string|必须|&nbsp;|属性名称|&nbsp;|
```   ```├─ propVal|string|必须|&nbsp;|属性值|&nbsp;|

## 获取型号功能


> 基本信息

?> **接入地址：** `/https://api.haigeek.com/adc/scenePortal/cmpt/getModelPropByProductCode`</br>
**HTTP Method：** POST

**接口描述**

```
入参：
{
"productCode": "DH1WK1A33"
}

出参：
{
"retCode": "00000",
"retInfo": "成功",
"data": [{
"id": "E210C45F0E5848319DC31964511DAD15",
"midtypeCode": "03011",
"prodtypeCode": "A178",
"typeId": "2054a01b15d2960c0311a3bb8ed90c000000eb75e6e613eb2df5f5ee17974640",
"model": "50T75",
"productCode": "DH1WK1A33",
"propClass": "message",
"propName": "eventContain",
"description": "事件多参数",
"functionName": "eventContain",
"functionDesc": "事件多参数",
"propFixer": "设置为",
"thenLabel": true,
"ifNeedAuth": "2",
"ifLabel": "0",
"props": [{
"propName": "windSpeed"
},
{
"propName": "targetTemperature"
},
{
"propName": "targetHumidity"
},
{
"propName": "onOffStatus"
}]
}]
}

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
productCode|string|必须|&nbsp;|成品编码|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ sysProps|object|必须|&nbsp;|app用系统属性|&nbsp;|
```   ```├─ id|string|必须|&nbsp;|成品编码|&nbsp;|
```   ```├─ componentId|string|必须|&nbsp;|组件id|&nbsp;|
```   ```├─ componentType|string|必须|&nbsp;|组件类型（MODEL 型号组件）|&nbsp;|
``` ```├─ conditions|object|必须|&nbsp;|条件属性集合|&nbsp;|
```   ```├─ propId|string|必须|&nbsp;|单命令：属性主键；组命令：组命令功能主键|&nbsp;|
```   ```├─ propClass|string|必须|&nbsp;|属性类别|&nbsp;|
```   ```├─ desc|string|必须|&nbsp;|单命令：属性标识显示名称；组命令：组命令功能标识显示名称|&nbsp;|
```   ```├─ fixer|string|必须|&nbsp;|属性修饰词|&nbsp;|
```   ```├─ splitFunc|string|必须|&nbsp;|拆分标识 0：不拆，1：拆分|&nbsp;|
```   ```├─ propSort|string|必须|&nbsp;|排序|&nbsp;|
```   ```├─ ifNeedAuth|string|必须|&nbsp;|是否需要授权 1 需要授权 2 不需要授权（音响）|&nbsp;|
```   ```├─ propName|string|必须|&nbsp;|功能标识|&nbsp;|
```   ```├─ functionName|string|必须|&nbsp;|组命令标识|&nbsp;|
```   ```├─ ifLabel|string|必须|&nbsp;|否启用标签：0:否，1：是|&nbsp;|
```   ```├─ props|object[]|必须|&nbsp;|&nbsp;|item 类型: object|
```     ```├─ propId|string|必须|&nbsp;|属性主键|&nbsp;|
```     ```├─ fixer|string|必须|&nbsp;|属性修饰词|&nbsp;|
```     ```├─ propName|string|必须|&nbsp;|属性标识名称|&nbsp;|
```     ```├─ desc|string|必须|&nbsp;|属性标识显示名称|&nbsp;|
```     ```├─ functionName|string|必须|&nbsp;|属性功能标识名称|&nbsp;|
```     ```├─ propValType|string|必须|&nbsp;|取值类型|&nbsp;|
```     ```├─ variants|string|必须|&nbsp;|取值范围|&nbsp;|
```     ```├─ defaultValue|string|必须|&nbsp;|默认值|&nbsp;|
```     ```├─ defaultValueDesc|string|必须|&nbsp;|默认值描述|&nbsp;|
``` ```├─ actions|object|必须|&nbsp;|动作属性集合|&nbsp;|
```   ```├─ propId|string|必须|&nbsp;|单命令：属性主键；组命令：组命令功能主键|&nbsp;|
```   ```├─ propClass|string|必须|&nbsp;|属性类别|&nbsp;|
```   ```├─ desc|string|必须|&nbsp;|单命令：属性标识显示名称；组命令：组命令功能标识显示名称|&nbsp;|
```   ```├─ fixer|string|必须|&nbsp;|属性修饰词|&nbsp;|
```   ```├─ splitFunc|string|必须|&nbsp;|拆分标识 0：不拆，1：拆分|&nbsp;|
```   ```├─ propSort|string|必须|&nbsp;|排序|&nbsp;|
```   ```├─ ifNeedAuth|string|必须|&nbsp;|是否需要授权 1 需要授权 2 不需要授权|&nbsp;|
```   ```├─ propName|string|必须|&nbsp;|功能标识|&nbsp;|
```   ```├─ functionName|string|必须|&nbsp;|组命令标识|&nbsp;|
```   ```├─ ifLabel|string|必须|&nbsp;|否启用标签：0:否，1：是|&nbsp;|
```   ```├─ props|object[]|必须|&nbsp;|&nbsp;|item 类型: object|
```     ```├─ propId|string|必须|&nbsp;|属性主键|&nbsp;|
```     ```├─ fixer|string|必须|&nbsp;|属性修饰词|&nbsp;|
```     ```├─ propName|string|必须|&nbsp;|属性标识名称|&nbsp;|
```     ```├─ desc|string|必须|&nbsp;|desc|&nbsp;|
```     ```├─ functionName|string|必须|&nbsp;|属性功能标识名称|&nbsp;|
```     ```├─ propValType|string|必须|&nbsp;|取值类型|&nbsp;|
```     ```├─ variants|string|必须|&nbsp;|取值范围|&nbsp;|
```     ```├─ defaultValue|string|必须|&nbsp;|默认值|&nbsp;|
```     ```├─ defaultValueDesc|string|必须|&nbsp;|默认值描述|&nbsp;|


## 查询型号支持场景状态列表

> 基本信息

?> **接入地址：** `https://api.haigeek.com/adc/scenePortal/cmpt/getModelSupportSceneStateList`</br>
**HTTP Method：** POST

**接口描述**

```
{
"retCode": "00000",
"retInfo": "成功",
"data": [{
    "productCode": "FY0015009",
    "supportSceneStatus": true,
    "sceneType": 1
},
{
    "productCode": "FY001LM0L",
    "supportSceneStatus": true,
    "sceneType": 1
}]
}

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
type|string|必须|&nbsp;|型号状态：0、未上线 1、已上线  2、全部状态（包括已上线未上线）|&nbsp;|
productCodeList|string[]|必须|&nbsp;|成品编码列表|item 类型: string|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object[]|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ productCode|string|必须|&nbsp;|成品编码|&nbsp;|
``` ```├─ supportSceneStatus|boolean|必须|&nbsp;|是否支持显示|&nbsp;|
``` ```├─ sceneType|string|必须|&nbsp;|场景类型：1、条件  2、 动作  3 条件和动作都支持|&nbsp;|



## 根据中类组件属性ID查询属性信息（为了兼容app老服务暂时返回常量）

> 基本信息

?> **接入地址：** ` https://api.haigeek.com/adc/scenePortal/cmpt/getPropByIds`</br>
**HTTP Method：** POST

**接口描述**

```
为了兼容app老服务暂时返回常量

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
propId|string|必须|&nbsp;|属性id|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-



## 获取非设备类组件和属性功能列表



> 基本信息

?> **接入地址：** `https://api.haigeek.com/adc/scenePortal/cmpt/getCmptPropList`</br>
**HTTP Method：** POST

**接口描述**

```
{
"retCode": "00000",
"retInfo": "成功",
"data": {
    "componentId": "3404d74e0ede4f33ba8ab72e11de8eac",
    "componentType": "WEATHER",
    "componentName": "当前天气",
    "componentDesc": "当前天气",
    "props": [{
        "propId": "3d7f098d96bd48098168b0f0bf1b206b",
        "fixer": "设置为",
        "propName": "pm25",
        "desc": "室外PM2.5",
        "functionName": "pm25",
        "propValType": "int",
        "variants": "{"unit":"ug/m³","minValue":0,"step":5,"maxValue":2000}"
    },
    {
        "propId": "b140f5d6dfb4464e9c4b8548eed77a6d",
        "fixer": "设置为",
        "propName": "temperature",
        "desc": "室外温度",
        "functionName": "temperature",
        "propValType": "int",
        "variants": "{"unit":"℃","minValue":-60,"step":1,"maxValue":60}"
    },
    {
        "propId": "c4c49da19d104cf892b53f674de72c7e",
        "fixer": "设置为",
        "propName": "humidy",
        "desc": "室外湿度",
        "functionName": "humidy",
        "propValType": "int",
        "variants": "{"unit":"%","minValue":0,"step":1,"maxValue":100}"
    }]
    }
}

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
type|string|必须|&nbsp;|组件类型（WEATHER 天气；TIMER  定时；DELAY 延时；GEOFENCE 地理围栏）|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
componentId```                         ```|string|必须|&nbsp;|组件id|&nbsp;|
componentName|string|必须|&nbsp;|组件名称|&nbsp;|
componentType|string|必须|&nbsp;|组件类型|&nbsp;|
props|object[]|必须|&nbsp;|子属性|item 类型: object|
``` ```├─ name|string|必须|&nbsp;|属性名称|&nbsp;|
``` ```├─ type|string|必须|&nbsp;|属性类别，可取值：property alarm operation group(组命令)|&nbsp;|
``` ```├─ valType|string|必须|&nbsp;|为property或者为operation时，可取double int bool enum；type为alarm,该字段为null|&nbsp;|
``` ```├─ variants|string|必须|&nbsp;|取值范围|&nbsp;|
``` ```├─ whenLabel|boolean|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ thenLabel|boolean|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ sort|integer|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ description|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ createTime|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ updateTime|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ componentId|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ defaultValue|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ icon|string|必须|&nbsp;|&nbsp;|&nbsp;|


## 根据中类组件属性ID查询属性信息

> 基本信息

?> **接入地址：** `  https://api.haigeek.com/adc/scenePortal/cmpt/getPropById`</br>
**HTTP Method：** POST

**接口描述**

```

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
propId|string|必须|&nbsp;|属性id|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-


## 获取组件信息接口


> 基本信息

?> **接入地址：** ` https://api.haigeek.com/adc/scenePortal/cmpt/getById`</br>
**HTTP Method：** POST

**接口描述**

```

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
id|string|必须|&nbsp;|组件id|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ id|string|必须|&nbsp;|组件id|&nbsp;|
``` ```├─ componentName|string|必须|&nbsp;|组件名称|&nbsp;|
``` ```├─ componentType|string|必须|&nbsp;|组件类型|&nbsp;|
``` ```├─ componentDesc|string|必须|&nbsp;|组件描述|&nbsp;|
``` ```├─ typeId|string|非必须|&nbsp;|typeid|&nbsp;|
``` ```├─ model|string|非必须|&nbsp;|型号名称|&nbsp;|
``` ```├─ prodtypeCode|string|必须|&nbsp;|组件类型编码|&nbsp;|
``` ```├─ prodtypeName|string|非必须|&nbsp;|组件类型名称|&nbsp;|
``` ```├─ DeviceDesc|object|非必须|&nbsp;|中类组件描述信息|&nbsp;|
```   ```├─ bigClass|string|非必须|&nbsp;|大类|&nbsp;|
```   ```├─ middleClass|string|非必须|&nbsp;|中类|&nbsp;|
```   ```├─ id|string|非必须|&nbsp;|id|&nbsp;|


## 查询场景的规则信息


> 基本信息

?> **接入地址：** `https://api.haigeek.com/adc/scenePortal/scene/app/rule/getById`</br>
**HTTP Method：** POST

**接口描述**

```

```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
ruleId|string|必须|&nbsp;|场景规则Id|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ id|string|必须|&nbsp;|成品编码|&nbsp;|
``` ```├─ rule|string|必须|&nbsp;|规则名称|&nbsp;|
``` ```├─ salience|string|必须|&nbsp;|规则执行优先级数字越大则越先执行|&nbsp;|
``` ```├─ when|object|必须|&nbsp;|条件|&nbsp;|
```   ```├─ conditions|object[]|必须|&nbsp;|&nbsp;|item 类型: object|
```     ```├─ id|string|必须|&nbsp;|条件id|&nbsp;|
```     ```├─ desc|string|必须|&nbsp;|单命令：属性标识显示名称；组命令：组命令功能标识显示名称|&nbsp;|
```     ```├─ stdDesc|string|必须|&nbsp;|属性修饰词|&nbsp;|
```     ```├─ logicalSign|string|必须|&nbsp;|逻辑运算符（枚举类型）|&nbsp;|
```     ```├─ key|string|必须|&nbsp;|&nbsp;|&nbsp;|
```     ```├─ operationSign|string|必须|&nbsp;|关系运算符（枚举类型）|&nbsp;|
```     ```├─ value|string|必须|&nbsp;|&nbsp;|&nbsp;|
```     ```├─ componentId|string|必须|&nbsp;|组件id|&nbsp;|
```     ```├─ componentType|string|必须|&nbsp;|组件类型|&nbsp;|
```     ```├─ groupTag|string|必须|&nbsp;|分组tagID，非设备条件为null|&nbsp;|
``` ```├─ then|object|必须|&nbsp;|动作|&nbsp;|
```   ```├─ actions|object[]|必须|&nbsp;|&nbsp;|item 类型: object|
```     ```├─ id|string|必须|&nbsp;|动作id|&nbsp;|
```     ```├─ type|string|必须|&nbsp;|动作类型|&nbsp;|
```     ```├─ dealyTime|string|必须|&nbsp;|&nbsp;|&nbsp;|
```     ```├─ stdDesc|string|必须|&nbsp;|标准描述|&nbsp;|
```     ```├─ priority|string|必须|&nbsp;|优先级|&nbsp;|
```     ```├─ control|object|必须|&nbsp;|&nbsp;|&nbsp;|
```       ```├─ componentId|string|必须|&nbsp;|组件id|&nbsp;|
```       ```├─ args|object[]|必须|&nbsp;|&nbsp;|item 类型: object|
```         ```├─ name|object|必须|&nbsp;|&nbsp;|&nbsp;|
```           ```├─ id|string|必须|&nbsp;|功能id|&nbsp;|
```           ```├─ value|string|必须|&nbsp;|功能名|&nbsp;|
```           ```├─ desc|string|必须|&nbsp;|功能描述|&nbsp;|
```           ```├─ required|string|必须|&nbsp;|&nbsp;|&nbsp;|
```         ```├─ value|object|必须|&nbsp;|&nbsp;|&nbsp;|
```           ```├─ value|string|必须|&nbsp;|设定值|&nbsp;|
```           ```├─ desc|string|必须|&nbsp;|设定值描述|&nbsp;|
```           ```├─ required|string|必须|&nbsp;|&nbsp;|&nbsp;|


## 查询模板场景基本信息


> 基本信息

?> **接入地址：** `https://api.haigeek.com/adc/scenePortal/scene/findBasicSceneInfo`</br>
**HTTP Method：** POST

**接口描述**

```
```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
appSceneId|string|必须|&nbsp;|场景id|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ id|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ isAccessApp|number|必须|&nbsp;|app是否上架 0-未上架 1-已上架|&nbsp;|
``` ```├─ appSceneSort|integer|必须|&nbsp;|app上场景排序|&nbsp;|
``` ```├─ sourceId|string|必须|&nbsp;|场景来源|&nbsp;|
``` ```├─ sceneAlias|string|必须|&nbsp;|场景别名|&nbsp;|
``` ```├─ sceneDesc|string|必须|&nbsp;|场景描述|&nbsp;|
``` ```├─ sceneName|string|必须|&nbsp;|场景名称|&nbsp;|
``` ```├─ appId|string|必须|&nbsp;|客户端id|&nbsp;|
``` ```├─ auto|string|必须|&nbsp;|是否支持自动实例化|&nbsp;|
``` ```├─ banner|string|必须|&nbsp;|场景banner图URL|&nbsp;|
``` ```├─ canAppTrigger|string|必须|&nbsp;|是否需要APP触发|&nbsp;|
``` ```├─ createTime|string|必须|&nbsp;|创建时间|&nbsp;|
``` ```├─ icon|string|必须|&nbsp;|场景图标URL|&nbsp;|
``` ```├─ storeIcon|string|必须|&nbsp;|场景商店URL|&nbsp;|
``` ```├─ inoutSide|string|必须|&nbsp;|场景标识|&nbsp;|
``` ```├─ keyword|string|必须|&nbsp;|关键字|&nbsp;|
``` ```├─ status|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ video|string|必须|&nbsp;|场景短视频URL|&nbsp;|
``` ```├─ userIdWhiteList|string|必须|&nbsp;|用户id白名单|&nbsp;|
``` ```├─ loginIdWhiteList|string|必须|&nbsp;|登录id白名单|&nbsp;|
``` ```├─ sortList|object[]|必须|&nbsp;|	应用场景分类列表|item 类型: object|
``` ```├─ tagList|object[]|必须|&nbsp;|应用场景标签列表|item 类型: object|
``` ```├─ type|string|必须|&nbsp;|场景类型|&nbsp;|
``` ```├─ updateTime|string|必须|&nbsp;|更新时间|&nbsp;|
``` ```├─ userId|string|必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ version|string|必须|&nbsp;|应用场景版本|&nbsp;|
``` ```├─ triggerType|string|必须|&nbsp;|platform：平台触发，manually：手动触发：timerTrigger 时间触发 weatherTrigger:天气触发|&nbsp;|
``` ```├─ taskInfo|object|必须|&nbsp;|定时策略信息|&nbsp;|
``` ```├─ taskInfoList|object[]|必须|&nbsp;|多个定时策略信息|item 类型: object|



## 根据场景id查询当前场景所在网关设备以及该场景所支持的网关列表


> 基本信息

?> **接入地址：** `/iftttscene/edge/find/gateway-device-of-scene`</br>
**HTTP Method：** POST

**接口描述**

```
{
  "retCode": "00000",
  "retInfo": "返回成功",
  "data": {
    "deviceId": "DC330D3722E1",
    "supportTable": [
      {
        "deviceId": "DC330D3722E1"
      },
      {
        "deviceId": "DC330D6A14BB"
      },
      {
        "deviceId": "0007A8AA464F"
      }
    ]
  }
}
```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
sceneId|string|必须|&nbsp;|场景id|mock: 2012191658176438709924980006936|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|
data|object|必须|&nbsp;|返回数据|&nbsp;|
``` ```├─ deviceId|string|非必须|&nbsp;|&nbsp;|&nbsp;|
``` ```├─ supportTable|object[]|非必须|&nbsp;|&nbsp;|item 类型: object|
```   ```├─ deviceId|string|必须|&nbsp;|app上场景排序|&nbsp;|



## 切换场景运行位置


> 基本信息

?> **接入地址：** `/iftttscene/edge/change-location`</br>
**HTTP Method：** POST

**接口描述**

```
请求参数：
{
  "sceneId": "868086971205000000",
  "familyId": "868086971205111111",
  "sceneLocation": "edge",
  "gatewayId": "DB1230C3F"
}
返回参数：
{
  "retCode": "00000",
  "retInfo": "成功"
}
```
> 请求参数

**Headers** 

参数名称|参数值|是否必须|示例|备注
:-|:-:|:-:|:-:|:-
Content-Type|application/json|是|&nbsp;|&nbsp;|


**Body** 

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
sceneId|string|必须|&nbsp;|场景id|mock: 2012191658176438709924980006936|
familyId|string|必须|&nbsp;|家庭id|&nbsp;|
sceneLocation|string|必须|&nbsp;|场景id|运行位置类型：local、cloud|
gatewayId|string|非必须|&nbsp;|网关id,locationType为local时必填|&nbsp;|

> 返回数据

名称|类型|是否必须|默认值|备注|其他信息
:-|:-:|:-:|:-:|:-:|:-
retCode```                         ```|string|必须|&nbsp;|返回码 00000 成功|&nbsp;|
retInfo|string|必须|&nbsp;|返回信息|&nbsp;|


