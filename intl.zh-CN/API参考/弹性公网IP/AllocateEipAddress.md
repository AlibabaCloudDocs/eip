# AllocateEipAddress {#doc_api_Vpc_AllocateEipAddress .reference}

调用AllocateEipAddress接口申请弹性公网IP（EIP）。

## API描述 {#description .section}

请确保在使用该接口前，已充分了解EIP的收费方式和价格。详细信息，请参见[计费概述](~~122035~~)。

调用本接口后将在指定的地域内随机获取一个状态为**Available**的弹性公网IP。弹性公网IP在传输层目前只支持ICMP、TCP和UDP协议，不支持IGMP和SCTP等协议。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddress&type=RPC&version=2016-04-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AllocateEipAddress|要执行的操作，取值：**AllocateEipAddress**。

 |
|RegionId|String|是|cn-hangzhou|弹性公网IP所属的地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|AutoPay|Boolean|否|false| 是否自动付费，该参数可不填。

 |
|Bandwidth|String|否|5|EIP的带宽峰值，单位为Mbps，默认值为**5**。

 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-001\*\*\*\*|客户端token，用于保证请求的幂等性。由客户端生成该参数值，要保证在不同请求间唯一，最大值不超过64个ASCII字符。

 |
|ISP|String|否|BGP|线路类型，默认值为**BGP**。

 -   对于已开通单线带宽白名单的用户，ISP字段可以设置为**ChinaTelecom**、**ChinaUnicom**和**ChinaMobile**，用来开通中国电信、中国联通、中国移动的单线EIP。
-   如果是杭州金融云用户，该字段必填，取值：**BGP\_FinanceCloud**。

 |
|InstanceChargeType|String|否|PostPaid| EIP的付费方式，必须取值**PostPaid**（后付费），且**InternetChargeType**必须取值**PayByTraffic**。后付费的详细信息，请参见[后付费](~~72142~~)。

 |
|InternetChargeType|String|否|PayByTraffic| EIP的计费方式，必须取值为**PayByTraffic**（按流量计费）。详细信息，请参见[按使用流量](~~72142~~)。

 |
|Netmode|String|否|Public|网络类型，默认值为**Public**。

 |
|Period|Integer|否|1| 购买时长，该参数不填。

 |
|PricingCycle|String|否|Month| 预付费的计费周期，该参数可不填。

 |
|ResourceGroupId|String|否|rg-acfmxazffggds\*\*\*\*|企业资源组ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|EipAddress|String|12.xx.xx.78|分配的EIP。

 |
|AllocationId|String|eip-25877c70gddh\*\*\*\*|EIP的ID。

 |
|OrderId|Long|10|订单号，仅预付费时返回。

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。

 |
|ResourceGroupId|String|rg-acfmxazfdgdg\*\*\*\*|企业资源组ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=AllocateEipAddress
&RegionId=cn-hangzhou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<AllocateEipAddressResponse>
      <AllocationId>eip-25877c70gfdkh****</AllocationId>
      <EipAddress>123.xx.xx.206</EipAddress>
      <RequestId>B6B9F518-60F8-4D81-9242-1207B356754D</RequestId>
</AllocateEipAddressResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"B6B9F518-60F8-4D81-9242-1207B356754D",
	"EipAddress":"123.xx.xx.206",
	"AllocationId":"eip-25877c70gfdkh****"
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

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

