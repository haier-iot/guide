

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

## 获取非设备类组件和属性功能列表


## 根据中类组件属性ID查询属性信息


## 获取组件信息接口


## 查询场景的规则信息


## 查询模板场景基本信息



