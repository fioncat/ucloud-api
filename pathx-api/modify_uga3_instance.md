# 修改统一接入加速配置属性 - ModifyUGA3Instance

## 简介

修改统一接入加速配置属性，如Name，ReMark






## 使用方法

您可以选择以下方式中的任意一种，发起 API 请求：
- 多语言 OpenSDK / [Go](https://github.com/ucloud/ucloud-sdk-go) / [Python](https://github.com/ucloud/ucloud-sdk-python3) / [Java](https://github.com/ucloud/ucloud-sdk-java) /
- [UAPI 浏览器](https://console.ucloud.cn/uapi/detail?id=ModifyUGA3Instance)
- [CloudShell 云命令行](https://shell.ucloud.cn/)


## 定义

### 公共参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **Action**     | string  | 对应的 API 指令名称，当前 API 为 `ModifyUGA3Instance`                        | **Yes** |
| **PublicKey**  | string  | 用户公钥，可从 [控制台](https://console.ucloud.cn/uapi/apikey) 获取                                             | **Yes** |
| **Signature**  | string  | 根据公钥及 API 指令生成的用户签名，参见 [签名算法](api/summary/signature.md)  | **Yes** |

### 请求参数

| 参数名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **ProjectId** | string | 项目ID。不填写为默认项目，子帐号必须填写。 请参考[GetProjectList接口](https://docs.ucloud.cn/api/summary/get_project_list) |**Yes**|
| **InstanceId** | string | 加速配置实例ID，格式uga-xxxx。不支持GlobalSSH实例。 |**Yes**|
| **Name** | string | 加速配置实例名称，不填或空字符串则不更新 |No|
| **Remark** | string | 备注信息，暂时前端为使用 |No|

### 响应字段

| 字段名 | 类型 | 描述信息 | 必填 |
|:---|:---|:---|:---|
| **RetCode** | int | 返回状态码，为 0 则为成功返回，非 0 为失败 |**Yes**|
| **Action** | string | 操作指令名称 |**Yes**|
| **Message** | string | 返回错误消息，当 `RetCode` 非 0 时提供详细的描述信息 |No|




## 示例

### 请求示例
    
```
https://api.ucloud.cn/?Action=ModifyUGA3Instance
&ProjectId=LSLRQcpF
&InstanceId=BsQLFQzC
&Domain=QZidFhAw
&Name=hOnwvbkH
&IPList=dyNcrVqU
&Remark=VAXWfscS
&Bandwidth=crDMiXCE
&AreaCode=fhyqSYWY
&Area=MrqyHbPJ
&CouponId=MmVvSfpx
```

### 响应示例
    
```json
{
  "Action": "ModifyUGA3InstanceResponse",
  "Message": "cSwYPLaa",
  "RetCode": 0
}
```





