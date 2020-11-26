# AllocateEipAddress

Applies for an elastic IP address \(EIP\).

## Description

Before you call this operation, make sure that you have understood the billing methods and pricing of EIPs. For more information, see [Billing methods](~~122035~~).

After you call this operation, an EIP in the **Available** state is randomly allocated in a specified region. EIPs support only the following transport layer protocols: ICMP, TCP, and UDP.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|AllocateEipAddress|The operation that you want to perform. Set the value to **AssociateEipAddress**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where you want to create an EIP. You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |
|Bandwidth|String|No|5|The maximum bandwidth of the EIP. Valid values:**1** to **200**. Unit: Mbit/s.

Default value: **5**. |
|Period|Integer|No|1|The subscription duration of the EIP.

When**PricingCycle** is set to **Month**, **Period** can be set from **1 to 9**.

When**PricingCycle** is set to **Year**, **Period** can be set from **1 to 5**.

This parameter is required when **InstanceChargeType**is set to**PrePaid**. If **InstanceChargeType** is set to **PostPaid**, ignore this parameter. |
|ISP|String|No|BGP|The type of lines. Valid values:

-   **BGP**: BGP \(Multi-ISP\) lines.

Up to 89 high-quality BGP lines are available worldwide. Direct connections with multiple Internet Service Providers \(ISPs\), including Telecom, Unicom, Mobile, Railcom, Netcom, CERNET, China Broadcast Network, Dr. Peng, and Founder, can be established in all regions in mainland China.

-   **BGP\_PRO**: BGP \(Multi-ISP\) Pro lines.

BGP \(Multi-ISP\) Pro lines are provided to optimize data transmission to mainland China and improve connection quality for international services. Compared with traditional BGP \(Multi-ISP\) lines, BGP \(Multi-ISP\) Pro lines can be used to establish direct connection without the use of international ISP services and reduce network latency.


BGP \(Multi-ISP\) lines are supported in all regions. BGP \(Multi-ISP\) Pro lines are supported in only China \(Hong Kong\).

**Note:** If your account is in the BGP \(single line\) whitelist, you can set the ISP field to **ChinaTelecom**,**ChinaUnicom**, or **ChinaMobile**. If your workloads are deployed in China East 1 Finance. Set the value to **BGP\_FinanceCloud**. |
|ActivityId|Long|No|None|The promotion code. Ignore this parameter. |
|Netmode|String|No|public|The network type. Set the value to **public** \(Internet\). |
|AutoPay|Boolean|No|false|Specifies whether to enable automatic payments. Valid values:

**false**: disables automatic payments. After an order is generated, you must go to Billing Management \> Orders to complete the payment.

**true**: enables automatic payments. The system automatically deducts funds from your account to pay for orders.

This parameter is required when **InstanceChargeType** is set to **PrePaid**. If **InstanceChargeType** is set to **PostPaid**, this parameter is not required. |
|PricingCycle|String|No|Month|The billing cycle of subscription EIPs. Valid values:

**Month**: Bills are paid on a monthly basis. This is the default value.

**Year**: Bills are paid on an annual basis.

This parameter is required when **InstanceChargeType** is set to **PrePaid**. If **InstanceChargeType** is set to **PostPaid**, this parameter is not required. |
|InstanceChargeType|String|No|PostPaid|The billing method of the EIP. Valid values:

**PrePaid**: the subscription billing method.

**PostPaid**: the pay-as-you-go billing method. This is the default value.

When**InstanceChargeType** is set to **PrePaid**, set **InternetChargeType** to **PayByBandwidth**. When**InstanceChargeType** is set to **PostPaid**, set **InternetChargeType** to **PayByBandwidth** or **PayByTraffic**. |
|InternetChargeType|String|No|PayByTraffic|The billing method of the EIP. Valid values:

**PayByBandwidth**: the pay-by-bandwidth billing method. This is the default value.

**PayByTraffic**: the pay-by-data-transfer billing method.

When**InstanceChargeType** is set to **PrePaid**, **InternetChargeType** must be set to **PayByBandwidth**.

When**InstanceChargeType** is set to**PostPaid**, **InternetChargeType** can be set to **PayByBandwidth** or **PayByTraffic**. |
|ResourceGroupId|String|No|rg-acfmxazffggds\*\*\*\*|The ID of the resource group. |
|ClientToken|String|No|0c593ea1-3bea-11e9-b96b-88e9fe637760|The client token that is used to ensure the idempotence of the request. You can use the client to generate the parameter value, but you must ensure that it is unique among different requests. The **ClientToken** value can only contain ASCII characters and cannot exceed 64 characters in length. For more information, see [How can I ensure idempotence?](~~36569~~) |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipAddress|String|12.xx.xx.78|The allocated EIP. |
|AllocationId|String|eip-25877c70gddh\*\*\*\*|The ID of the EIP. |
|OrderId|Long|10|Order number. It is returned only when **InstanceChargeType** is set to **PrePaid**. |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |
|ResourceGroupId|String|rg-acfmxazfdgdg\*\*\*\*|The ID of the resource group to which the elastic IP address belongs. |

## Examples

Sample requests

```
http(s)://vpc.aliyuncs.com/? Action=AllocateEipAddress
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<RequestId>4EC47282-1B74-4534-BD0E-403F3EE64CAF</RequestId>
<ResourceGroupId>rg-acfmxazfdgdg****</ResourceGroupId>
<AllocationId>eip-25877c70gddh****</AllocationId>
<EipAddress>12.xx.xx.78</EipAddress>
<OrderId>10</OrderId>
```

`JSON` format

```
{
    "RequestId": "4EC47282-1B74-4534-BD0E-403F3EE64CAF",
    "ResourceGroupId": "rg-acfmxazfdgdg****",
    "AllocationId": "eip-25877c70gddh****",
    "EipAddress": "12.xx.xx.78",
    "OrderId": 10
}
```

## Error codes

|Http Status Code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|The error message returned because you are not authorized to perform this operation on the specified resource. You can apply for permissions and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|The error message returned because the number of elastic IP addresses exceeds the quota limit. To request a quota increase, submit a ticket. We recommend that you use NAT gateways.|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|The error message returned because the value of InternetChargeType is invalid.|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|The error message returned because the specified bandwidth value is invalid.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your account has insufficient funds. Top up your account and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|The error message returned because the number of elastic IP addresses exceeds the threshold. To obtain more elastic IP addresses, submit a ticket. We recommend that you use NAT gateways.|
|400|ReserveIpFail|Reserve eip failed.|The error message returned because the reservation for the specified elastic IP address failed.|
|400|InvalidRegion.NotSupport|The specified region does not support.|The error message returned because the region with the specified ID does not support this operation.|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|The error message returned because the the specified parameter value of ResourceGroupId does not exist.|
|409|OperationConflict|Request was denied due to conflict with a previos request.|The error message returned because a request conflict occurred. Try again later or submit a ticket.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

