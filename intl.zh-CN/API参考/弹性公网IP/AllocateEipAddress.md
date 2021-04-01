# AllocateEipAddress

调用AllocateEipAddress接口申请弹性公网IP EIP（Elastic IP Address）。

## API描述

请确保在使用该接口前，您已充分了解EIP的收费方式和价格。更多信息，请参见[计费概述](~~122035~~)。

调用本接口后将在指定的地域内随机获取一个状态为**Available**的弹性公网IP。弹性公网IP在传输层目前只支持ICMP、TCP和UDP协议，不支持IGMP和SCTP等协议。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddress&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AllocateEipAddress|要执行的操作，取值：**AllocateEipAddress**。 |
|RegionId|String|是|cn-hangzhou|弹性公网IP所属的地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|Bandwidth|String|否|5|EIP的带宽峰值，取值范围：**1**~**200**，单位为Mbps。

 默认值为**5**。 |
|Period|Integer|否|1|购买时长。

 当**PricingCycle**取值**Month**时，**Period**取值范围为**1**~**9**。

 当**PricingCycle**取值**Year**时，**Period**取值范围为**1**~**5**。

 如果**InstanceChargeType**参数的值为**PrePaid**时，该参数必选，如果**InstanceChargeType**参数的值为**PostPaid**时，该参数不填。 |
|ISP|String|否|BGP|线路类型，目前只支持在创建按量付费实例时指定线路类型，取值：

 -   **BGP**：BGP（多线）线路。

BGP（多线）线路在全球有多达89条优质BGP线路，在中国内地的每个地域均提供电信、联通、移动、铁通、网通、教育网、广电、鹏博士、方正宽带等多条线路的直连覆盖。

-   **BGP\_PRO**：BGP（多线）精品线路。

BGP（多线）精品线路是一种优化海外回中国内地流量的公网线路，可以提高国际业务访问质量。相比普通BGP（多线）线路， BGP（多线）精品线路在为中国内地终端客户（不包括中国内地数据中心）提供服务时，通过底层网络直连回中国内地，无需绕行国际运营商出口，时延更低。


 目前，全部地域都支持BGP（多线）线路EIP，仅中国（香港）地域支持BGP（多线）精品线路EIP。

 **说明：** 如果是开通了单线带宽白名单的用户，ISP字段可以设置为**ChinaTelecom**（中国电信）、**ChinaUnicom**（中国联通）和**ChinaMobile**（中国移动）；如果是杭州金融云用户，该字段必填，取值：**BGP\_FinanceCloud**。 |
|ActivityId|Long|否|123456|特殊活动ID，无需配置此参数。 |
|Netmode|String|否|public|网络类型，取值为**public**（公网）。 |
|AutoPay|Boolean|否|false|是否自动付费，取值：

 -   **false**：不开启自动付费，生成订单后需要到订单中心完成支付。
-   **true**：开启自动付费，自动支付订单。

 当**InstanceChargeType**参数的值为**PrePaid**时，该参数必选；当**InstanceChargeType**参数的值为**PostPaid**时，该参数可不填。 |
|PricingCycle|String|否|Month|包年包月的计费周期，取值：

 -   **Month**（默认值）：按月付费。
-   **Year**：按年付费。

当**InstanceChargeType**参数的值为**PrePaid**时，该参数必选；当**InstanceChargeType**参数的值为**PostPaid**时，该参数可不填。 |
|InstanceChargeType|String|否|PostPaid|EIP的计费方式，取值：

 -   **PrePaid**：包年包月。
-   **PostPaid**（默认值）：按量计费。

 当**InstanceChargeType**取值为**PrePaid**时，**InternetChargeType**必须取值**PayByBandwidth**；当**InstanceChargeType**取值为**PostPaid**时，**InternetChargeType**可取值**PayByBandwidth**或**PayByTraffic**。 |
|InternetChargeType|String|否|PayByTraffic|EIP的计量方式，取值：

 -   **PayByBandwidth**（默认值）：按带宽计费。
-   **PayByTraffic**：按流量计费。

 当**InstanceChargeType**取值为**PrePaid**时，**InternetChargeType**必须取值**PayByBandwidth**。

 当**InstanceChargeType**取值为**PostPaid**时，**InternetChargeType**可取值**PayByBandwidth**或**PayByTraffic**。 |
|ResourceGroupId|String|否|rg-acfmxazffggds\*\*\*\*|资源组ID。 |
|ClientToken|String|否|0c593ea1-3bea-11e9-b96b-88e9fe637760|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。**ClientToken**只支持ASCII字符，且不能超过64个字符。更多信息，请参见[如何保证幂等性](~~36569~~)。 |
|Name|String|否|EIP1|EIP实例的名称。

 **说明：** 创建预付费的EIP实例时，不支持设置该参数。 |
|Description|String|否|test|EIP实例的描述。

 **说明：** 创建预付费的EIP实例时，不支持设置该参数。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|EipAddress|String|12.XX.XX.78|分配的EIP。 |
|AllocationId|String|eip-25877c70gddh\*\*\*\*|EIP实例的ID。 |
|OrderId|Long|10|订单号，仅**InstanceChargeType**取值为**PrePaid**时返回。 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。 |
|ResourceGroupId|String|rg-acfmxazfdgdg\*\*\*\*|资源组ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=AllocateEipAddress
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<AllocateEipAddressResponse>
  <ResourceGroupId>rg-acfmxazfdgdg****</ResourceGroupId>
  <RequestId>4EC47282-1B74-4534-BD0E-403F3EE64CAF</RequestId>
  <AllocationId>eip-25877c70gddh****</AllocationId>
  <EipAddress>12.XX.XX.78</EipAddress>
  <OrderId>10</OrderId>
</AllocateEipAddressResponse>
```

`JSON`格式

```
{
    "AllocateEipAddressResponse": {
        "ResourceGroupId": "rg-acfmxazfdgdg****",
        "RequestId": "4EC47282-1B74-4534-BD0E-403F3EE64CAF",
        "AllocationId": "eip-25877c70gddh****",
        "EipAddress": "12.XX.XX.78",
        "OrderId": 10
    }
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
|409|OperationConflict|Request was denied due to conflict with a previos request.|请求冲突，稍等一段时间重试，或者提交工单反馈。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

