# 申请短信模板 - CreateUSMSTemplate

## 简介

调用接口CreateUSMSTemplate申请短信模板

?> 您可以通过调用接口CreateUSMSTemplate或者到控制台申请短信模板，短信模板需遵守 [UCloud服务协议](https://docs.ucloud.cn/management_monitor/usms/introduction/service_level)，短信模板申请流程可参见官网 [短信模板审核规范](https://docs.ucloud.cn/management_monitor/usms/introduction/2005/2103) 说明；




## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=CreateUSMSTemplate)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `CreateUSMSTemplate`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID，不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **Purpose** | int | 短信模板用途类型：1-验证码类短信模板；2-系统通知类短信模板；3-会员推广类短信模板； |**Yes**|
| **TemplateName** | string | 短信模板名称，不超过32个字符，每个中文、符号、英文、数字等都计为1个字。 |**Yes**|
| **Template** | string | 短信模板内容，说明如下：字数不超过500，每个中文、符号、英文、数组等都计为一个字；模板中的变量填写格式：{N}，其中N为大于1的整数，有多个参数时，建议N从1开始顺次，例如：{1}、{2}等；短信模板禁止仅包括变量的情况； |**Yes**|
| **International** | boolean | 标记是否为国际短信。true:国际短信，false:国内短信，若不传值则默认该值为false |No|
| **Remark** | string | 短信模板申请原因说明，字数不超过128，每个中文、符号、英文、数字等都计为1个字。 |No|
| **UnsubscribeInfo** | string | 当Purpose为3时，也即会员推广类短信模板，该项必填。枚举值：TD退订、回T退订、回N退订、回TD退订、退订回T、退订回D、退订回TD、退订回复T、退订回复D、退订回复N、退订回复TD、拒收回T |No|
| **Instruction** | string | 模板变量属性说明 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|
| **TemplateId** | string | 短信模板ID（短信模板申请时的工单ID） |**Yes**|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=CreateUSMSTemplate
&ProjectId=org-bxxxxy
&Purpose=2
&TemplateName=ucloud-alert
&Template=alertXXXXXXXXXXXXXXXXXXXXXXXX
&Remark=XXXXXXXXXXXXXXXX
&International=true
&Instruction=nkhgFrIo
&Instruction=TwnkHrCj
```

### 响应示例
    
```json
{
  "Action": "CreateUSMSTemplateResponse",
  "Message": "",
  "RetCode": 0,
  "TemplateId": "UTA190816758B3F"
}
```





