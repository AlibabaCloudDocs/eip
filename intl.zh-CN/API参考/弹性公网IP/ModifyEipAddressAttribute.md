# ModifyEipAddressAttribute

调用ModifyEipAddressAttribute接口修改指定EIP的名称、描述信息和带宽峰值。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=ModifyEipAddressAttribute&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyEipAddressAttribute|要执行的操作，取值：**ModifyEipAddressAttribute**。 |
|AllocationId|String|是|eip-2zeerraiwb7uj6i0d\*\*\*\*|要修改的EIP的ID。 |
|RegionId|String|是|cn-hangzhou|EIP所属的地域ID。 |
|Bandwidth|String|否|100|EIP的带宽峰值，取值：**1**~**200**，单位为Mbps。 |
|Description|String|否|abc|EIP的描述信息。

 长度为2~256个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。 |
|Name|String|否|Test123|EIP的名称。

 长度为2~128个字符，必须以字母或中文开头，可包含数字、点号（.）、下划线（\_）和短横线（-）。但不能以`http://`或`https://`开头。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。 |

## 示例

请求示例

```

http(s)://vpc.aliyuncs.com/?Action=ModifyEipAddressAttribute
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<公共请求参数>

```

正常返回示例

`XML` 格式

```
<ModifyEipAddressAttributeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyEipAddressAttributeResponse>
```

`JSON` 格式

```
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|InsufficientBalance.Eip|Your account does not have enough balance.|账户余额不足，请先充值再操作。|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|指定的公网 IP 不存在，请您检查您填写的参数是否正确。|
|400|InvalidParameter|Specified value of "Bandwidth" is not supported.|该带宽不合法。|
|500|InternalError|The request processing has failed due to some unknown error.|请求处理由于某些未知错误失败。|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|指定的EIP状态不支持此操作。|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found..|指定的公网 IP 不存在，请您检查填写的公网 IP 是否正确。|
|400|InvalidParameter|The parameter is invalid.|该参数值不合法。|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

