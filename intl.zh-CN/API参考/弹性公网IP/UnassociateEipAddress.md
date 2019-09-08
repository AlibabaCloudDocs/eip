# UnassociateEipAddress {#doc_api_Vpc_UnassociateEipAddress .reference}

使用UnassociateEipAddress将弹性公网IP（EIP）从绑定的云资源上解绑。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=UnassociateEipAddress&type=RPC&version=2016-04-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UnassociateEipAddress|要执行的操作。

 取值： **UnassociateEipAddress**。

 |
|AllocationId|String|是|eip-2zeerraiwb7uj6i0d0fo3|EIP的ID。

 |
|InstanceId|String|是|i-12345678|要解绑的云产品的实例ID。

 |
|RegionId|String|是|cn-hangzhou|弹性公网IP的地域ID。

 |
|InstanceType|String|否|EcsInstance|要解绑的资源类型，取值：

 -   EcsInstance（默认值）：专有网络的ECS实例
-   SlbInstance：专有网络的SLB实例
-   Nat：NAT网关
-   HaVip：HAVIP

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|220F3179-5238-47F0-A0CA-1272AA2BC41F|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=UnassociateEipAddress
&AllocationId=eip-25877c70x
&InstanceId=i-25skktcp4
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<UnassociateEipAddressResponse>
	  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</UnassociateEipAddressResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|指定的EIP状态不支持此操作。|
|400|InvalidInstanceId.NotFound|Specified instance does not exist.|该实例不存在，请您检查填写的实例是否正确。|
|400|IncorrectInstanceStatus|The current status of instance does not support this operation.|当前实例的状态不支持该操作。|
|400|InvalidInstanceType.ValueNotSupported|The specified value of InstanceType is not supported.|参数InstanceType的值不合法。|
|400|IncorrectHaVipStatus|This operation is denied because satus of the specified HaVip is neither Available nor InUse.|无法执行该操作，因为HAVIP的状态是Available或InUse。|
|400|OperationDenied|Eip of default vpc not allow this operation|默认专有网络的EIP不支持该操作。|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|
|400|InvalidParameter|The specified parameter is not valid.|该参数值不合法。|
|400|Forbbiden|The eip instance owener error|EIP 不属于当前调用者，请您检查该 EIP 是否可被您调用。|
|400|InvalidBindingStatus|The eip binding status invalid.|EIP绑定状态不正确。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

