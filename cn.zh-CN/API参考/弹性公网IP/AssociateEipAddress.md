# AssociateEipAddress

调用AssociateEipAddress接口将弹性公网IP（Elastic IP Address，简称EIP）绑定到同地域的云产品实例上。

## API描述

在调用本接口时，请注意：

-   EIP可绑定到同地域的专有网络类型的ECS实例、专有网络类型的SLB实例、专有网络类型的辅助弹性网卡和NAT网关上。
-   如果您需要将EIP绑定到NAT网关上，确保在2017年11月03日之前账号下不存在NAT带宽包。

    对于2017年11月03日之前账号下存在NAT带宽包的用户，如需使用EIP绑定NAT网关，请参见[为什么在NAT网关控制台不能绑定EIP](~~187955~~)中的操作步骤。


## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=AssociateEipAddress&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AssociateEipAddress|要执行的操作，取值：**AssociateEipAddress**。 |
|AllocationId|String|是|eip-2zeerraiwb7ujsxdc\*\*\*\*|绑定云产品实例的EIP的ID。 |
|InstanceId|String|是|i-2zebb08phyczzawe\*\*\*\*|要绑定EIP的实例ID。

 支持输入NAT网关实例ID、负载均衡SLB实例ID、云服务器ECS实例ID、辅助弹性网卡实例ID、高可用虚拟IP实例ID。 |
|RegionId|String|是|cn-hangzhou|要绑定云产品实例的EIP所属的地域ID。 |
|InstanceType|String|否|EcsInstance|要绑定EIP的实例的类型，取值：

 -   **Nat**：NAT网关。
-   **SlbInstance**：负载均衡SLB。
-   **EcsInstance**：云服务器ECS。
-   **NetworkInterface**：辅助弹性网卡。
-   **HaVip**：高可用虚拟IP。 |
|InstanceRegionId|String|否|cn-hangzhou|要绑定EIP的实例所属地域的ID。

 **说明：** 仅在EIP加入到带宽共享性全球加速实例后，才需要填写该参数。 |
|PrivateIpAddress|String|否|192.1.XX.XX|交换机网段内的一个IP地址。

 如果不输入该参数，系统根据VPC ID和交换机ID自动分配一个私网IP地址。 |
|Mode|String|否|NAT|绑定模式，取值：

 -   **NAT**（默认值）：NAT模式（普通模式）。
-   **MULTI\_BINDED**：多EIP网卡可见模式。
-   **BINDED**：EIP网卡可见模式。

 仅**InstanceType**配置为**NetworkInterface**时，才需要配置该参数。 |
|ClientToken|String|否|0c593ea1-3bea-11e9-b96b-88e9fe63\*\*\*\*|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。`ClientToken`只支持ASCII字符，且不能超过64个字符。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=AssociateEipAddress
&AllocationId=eip-2zeerraiwb7ujsxdc****
&InstanceId=i-2zebb08phyczzawe****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<AssociateEipAddressResponse>
  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</AssociateEipAddressResponse>
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
|400|InvalidAssociation.Duplicated|Specified instance already is associated.|该实例已绑定EIP或全球加速实例，不能再绑定，如需更换实例绑定的EIP或全球加速实例，请先解绑。|
|400|OperationDenied|Specified instance is not in VPC.|该实例在VPC中不存在。|
|400|InvalidParameter.Mismatch|Specified elastic IP address and ECS instance are not in the same region.|该EIP和ECS实例不在同一个地域内。|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation|当前EIP的状态不支持该操作。|
|404|InvalidInstanId.NotFound|Specified instance does not exist.|指定的实例不存在，请您检查该实例是否正确。|
|400|IncorrectInstanceStatus|Current instance status does not support this operation.|当前实例的状态不支持该操作。|
|400|InvalidInstanceType.ValueNotSupported|The specified value of InstanceType is not supported.|参数InstanceType的值不合法。|
|400|IncorrectHaVipStatus|HaVip can be operated by this action only when it's status is Available or InUse.|只有当HAVIP的状态是Available或InUse时，才可以执行该操作。|
|400|InvalidParameter|The specified parameter is not valid.|该参数值不合法。|
|400|OperationDenied|Eip of default vpc not allow this operation|默认专有网络的EIP不支持该操作。|
|400|Forbbiden|The eip instance owener error|EIP 不属于当前调用者，请您检查该 EIP 是否可被您调用。|
|400|InvalidBindingStatus|The eip binding status invalid.|EIP绑定状态不正确。|
|400|BIND\_INSTANCE\_HAVE\_PORTMAP\_OR\_BIND\_EIP|The instance may have portMap or already bind eip.|ECS 实例已经存在端口转发规则，请删除相应的端口转发规则再进行操作。|
|400|BIND\_INSTANCE\_OWENER\_ERROR|Cannot operate the eip.|不能操作这个EIP。|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|指定的公网 IP 不存在，请您检查您填写的参数是否正确。|
|400|InvalidParams.NotFound|instance not found|实例不存在。|
|503|ServiceUnavailable|The request has failed due to a temporary failure of the server.|请求失败，因为临时服务器故障。|
|400|OperationDenied.CloudBoxResourceExist|The operation is not allowed because there are resources related to the cloud box in VPC.|指定操作被禁止，因为vpc中存在云盒相关的资源。|
|400|OperationDenied.CloudBoxVSwitchExist|The operation is not allowed because a cloud box type vSwitch exists in VPC.|指定操作被禁止，因为vpc中存在云盒类型的虚拟交换机。|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

