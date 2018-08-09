!>  **当前版本**：[UWS 账户服务 V1.0.0][account_document_url]  
 **发布时间**：2018-07-19  


## 简介

> 账号服务旨在提供涵盖物联全流程的访问控制服务，为开发者搭建统一的用户登录系统。  

开发者通过集成U+IOT平台账号服务，不仅提供用户账号的注册、登录、找回密码等账户管理服务，同时帮助开发者构建包括物联设备的统一控制、设备与用户权限管理等在内的一致性的IOT系统化管控模式。

![账户图片][account_type]

### 名词解释

-  **海尔OAuth授权**
>  指海尔集团用户中心对外提供的统一账户授权，可使用该种用户授权登录海尔优家IOT平台获取用户设备相关权限，同时具备登录海尔集团旗下相关其他业务服务权限，如海尔商城、海尔社区等；


- **海尔优家 账号**
>  指海尔集团旗下海尔优家平台对外提供的自有物联网账户体系，该账户体系具备绑定/控制等操作海尔物联网家电权限；

若使用海尔OAuth授权登录，按照海尔OAuth接入要求，可同时自动获得海尔优家账号信息；即使用海尔账号的同时获得海尔优家账号；

- **海尔优家 OAuth**
> 指海尔优家对外提供的OAuth服务，需要使用海尔优家账号进行登录授权；

由于海尔账号同时具备海尔优家账号权限，顾也可在该种授权服务下使用 海尔账号尽心登录；  
海尔账号与海尔优家账号单向互通，具备海尔优家 OAuth权限不代表具有海尔集团旗下业务权限；

- **海尔优家 第三方登录**
> 指使用第三方平台账号登录海尔优家平台，如微信、京东、淘宝等；

第三方社交账号支持QQ、微信、微博、豆瓣、人人网账号登录,若有其他第三方平台账号登录需求，可在线反馈;

- **海尔优家 开发者自有账号登录**
> 指开发者已有账户体系，且希望使用自有账户体系登录海尔优家平台；  

海尔优家提供平台间账户对接方案，具有标准OAuth方案、应用前方方案等，该种对接方式需要走线下申请流程，如有需求，可在开发者社区反馈，或通过海尔优家商务BD反馈；

### 功能介绍
**账号基础能力**  
1、	IOT平台账号注册：使用此接口用户可以使用手机或邮箱注册IOT账号，并调用验证码接口获取验证码，进行注册激活  
2、	IOT平台账号登录与退出，进行登录验证获取系统创建的安全令牌（accessToken），系统校验accessToken进行用户退出登录。  
3、	IOT账号验证码申请与验证，使用此接口可以申请和验证手机或邮箱的验证码保证注册、登录的安全性。  

**账号信息相关能力**  
1、	查询IOT平台账号信息，请求获取用户信息（包括id、loginName、email、mobile等用户属性）。
2、	修改IOT平台账号信息，用户主动修改其应用属性信息、用户基础属性等，需要进行权限认证。  

**账号体系关联能力**  
1、	第三方社交账号登录，支持QQ、微信、微博、豆瓣、人人网账号登录。
2、	开发者的自有账号登录，在U+IOT平台生成对应的暗账号并以U+账号身份进行用户授权登录到U+平台，开发者可建立其独立的开发者账号体系。


### 公共结构  
#### UserBase  
描述用户基础信息结构。   
  
| **名称** | 用户基础信息 |&emsp;| UserBase |   
| ------------- |:----------:|:-----:|:--------:|
|**字段名**|**类型**|**说明**|**备注**|  
|id| String | 用户ID |由系统生成|  
|loginName| String | 登录名 |长度为3~15位 不允许使用特殊字符|  
|email| String | 邮箱 |需要符合邮箱格式|    
|mobile| String | 手机号 |需要符合手机号格式|      
|email| String | 邮箱 |0：海尔账号  99：自有账号|  

#### UserProfile  
用户扩展属性。属性不固定的键值对对象，结构如下：  
{  
	"key1":"value1",  
	"key2":"value2",  
	"key3":"value3",  
	 …  
	"keyn":"valuen",  
}  
用于满足各不同应用对用户信息的不同需求。当应用需要扩展用户属性时，可以向云平台用户系统申请，申请时列明需要扩展的属性，并列明每个属性对应的key、类型及长度。  

以下是烤圈应用的用户扩展属性：  
 
 
| **名称** | 用户 | &emsp; |&emsp; | UserProfile |  
| ------------- |:-------------:|:-----:|:-------------:|  
|**字段名**|**类型**|**说明**|**长度**|**备注**|  
|id|String|用户ID|20||  
|nickName|String|昵称|32||  
|userName|String|用户姓名|32||  
|avatar|String|用户头像资源id||&emsp; |  
|points|long|积分|8||  
|focusCount|int|关注数|8||  
|followCount|int|粉丝数|8|&emsp;|  

#### User    
     
| **名称** | 用户属性 |&emsp;| User |
| ------------- |:-------------:|:-----:|:-------------:|  
|**字段名**|**类型**|**说明**|**备注**|  
|userBase|UserBase|用户基本属性对象||  
|userProfile|UserProfile|用户扩展属性|&emsp;|  

## 接口清单


<!-- 注释开始
### 海尔优家 账号  
> API接口总览

| API名称        | 作用          | 是否开放  | 特别说明|
| ------------- |:-------------:|:-----:|:-------------:|
| 海尔账号注册     | 使用手机号或邮箱注册海尔优家平台账号 | 是| 无|  
| 海尔账号激活     | 注册的新用户收到验证码后，使用该接口进行激活操作 | 是| 无|  
| 海尔账号重新发送激活码(注册后) | 使用本接口的前提条件是用户已经注册，但未激活 | 是| 无|  
| 海尔账号注册前申请激活码(新版注册)     | 使用手机号注册的用户可以使用简易注册流程 | 是| 无|  
| 海尔账号注册并登录(新版注册)   | 使用手机号注册的用户可以使用简易注册流程 | 是| 无|  
| 海尔账号登录     | 用户登录成功，安全系统创建安全令牌accessToken，通过header头返回给用户 | 是| 无|  
| 海尔账号退出     | 用户退出Haier U+云平台 | 是| 无|  
| 查询登录用户基础信息     | 根据登录者token，获取登录者用户的基础信息。登录后使用 | 是| 无|  
| 海尔账号申请重置密码     | 当用户需要重置密码时，使用此接口申请重置密码 | 是| 无|  
| 海尔账号重置密码     | 当用户申请重置密码，并收到验证码后，使用该接口进行密码重置 | 是| 无|  
| 海尔邮箱账号申请绑定手机号     | 当用户需要绑定手机号时，使用此接口申请绑定手机号的手机验证码 | 是| 无|  
| 海尔邮箱账号绑定手机号     | 当用户申请绑定手机号，并收到验证码后，使用该接口进行绑定手机号 | 是| 无|  
| 海尔账号快速登陆验证码申请     | 已注册手机号申请临时登陆验证码，验证码为6位数字，10分钟有效期 | 是| 无|  
| 海尔账号手机验证码快速登录     | 当已注册用户申请动态登录验证码，并收到6位动态验证码后，使用该接口进行快速登录 | 是| 无|  

#### 海尔账号注册
> 注册新用户。使用手机注册的用户，注册成功后，平台根据用户填写的mobile向用户的手机发送短信验证码，用户使用短信中的验证码，调用“海尔账号激活”接口进行激活。使用邮箱注册的用户，注册成功后，平台根据用户填写的email向用户的邮箱发送包含激活链接的邮件，用户点击链接直接激活，不再需要调用“海尔账号激活”接口。激活码的有效时间为10分钟。不需登录可以访问。  


##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/register`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| loginName     | String | Body| 非必填|登录名。不填写时由系统自动生成（推荐）|  
| loginId     | String | Body| 必填|填写手机号或者邮箱|  
| password    | String | Body| 必填|密码，长度为6~255位|  


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:    
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"loginId": "13500001111",
"password": "123456"
}


```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> B00002-00002、A00001-22001、B00002-22100、B00002-22803、A00001-00011、B00002-01002、A00001-01004  

#### 海尔账号激活
> 注册的新用户收到验证码后，使用该接口进行激活操作。使用手机号注册的情况，使用该接口激活。激活码的有效时间为10分钟。不需登录可以访问。  
  


##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/activate`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| uvc     | String | Body| 必填|验证码，用户收到的激活验证码|  
| loginId     | String | Body| 必填|填写手机|  
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"uvc": "123456",
"loginId": "13500001111"
}



```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> B00002-00002、A00001-22001、B00002-22100、B22101-22101、B22102-22102、B00007-22805、A00001-00011、B00002-01002、A00001-01004   

#### 海尔账号重新发送激活码（注册后）
> 在注册成功后，但因手机网络、邮件网络等原因，用户未能收到激活码（或激活邮件）的情况，以及用户收到激活码但没有执行激活，导致激活码过期的情况等情况下，可通过本接口向用户重新发送激活码（或激活邮件）。使用本接口的前提条件是用户已经注册，但未激活。激活码的有效时间为10分钟。不需登录可以访问。   
  


##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/sendActivationCode`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| loginId     | String | Body| 必填|填写手机号或者邮箱|   
   
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"loginId": "13500001111",
}


```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> B00002-00002、A00001-22001、B00002-22100、B00002-22802、B22101-22101、A00001-00011、B00002-01002、A00001-01004   

#### 海尔账号注册前申请激活码（新版注册）
> 使用手机号注册的用户可以使用简易注册流程，分两步执行  
1、	先申请激活码，发送短信激活码到用户手机  
2、	使用收到的激活码进行注册并登录    
使用本接口完成简易注册流程的第一步，申请激活码。申请激活码的手机号必须与注册使用的手机号为同一号码。激活码的有效时间为10分钟。不需登录可以访问。  

  


##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/applyActivationCode`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| mobile     | String | Body| 必填|申请激活码的手机号|   
   
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"mobile": "13500001111",
}


```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> B22102-22102、B00002-22803、A00001-00011、B00002-01002、A00001-01004  

#### 海尔账号注册并登录（新版注册）
>使用手机号注册的用户可以使用简易注册流程，分两步执行  
1、	先申请激活码，发送短信激活码到用户手机  
2、	使用收到的激活码进行注册并登录    
使用本接口完成简易注册流程的第二步，注册并登录。申请激活码的手机号必须与注册使用的手机号为同一号码。成功后，安全系统创建安全令牌accessToken，通过header头返回给用户。激活码的有效时间为10分钟。不需登录可以访问。  


  


##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/ registerAndlogin`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| mobile     | String | Body| 必填|用户注册使用的手机号|   
| password     | String | Body| 必填|密码，长度为6~255位| 
| uvc     | String | Body| 必填|激活码|  
  
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|  accessToken  |  String  | Header    | 必填    |  安全令牌  |  
|  openId  |  String  | Body    | 必填    |  用户标识  |  

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"mobile": "13500001111",
"password": "qqqqqq",
"uvc": "633445"
}


```  

**请求应答**

```java
Header：
accessToken:TGT1OY0RUUAH5D242SB68E9WX0W930
Body
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> B22102-22102、B00007-22805、A00001-00011、B00002-01002、A00001-01004、B00002-21004、B00002-21005、B00002-21006、B00002-21007、B00002-21008、B00002-21009、B00002-21010、A00001-21011、B00007-21012、A00001-21013、B00007-21020、A00001-21026、B00002-22100、B22101-22101、B22113-22113、B22109-22820、B00006-22821、B00003-22826、A00001-00011、B00002-01002、A00001-01004  

#### 海尔账号登录
>用户登录成功，安全系统创建安全令牌accessToken，通过header头返回给用户。不需登录可以访问。  

##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/login`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| loginId     | String | Body| 必填|可以填写手机号、邮箱或者loginName|   
| deviceToken     | String | Body| 非必填|ios设备为iostoken Android设备可不填 | 
| password     | String | Body| 必填|密码，长度为6~255位;不允许使用|  
  
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|  accessToken  |  String  | Header    | 必填    |  安全令牌  |  
|  openId  |  String  | Body    | 必填    |  用户标识，即userId  |  

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"loginId": "13500001111",
"password": "qqqqqq"
}



```  

**请求应答**

```java
Header：
accessToken:TGT1OY0RUUAH5D242SB68E9WX0W930
Body
{"retCode":"00000","retInfo":"操作成功","openId":"UAH1927B68E"}

```

##### 3、错误码  
> B00002-21004、B00002-21005、B00002-21006、B00002-21007、B00002-21008、B00002-21009、B00002-21010、A00001-21011、B00007-21012、A00001-21013、B00007-21020、A00001-21026、B00002-22100、B22101-22101、B22113-22113、B22109-22820、B00006-22821、B00003-22826、A00001-00011、B00002-01002、A00001-01004    
    
#### 海尔账号退出
>用户退出Haier U+云平台。安全系统校验请求头中的accessToken，accessToken有效，执行退出平台操作。登录后访问。   
 

##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/logout`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
|      |  | | | &emsp;|    



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:TGT1OY0RUUAH5D242SB68E9WX0W930  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json


```  

**请求应答**

```java

{"retCode":"00000","retInfo":"操作成功","openId":"UAH1927B68E"}

```

##### 3、错误码  
> B00007-21021、B00002-21004、B00002-21005、B00002-21006、B00002-21007、B00002-21010、A00001-21026、A00001-21011、B00002-21030、A00001-21027、B00007-21014、B00007-21015、B00007-21016  

#### 海尔账号申请重置密码
>当用户需要重置密码时，使用此接口申请重置密码。使用手机号申请重置密码的情况，申请成功后，平台会向用户手机发送重置密码的短信，用户使用收到的验证码，调用“重置密码接口”进行密码重置。使用邮箱申请重置密码的情况，申请成功后，平台会向用户邮箱发送重置密码的邮件，用户使用邮件直接重置密码，不再需要调用“重置密码接口”。验证码的有效时间为10分钟。不需登录可以访问。  
    
 

##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/applyReset`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
|  loginId  | String | Body | 必填| 填写注册使用的手机号或者邮箱 |    



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"loginId": "13500001111",
}


```  

**请求应答**

```java
{"retCode": "00000","retInfo": "操作成功"}
```

##### 3、错误码  
> B00002-00002、B00006-22823、A00001-00011、B00002-01002、A00001-01004    

#### 海尔账号重置密码
>当用户申请重置密码，并收到验证码后，使用该接口进行密码重置。使用手机号申请重置密码的情况，使用该接口重置密码。验证码的有效时间为10分钟。不需登录可以访问。  
 
##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/reset`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
|  uvc  | String | Body | 必填| 验证码 |    
|  loginId  | String | Body | 必填| 填写注册使用的手机号 |    
|  newPwd  | String | Body | 必填| 新密码，长度为6~255位 |    



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"uvc": "789012",
"newPwd": "zz1234",
"loginId": "13500001111",
}


```  

**请求应答**

```java
{"retCode": "00000","retInfo": "操作成功"}
```

##### 3、错误码  
> B00002-00002、B00006-22821、B00006-22823、B00007-22805、A00001-00011、B00002-01002、A00001-01004、B22109-22820    


#### 海尔邮箱账号申请绑定手机号
>当用户需要绑定手机号时，使用此接口申请绑定手机号的手机验证码。用户登录后，需要申请绑定手机号，申请成功后，平台会向用户手机发送验证码，调用“绑定手机号”进行绑定手机号。验证码的有效时间为10分钟。登录后访问。  
 
 
##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/sendBindMobileCode`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
|  email  | String | Body | 必填| 填写注册使用的邮箱 |    
|  mobile  | String | Body | 必填| 接受申请绑定手机号验证码的手机号 |  
  



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"email": "zz1234@qq.com",
"mobile": "13500001111"
}


```  

**请求应答**

```java
{"retCode": "00000","retInfo": "操作成功"}
```

##### 3、错误码  
> B00002-00002、B00002-01002、B00002-22100、A00001-22001、B22101-22101  

#### 海尔邮箱账号绑定手机号
>当用户申请绑定手机号，并收到验证码后，使用该接口进行绑定手机号。登录后可以访问。  

 
##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/bindMobile`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:| 
|  mobile  | String | Body | 必填| 申请绑定的手机号 |  
|  uvc  | String | Body | 必填| 验证码 |  



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"mobile": "13500001111",
"uvc": "789012"
}


```  

**请求应答**

```java
{"retCode": "00000","retInfo": "操作成功"}
```

##### 3、错误码  
> B00002-00002、B22101-22101、B00002-22100、B00007-22805、A00001-00011、B00002-01002、A00001-01004    

#### 海尔账号快速登陆验证码申请
>已注册手机号申请临时登陆验证码，验证码为6位数字，10分钟有效期  

 
##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/applyLoginMsg`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:| 
|  mobile  | String | Body | 必填| 申请绑定的手机号 |  
 



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"mobile": "13500001111"
}



```  

**请求应答**

```java
{"retCode": "00000","retInfo": "操作成功"}
```

##### 3、错误码  
> B22102-22102、B00002-22803、A00001-00011、B00002-01002、A00001-01004  


#### 海尔账号手机验证码快速登录
>当已注册用户申请动态登录验证码，并收到6位动态验证码后，使用该接口进行快速登录。当未注册的手机号登陆时，需先进行注册再登陆   

 
##### 1、接口定义

?> **接入地 址：**  `https://uhome.haier.net:6503/openapi/v2/user/userloginByMsg`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:| 
|  mobile  | String | Body | 必填| 快速登录的手机号 |  
|  uvc  | String | Body | 必填| 用户手机收到的6位动态验证码 |  
|  deviceToken  | String | Body | 非必填| ios设备为iostoken Android设备可不填 |  



**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|  accessToken  |  String |  Header   | 必填    |  安全令牌 |  
|  userId  |  String |  Body   | 必填    |  用户标识 | 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"mobile": "13500001111",
"uvc": "789012"
}



```  

**请求应答**

```java
Header：
accessToken:TGT1OY0RUUAH5D242SB68E9WX0W930
Body
{"retCode":"00000","retInfo":"操作成功","userId":"UAH1927B68E"}

```

##### 3、错误码  
> B00002-21004、B00002-21005、B00002-21006、B00002-21007、B00002-21008、B00002-21009、B00002-21010、A00001-21011、B00007-21012、A00001-21013、B00007-21020、A00001-21026、B00002-22100、B22101-22101、B22113-22113、B22109-22820、B00006-22821、B00003-22826、A00001-00011、B00002-01002、A00001-01004  

注释结束 -->

### 海尔优家 开发者自有账号登录
> API接口总览

| API名称        | 作用          | 是否开放  | 特别说明|
| ------------- |:-------------:|:-----:|:-------------:|
| 账号注册     | 使用手机注册，成功后，平台向用户手机发送短信验证码 | 是| 无|  
| 账号登录     | 用户登录成功，安全系统创建安全令牌accessToken，通过header头返回给用户 | 是| 无|  
| 账号退出 | 系统校验请求头中的accessToken，accessToken有效，执行退出平台操作 | 是| 无|  
| 账号查询账号信息    | 用户查询账号信息| 是| 无|  
| 账号信息修改  | 修改用户的应用属性，其他基础属性 | 是| 无|  
| 账号动态验证码申请     | 验证码生成后会直接发送验证码到验证手机或验证邮箱 | 是| 无|  
| 账号动态验证码验证     | 当用户是注册时收到的激活码，那么transactionId填空字符串 | 是| 无|  

#### 账号注册
>使用手机注册的用户，注册成功后，平台根据用户填写的mobile向用户的手机发送短信验证码，用户使用短信中的验证码，调用“自有账号动态验证码验证”接口进行激活。使用邮箱注册的用户，注册成功后，平台根据用户填写的email向用户的邮箱发送包含激活验证码的邮件，调用“自有账号动态验证码验证”接口进行激活。激活码的有效时间为10分钟。不需登录可以访问。   



##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/users/register`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| user     | User | Body| id注册时不填；loginName可不填写，如不填写，则由系统自动生成；email与mobile两者必填一个；userProfile如果没有，需填写{}|用户信息，User对象中包括userBase和userProfile属性，注册自有账号时userBase中的acctype必须为99|  
| password     | String | Body| 必填|密码，长度为6~20位|  


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:    
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"password":"111111",
"user":
{
"userBase":{ 
"loginName":"test",
"email":"848421322@qq.com",
"mobile":"18259060830",
"accType":99
},
"userProfile":{
"nickName":"test",
"userName":"test",
"points":"0",
"focusCount":"0",
"followCount":"0"
}
}
}


```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> 见首页公共错误码 

#### 账号登录
> 用户登录成功，安全系统创建安全令牌accessToken，通过header头返回给用户。不需登录可以访问。  
  


##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/security/userlogin`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| sequenceId     | String | Body| 必填|&emsp; |  
| loginId     | String | Body| 必填|登录用户名 |  
| password     | String | Body| 必填|密码 |  
| accType     | int | Body| 必填|必须为99  |   
| loginType     | int | Body| 必填|登录类型 0：loginName ；1：手机号； 2：邮箱  |  

**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
| accessToken   |   String |  Header   |  必填   |  安全令牌  |  
| userId   |   String |  Body   |  必填   |  用户标识   |



##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"sequenceId":"20140305102633000001",
"accType": "99",
"loginId":"14759167292",
"password":"123456",
"thirdpartyAppId":"",
"thirdpartyAccessToken":"",
"loginType":"1"
}




```  

**请求应答**

```java
Header：
accessToken:TGT13OOQL5O7TEAB21WVIKCJTEL470
{"retCode":"00000","retInfo":"登录UHOME云平台成功","userId":"100013957366155388"}

```

##### 3、错误码  
> 见首页公共错误码   

#### 账号退出
> 系统校验请求头中的accessToken，accessToken有效，执行退出平台操作     
  


##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/security/userlogout`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| sequenceId     | String | Body| 必填|&emsp; |   
   
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:TGT13OOQL5O7TEAB21WVIKCJTEL470  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"sequenceId":"100013957366155388"
}



```  

**请求应答**

```java
{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> 见首页公共错误码  

#### 账号查询账号信息
>用户查询自有账号信息   

  


##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/users/{uid}`  
 **HTTP Method：** GET

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| uid     | int | Url| 必填|用户id|   
   
 


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
| user   |  User  |   Body  |  必填 userProfile可为null   | 用户信息   |

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:TGT13OOQL5O7TEAB21WVIKCJTEL470 
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json

```  

**请求应答**

```java
{"retCode":"00000","retInfo":"正确","user":{"userBase":{"id":"100013957366155385","loginName":"zhoujie","email":"848421322@qqq.com","mobile":"18259000000","accType":"99","status":"1"},"userProfile":{"phone":null,"updateTime":null,"status":null,"tel":null,"applyTime":null,"idcard":null,"companyName":null,"type":null,"postcode":null,"legalPerson":null,"contacts":null,"companyCode":null,"businessLicense":null,"address":null,"contactsPhone":null,"email":null,"QQ":null,"name":null,"realname":null,"idcardPhoto":null}}}

```

##### 3、错误码  
> 见首页公共错误码 

#### 账号信息修改
>修改用户的应用属性，其他基础属性。验证参数传入的userId（url）与登录用户（通过accessToken获取登录用户）是否为同一用户，不是同一用户将抛出错误码。  


  


##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/users/{userId}/profile`  
 **HTTP Method：** PUT

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| userId     | int | Url| 必填|用户id|   
| userProfile     | UserProfile | Body| 必填|用户扩展信息|  


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;   |   


##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken: TGT13OOQL5O7TEAB21WVIKCJTEL470 
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"userProfile":{"phone":14759167292,"updateTime":"20141115","status":null,"tel":"0596","applyTime":null,"idcard":null,"companyName":null,"type":null,"postcode":null,"legalPerson":null,"contacts":null,"companyCode":333,"businessLicense":null,"address":"china","contactsPhone":null,"email":"848421322@qq.com","QQ":"848421322","name":"test","realname":"test","idcardPhoto":null}
}

```  

**请求应答**

```java

{
    "retCode": "00000",
    "retInfo": "成功!"
}

```

##### 3、错误码  
> 见首页公共错误码 

#### 账号动态验证码申请
>uvcs:User Verification Code 注意： 验证码生成后会直接发送验证码到验证手机或验证邮箱，以保证安全  
  

##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/uvcs`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| loginName     | String | Body| 必填|账号，本字段做了兼容，可以填写用户名，如果validateType为1，可以填注册手机号；为2，填写邮箱|   
| validateType     | int | Body| 必填|验证方式 1：手机 2：邮箱| 
| validateScene     | int | Body| 必填|验证场景 1：激活 2：密码重置 |  
| sendTo     | String | Body| 必填|验证码发送到的地址（手机或邮箱），由validateType决定 |  
| accType     | int | Body| 必填|必须填写99 |   


**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|  transactionId  |  String  | Body    | 必填    |  事物ID  |  

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:TGT13OOQL5O7TEAB21WVIKCJTEL470
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"tenantId":"1",
"loginName":"test321",
"validateType":1,
"validateScene":2,
"sendTo":"14759167292",
"accType":99
}




```  

**请求应答**

```java
{"retCode":"00000","retInfo":"正确","transactionId":"1416045701521203"}

```

##### 3、错误码  
> 见首页公共错误码    
    
#### 账号动态验证码验证
>注意：当用户是注册时收到的激活码，那么transactionId填空字符串（””）     
 

##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/uvcs/{uvc}/verify`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
|   uvc   | String | Url | 必填 | 验证码|      
|   loginName   | String | Body | 必填 | 用户登录名或注册手机号或注册邮箱|    
|   validateScene   | int | Body | 必填 | 验证场景 1：激活 2：密码重置|  
|   validateType   | int | Body | 必填 | 验证方式 1：手机 2：邮件|  
|   transactionId   | String | Body | 必填 | 事物ID|  
|   accType   | int | Body | 必填 | 必须填写99|    

**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|    |    |     |     |  &emsp;  |  
 

##### 2、请求样例  

**用户请求**
```java  
Header：
appId: MB-FRIDGEGENE1-0000
appVersion: 99.99.99.99990
clientId: 123
sequenceId: 2014022801010
accessToken:TGT1OY0RUUAH5D242SB68E9WX0W930  
sign: e5bd9aefd68c16a9d441a636081f11ceaed51ff58ec608e5d90048f975927e7f
timestamp: 1491014447260 
language: zh-cn
timezone: +8
appKey: 6cdd4658b8e7dcedf287823b94eb6ff9
Content-Encoding: utf-8
Content-type: application/json
Body
{
"tenantId":"100",
"loginName":"test321",
"validateType":2,
"validateScene":2,
"accType":99,
"transactionId":"1416045701521203"
}


```  

**请求应答**

```java

{"retCode":"00000","retInfo":"操作成功"}

```

##### 3、错误码  
> 见首页公共错误码


### 海尔优家 OAuth

### 海尔优家 第三方登录

#### 第三方用户登录
>移动APP客户端，第三方用户登录Haier uHome云平台。安全系统调用云平台用户系统的验证Validate()接口。用户系统验证成功，向安全系统返回验证成功retCode，retInfo和userId。安全系统创建安全令牌accessToken，将accessToken和userId返回移动APP。用户系统验证失败retCode和retInfo，向安全系统返回验证失败结果。安全系统向移动APP返回登录失败。  
 



##### 1、接口定义

?> **接入地 址：**  `/serviceAgent/rest/security/userlogin`  
 **HTTP Method：** POST

**输入参数**  

| 参数名        | 类型          | 位置  | 必填|说明|
| ------------- |:-------------:|:-----:|:-------------:|
| loginId     | String | Body| 必填|登录用户名|  
| password     | String | Body| 必填|密码，如无需要，可填无意义值|  
| loginType     | int | Body| 必填|登录类型 0：loginName 1：手机号 2：邮箱 3：动态密码|    
| accType     | int | Body| 必填|用户类型 0: 海尔官网用户 1：QQ 2：微信 3：新浪 4：豆瓣 5：人人 99：uHome用户 8：百度用户 本字段不填默认为0|  
| sequenceId     | String | Body| 必填||  
| thirdpartyAppId     | String | Body| 非必填|第三方平台应用ID|  
| thirdpartyAccessToken     | String | Body| 必填|第三方平台安全令牌|  

**输出参数**  

|   名称      |     类型      | 位置  |必填 |说明|
| ------------- |:----------:|:-----:|:--------:|:---------:|
|  accessToken  |  String  |   Header  |  必填   |  安全令牌    |
|  userId  |  String  |   Body  |  必填   |  用户标识    |  


##### 2、请求样例  

**用户请求**
```java  
header:
appId MB-DEVELOPERSITE-0000
sequenceId 20140730112234000001
Content-Type application/json;charset=UTF-8
appKey 0b6d09518p152c9aj09cf6d80ee657c9
appVersion 10.01.11.00025
clientId 356877020056553-08002700DC94
body:
{
"loginId":"897",
"password":"111111",
"accType": "11",
"loginType":"1",
"sequenceId":"20140305102633000001",
"thirdpartyAccessToken":"AAAAAAAAAAAA",
"thirdpartyAppId":"bbbbbbb"
}


```  

**请求应答**

```java
header:
appId MB-DEVELOPERSITE-0000
sequenceId 20140730112234000001
Content-Type application/json;charset=UTF-8
appKey 0b6d09518p152c9aj09cf6d80ee657c9
appVersion 10.01.11.00025
clientId 356877020056553-08002700DC94
Body:
{"retCode":"00000","retInfo":"登录UHOME云平台成功","userId":"100013957366155388"}

```

##### 3、错误码  
> 见首页公共错误码  

## 使用方式

### 开通流程  
![开通流程][account_liucheng]

### 应用场景
**账号管理**  
开发者没有账户系统，可集成U+账号的相关服务。  

**第三方登录**  
通过主流的第三方平台，一键进行登录。  

**开发者账号**  
开发者有自己的账户系统，通过云云对接互联方式接入U+账户服务。  


## 文档资料
[UWS 账户服务][account_document_url]

## 常见问题

[^-^]:文本连接注释
[account_document_url]:_document/_account/账号服务v1.0.0（临时方案）.docx

[^-^]:常用图片注释
[account_type]:_media/_account/account_type.png
[account_liucheng]:_media/_account/account_liucheng.png


