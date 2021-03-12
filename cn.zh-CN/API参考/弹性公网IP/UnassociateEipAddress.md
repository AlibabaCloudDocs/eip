# UnassociateEipAddress

调用UnassociateEipAddress将弹性公网IP（EIP）从绑定的云产品上解绑。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=UnassociateEipAddress&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|UnassociateEipAddress|要执行的操作，取值：**UnassociateEipAddress**。 |
|AllocationId|String|是|eip-2zeerraiwb7uj6i0d\*\*\*\*|要解绑的EIP的ID。 您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|Force|Boolean|否|false|当EIP绑定了NAT网关，且NAT网关添加了DNAT或SNAT条目时，是否强制解绑EIP，取值：

 -   **false**（默认值）：不强制解绑EIP。
-   **true**：强制解绑EIP。 |
|RegionId|String|是|cn-hangzhou|要解绑的EIP的地域ID。 |
|InstanceId|String|否|i-hp3akk9irtd69jad\*\*\*\*|要解绑EIP的云产品实例的ID。 |
|InstanceType|String|否|EcsInstance|要解绑EIP的云产品类型，取值：

 -   **EcsInstance**（默认值）：专有网络类型的ECS实例。
-   **SlbInstance**：专有网络类型的SLB实例。
-   **NetworkInterface**：专有网络类型的辅助弹性网卡。
-   **Nat**：NAT网关。
-   **HaVip**：高可用虚拟IP。 |
|PrivateIpAddress|String|否|192.XX.XX.2|要解绑EIP的ECS实例或辅助弹性网卡实例的私网IP地址。 |
|ClientToken|String|否|02fb3da4-130e-11\*\*\*\*|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。`ClientToken`只支持ASCII字符，且不能超过64个字符。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=UnassociateEipAddress
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<UnassociateEipAddressResponse>
	  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</UnassociateEipAddressResponse>
```

`JSON`格式

```
{ 
    "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|指定的公网 IP 不存在，请您检查您填写的参数是否正确。|
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

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

