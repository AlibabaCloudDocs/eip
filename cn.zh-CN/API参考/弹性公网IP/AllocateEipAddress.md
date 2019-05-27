# AllocateEipAddress {#doc_api_Vpc_AllocateEipAddress .reference}

使用AllocateEipAddress接口申请弹性公网IP（EIP）。

调用本接口后将在指定的地域内随机获取一个状态为**Available**的弹性公网IP。弹性公网IP在传输层目前只支持ICMP、TCP和UDP协议，不支持IGMP和SCTP等协议。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddress)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AllocateEipAddress|要执行的操作，取值：**AllocateEipAddress**。

 |
|RegionId|String|是|cn-hangzhou|弹性公网IP所属的地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|AutoPay|Boolean|否|false|是否自动付费，取值：

 -   **false**：不开启自动付费，生成订单后需要到订单中心完成支付。
-   **true**：开启自动付费，自动支付订单。

 **说明：** **InstanceChargeType**参数的值为**PrePaid**时，该参数必选。

 |
|Bandwidth|String|否|5|EIP的带宽峰值，单位为Mbps，默认值为5。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-001xxxxxxxx|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大不值过64个 ASCII 字符。

 |
|ISP|String|否|BGP|线路类型，默认值为**BGP**。

 **说明：** 如果是杭州金融云用户，该字段必填，取值：**BGP\_FinanceCloud**。

 |
|InstanceChargeType|String|否|PostPaid|EIP的付费方式，取值：

 -   **PrePaid**：预付费。
-   **PostPaid**（默认值）：后付费。

 |
|InternetChargeType|String|否|PayByBandwidth|EIP的计费方式，取值：

 -   **PayByBandwidth**（默认值）：按带宽计费。
-   **PayByTraffic**：按流量计费。

 |
|Netmode|String|否|Public|网络类型，默认值为**Public**。

 |
|Period|Integer|否|10|购买时长。取值：

 -   当选择按月付费时，取值范围为**1-9**。
-   当选择按年付费时，取值范围为**1-3**。**InstanceChargeType**参数的值为**PrePaid**时，该参数必选。

 |
|PricingCycle|String|否|Month|预付费的计费周期，取值：

 -   **Month**（默认值）：按月付费
-   **Year**：按年付费。

**说明：** **InstanceChargeType**参数的值为**PrePaid**时，该参数必选。


 |
|ResourceGroupId|String|否|rg-acfmxazxxxxxxxx|企业资源组ID。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|EipAddress|String|12.xx.xx.78|分配的EIP。

 |
|AllocationId|String|eip-25877c70xxxxxxxx|EIP的ID。

 |
|OrderId|Long|10|订单号。只有预付费时返回。

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。

 |
|ResourceGroupId|String|rg-acfmxazxxxxxxxx|企业资源组ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=AllocateEipAddress
&RegionId=cn-beijing
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AllocateEipAddressResponse>
  <AllocationId>eip-25877c70xxxxxxxx</AllocationId>
  <EipAddress>123.xx.xx.206</EipAddress>
  <RequestId>B6B9F518-60F8-4D81-9242-1207B356754D</RequestId>
</AllocateEipAddressResponse>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"B6B9F518-60F8-4D81-9242-1207B356754D",
	"EipAddress":"123.xx.xx.206",
	"AllocationId":"eip-25877c70xxxxxxxx"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden|User not authorized to operate on the specified resource.|您没有权限操作该资源，请您申请操作权限后再试。|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|弹性公网 IP 的个数超过额度限制，如果您有更多额度的需求，请提交工单申请增加限额，建议您考虑使用NAT网关。|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|参数InternetChargeType的值不合法。|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|该带宽不合法。|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|弹性公网 IP 的个数超过额度限制，如果您有更多额度的需求，请提交工单申请增加限额，建议您考虑使用NAT网关。|
|400|ReserveIpFail|Reserve eip failed.|EIP预留失败。|
|400|InvalidRegion.NotSupport|The specified region does not support.|该 RegionId 不支持此操作。|

[查看本产品错误码](https://error-center.aliyun.com/status/product/Vpc)

