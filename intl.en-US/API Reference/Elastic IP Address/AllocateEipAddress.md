# AllocateEipAddress

Requests an elastic IP address \(EIP\).

## Description

Before you call this operation, make sure that you understand the billing methods and pricing of EIPs. For more information, see [Billing](~~122035~~).

After you call this operation, an EIP in the **Available** state is randomly allocated in the specified region. EIPs support only the following transport layer protocols: Internet Control Message Protocol \(ICMP\), Transmission Control Protocol \(TCP\), and User Datagram Protocol \(UDP\). Internet Group Management Protocol \(IGMP\) and Stream Control Transmission Protocol \(SCTP\) are not supported.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|AllocateEipAddress|The operation that you want to perform. Set the value to **AllocateEipAddress**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where you want to create an EIP. You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |
|Bandwidth|String|No|5|The maximum bandwidth of the EIP. Valid values: **1** to **200**. Unit: Mbit/s.

 Default value: **5**. |
|Period|Integer|No|1|The subscription duration.

 When**PricingCycle** is set to **Month**, **Period** can be set from **1 to 9**.

 When**PricingCycle** is set to **Year**, **Period** can be set from **1 to 5**.

 This parameter is required when **InstanceChargeType** is set to **PrePaid**. If **InstanceChargeType** is set to **PostPaid**, ignore this parameter. |
|ISP|String|No|BGP|The line type. You can set this parameter only when you create a pay-as-you-go EIP. Valid values:

 -   **BGP**: BGP \(Multi-ISP\) lines.

Up to 89 high-quality BGP lines are available worldwide. Direct connections with multiple Internet Service Providers \(ISPs\), including Telecom, Unicom, Mobile, Railcom, Netcom, CERNET, China Broadcast Network, Dr. Peng, and Founder, can be established in all regions in mainland China.

-   **BGP\_PRO**: BGP \(Multi-ISP\) Pro lines.

BGP \(Multi-ISP\) Pro lines optimize data transmission to China and improve connection quality for international services. Compared with traditional BGP \(Multi-ISP\) lines, BGP \(Multi-ISP\) Pro lines can be used to establish direct connections without using international ISP services. Therefore, BGP \(Multi-ISP\) Pro lines reduce network latency.


 BGP \(Multi-ISP\) lines are supported in all regions. BGP \(Multi-ISP\) Pro lines are supported only in the China \(Hong Kong\) region.

 **Note:** If your account is included in the BGP \(single line\) whitelist, you can set the ISP field to **ChinaTelecom**, **ChinaUnicom**, or **ChinaMobile**. If your workloads are deployed in China East 1 Finance. Set the value to **BGP\_FinanceCloud**. |
|ActivityId|Long|No|123456|The promotion code. Ignore this parameter. |
|Netmode|String|No|public|The type of the network. Set the value to **public** \(Internet\). |
|AutoPay|Boolean|No|false|Specifies whether to enable automatic payments. Valid values:

 -   **false**: disables automatic payment. After an order is generated, you must go to the order center to complete the payment.
-   **true**: enables automatic payments. After an order is generated, the system automatically deducts you account balance to pay for the order.

 This parameter is required when **InstanceChargeType** is set to **PrePaid**. This parameter is not required when **InstanceChargeType** is set to **PostPaid**. |
|PricingCycle|String|No|Month|The billing cycle of the subscription EIP. Valid values:

 -   **Month** \(default\): Bills are paid on a monthly basis.
-   **Year**: Bills are paid on an annual basis.

This parameter is required when **InstanceChargeType** is set to **PrePaid**. This parameter is not required when **InstanceChargeType** is set to **PostPaid**. |
|InstanceChargeType|String|No|PostPaid|The billing method of the EIP. Valid values:

 -   **PrePaid**: subscription.
-   **PostPaid**: pay-as-you-go. This is the default value.

 When**InstanceChargeType** is set to **PrePaid**, set **InternetChargeType** to **PayByBandwidth**. When**InstanceChargeType** is set to **PostPaid**, set **InternetChargeType** to **PayByBandwidth** or **PayByTraffic**. |
|InternetChargeType|String|No|PayByTraffic|The metering method of the EIP. Valid values:

 -   **PayByBandwidth**: pay-by-bandwidth. This is the default value.
-   **PayByTraffic**: pay-by-data-transfer.

 When**InstanceChargeType** is set to **PrePaid**, **InternetChargeType** must be set to **PayByBandwidth**.

 When **InstanceChargeType** is set to **PostPaid**, **InternetChargeType** can be set to **PayByBandwidth** or **PayByTraffic**. |
|ResourceGroupId|String|No|rg-acfmxazffggds\*\*\*\*|The ID of the resource group. |
|ClientToken|String|No|0c593ea1-3bea-11e9-b96b-88e9fe637760|The client token that is used to ensure the idempotence of the request. You can use the client to generate the value. Make sure that the client token is unique. The **ClientToken** value can contain only ASCII characters and cannot exceed 64 characters in length. For more information, see [How to ensure idempotence](~~36569~~). |
|Name|String|No|EIP1|The name of the EIP. |
|Description|String|No|test|The description of the EIP. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipAddress|String|12.xx.xx.78|The EIP that is allocated. |
|AllocationId|String|eip-25877c70gddh\*\*\*\*|The ID of the EIP. |
|OrderId|Long|10|The order number. This parameter is returned only when **InstanceChargeType** is set to **PrePaid**. |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |
|ResourceGroupId|String|rg-acfmxazfdgdg\*\*\*\*|The ID of the resource group. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AllocateEipAddress
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AllocateEipAddressResponse>
  <RequestId>4EC47282-1B74-4534-BD0E-403F3EE64CAF</RequestId>
  <ResourceGroupId>rg-acfmxazfdgdg****</ResourceGroupId>
  <AllocationId>eip-25877c70gddh****</AllocationId>
  <EipAddress>12.xx.xx.78</EipAddress>
  <OrderId>10</OrderId>
</AllocateEipAddressResponse>
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

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to perform this operation on the specified resource. You can apply for the permissions and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|The error message returned because the number of EIPs exceeds the quota. To request a quota increase, submit a ticket. We recommend that you use NAT gateways.|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|The error message returned because InternetChargeType is set to an invalid value.|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|The error message returned because the specified bandwidth value is invalid.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your Alibaba Cloud account has an insufficient balance. Top up your account and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|The error message returned because the number of EIPs exceeds the quota. To request a quota increase, submit a ticket. We recommend that you use NAT gateways.|
|400|ReserveIpFail|Reserve eip failed.|The error message returned because the reservation for the EIP failed.|
|400|InvalidRegion.NotSupport|The specified region does not support.|The error message returned because the specified region does not support this operation.|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|The error message returned because the ID of the resource group does not exist.|
|409|OperationConflict|Request was denied due to conflict with a previos request.|The error message returned because a request conflict occurs. Try again later or submit a ticket.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

