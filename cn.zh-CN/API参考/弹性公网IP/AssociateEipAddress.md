# AssociateEipAddress {#doc_api_Vpc_AssociateEipAddress .reference}

调用AssociateEipAddress接口将弹性公网IP（EIP）绑定到同地域的云产品实例上。

在调用本接口时，请注意：

-   EIP可绑定到同地域的专有网络ECS实例、专有网络的SLB实例和NAT网关上。
-   如果您需要将EIP绑定到NAT网关上，确保在2017年11月3日之前账号下不存在NAT带宽包。2017年11月3日之前账号下存在NAT带宽包，请提交工单，开通EIP绑定NAT网关功能。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=AssociateEipAddress&type=RPC&version=2016-04-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AssociateEipAddress|要执行的操作，取值：**AssociateEipAddress**。

 |
|AllocationId|String|是|eip-2zeerraiwb7ujxxxxxxxx|EIP的ID。

 |
|InstanceId|String|是|i-2zebb08phyczxxxxxxxx|要绑定的实例ID。

 |
|RegionId|String|是|cn-hangzhou|EIP所属的地域ID。

 |
|InstanceRegionId|String|否|cn-hangzhou|绑定的实例所属地域ID。

 |
|InstanceType|String|否|EcsInstance|要绑定的云产品实例的类型，取值：**Nat|SlbInstance|EcsInstance|NetworkInterface**。

 |
|Mode|String|否|NAT|绑定模式，取值：**NAT|MULTI\_BINDED**。

 |
|PrivateIpAddress|String|否|192.xx.xx.4|输入交换机网段内的一个IP地址。

 如果不输入，系统根据VPC ID和交换机ID自动分配一个私网IP地址。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|C0FD0EED-F90D-4479-803D-DD62335357E5|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://vpc.aliyuncs.com/?Action=AssociateEipAddress
&AllocationId=eip-2zeerraiwb7ujxxxxxxxx
&InstanceId=i-2zebb08phyczxxxxxxxx
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AssociateEipAddressResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</AssociateEipAddressResponse>
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
|400|InvalidAssociation.Duplicated|Specified instance already is associated.|该实例已绑定 EIP 或 全球加速实例，不能再绑定，如需更换实例绑定的 EIP 或全球加速实例，请先解绑。|
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

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

