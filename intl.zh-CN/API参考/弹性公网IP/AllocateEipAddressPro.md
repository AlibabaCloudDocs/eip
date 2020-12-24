# AllocateEipAddressPro

调用AllocateEipAddressPro申请指定的弹性公网IP（EIP）。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddressPro&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AllocateEipAddressPro|要执行的操作，取值：**AllocateEipAddressPro**。 |
|RegionId|String|是|cn-hangzhou|要指定申请的EIP所在的地域。

 您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|IpAddress|String|否|12.xx.xx.23|要指定申请的EIP的IP地址。

 **IpAddress**和**InstanceId**参数仅需传入一个，如果都不传，系统会随机申请EIP。 |
|InstanceId|String|否|eip-25877c70gddh\*\*\*\*|要指定申请的EIP的实例ID。

 **IpAddress**和**InstanceId**参数仅需传入一个，如果都不传，系统会随机申请EIP。 |
|Bandwidth|String|否|5|要指定申请的EIP的带宽峰值，单位为Mbps。

 默认为**5**Mbps。 |
|Period|Integer|否|1|购买时长。

 -   当**PricingCycle**取值**Month**时，**Period**取值范围为**1~9**。
-   当**PricingCycle**取值**Year**时，**Period**取值范围为**1~3**。

 如果**InstanceChargeType**参数的值为**PrePaid**时，该参数必选。

 如果**InstanceChargeType**参数的值为**PostPaid**时，该参数不填。 |
|ISP|String|否|BGP|线路类型，默认值为**BGP**。

 -   如果是开通了单线带宽白名单的用户，ISP字段可以设置为**ChinaTelecom**（中国电信）、**ChinaUnicom**（中国联通）和**ChinaMobile**（中国移动）。
-   如果是杭州金融云用户，该字段必填，取值：**BGP\_FinanceCloud**。 |
|Netmode|String|否|public|网络类型，仅取值为**public**（公网）。

 默认值为**public**（公网）。 |
|AutoPay|Boolean|否|true|是否自动付费，取值：

 -   **false**：不开启自动付费，生成订单后需要到订单中心完成支付。
-   **true**：开启自动付费，自动支付订单。

 当**InstanceChargeType**参数的值为**PrePaid**时，该参数必选。

 当**InstanceChargeType**参数的值为**PostPaid**时，该参数可不填。 |
|PricingCycle|String|否|Month|包年包月的计费周期，取值：

 -   **Month**（默认值）：按月付费。
-   **Year**：按年付费。

 当**InstanceChargeType**参数的值为**PrePaid**时，该参数必选；当**InstanceChargeType**参数的值为**PostPaid**时，该参数可不填。 |
|InstanceChargeType|String|否|PostPaid|要指定申请的EIP的计费方式，取值：

 -   **PrePaid**：包年包月。
-   **PostPaid**（默认值）：按量计费。

 当**InstanceChargeType**取值为**PrePaid**时，**InternetChargeType**必须取值**PayByBandwidth**。

 当**InstanceChargeType**取值为**PostPaid**时，**InternetChargeType**可取值**PayByBandwidth**或**PayByTraffic**。 |
|InternetChargeType|String|否|PayByBandwidth|要指定申请的EIP的计量方式，取值：

 -   **PayByBandwidth**（默认值）：按带宽计费。
-   **PayByTraffic**：按流量计费。

 当**InstanceChargeType**取值为**PrePaid**时，**InternetChargeType**必须取值**PayByBandwidth**。

 当**InstanceChargeType**取值为**PostPaid**时，**InternetChargeType**可取值**PayByBandwidth**或**PayByTraffic**。 |
|ResourceGroupId|String|否|rg-resourcegroup\*\*\*\*|要指定申请的EIP所属的资源组ID。 |
|ClientToken|String|否|0c593ea1-3bea-11e9-b96b-88e9fe637760|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。ClientToken只支持ASCII字符，且不能超过64个字符。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|AllocationId|String|eip-25877c70gddh\*\*\*\*|EIP的ID。 |
|EipAddress|String|123.xx.xx.206|指定申请的EIP的IP地址。 |
|OrderId|Long|20190000|订单ID。 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。 |
|ResourceGroupId|String|rg-resourcegroup\*\*\*\*|资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=AllocateEipAddressPro
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<AllocateEipAddressProResponse>
      <RequestId>473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E</RequestId>
      <AllocationId>eip-25877c70gddh****</AllocationId>
      <EipAddress>123.xx.xx.206</EipAddress>
      <OrderId>20190000</OrderId>
      <ResourceGroupId>rg-resourcegroup****</ResourceGroupId>
</AllocateEipAddressProResponse>
```

`JSON` 格式

```
{
	"RequestId":"473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E",
    "AllocationId":"eip-25877c70gddh****",
    "EipAddress":"123.xx.xx.206",
    "OrderId":"20190000",
    "ResourceGroupId":"rg-resourcegroup****"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden|User not authorized to operate on the specified resource.|您没有权限操作该资源，请您申请操作权限后再试。|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|弹性公网 IP 的个数超过额度限制，如果您有更多额度的需求，请提交工单申请增加限额，建议您考虑使用NAT网关。|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|参数InternetChargeType的值不合法。|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|该带宽不合法。|
|400|InsufficientBalance|Your account does not have enough balance.|账户余额不足，请先充值再操作。|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|弹性公网 IP 的个数超过额度限制，如果您有更多额度的需求，请提交工单申请增加限额，建议您考虑使用NAT网关。|
|400|ReserveIpFail|Reserve eip failed.|EIP预留失败。|
|400|InvalidRegion.NotSupport|The specified region does not support.|该 RegionId 不支持此操作。|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|资源组ID不存在。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

