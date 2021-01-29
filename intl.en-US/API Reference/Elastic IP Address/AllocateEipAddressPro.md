# AllocateEipAddressPro

Applies for a specified elastic IP address \(EIP\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer automatically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddressPro&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|AllocateEipAddressPro|The operation that you want to perform. Set the value to **AllocateEipAddressPro**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where you want to apply for the specified EIP.

 You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |
|IpAddress|String|No|12.xx.xx.23|The IP address of the specified EIP to be applied.

 Specify **IpAddress** or **InstanceId**. If you leave this parameter empty, the system randomly allocates an EIP. |
|InstanceId|String|No|eip-25877c70gddh\*\*\*\*|The ID of the specified EIP to be applied.

 Specify **IpAddress** or **InstanceId**. If you leave this parameter empty, the system randomly allocates an EIP. |
|Bandwidth|String|No|5|The maximum bandwidth of the specified EIP to be applied. Unit: Mbit/s.

 Default value: **5**. |
|Period|Integer|No|1|The subscription duration of the EIP.

 -   When**PricingCycle** is set to **Month**, **Period** can be set from **1 to 9**.
-   When**PricingCycle** is set to **Year**, **Period** can be set from **1 to 3**.

 This parameter is required when **InstanceChargeType** is set to **PrePaid**.

 Ignore this parameter when **InstanceChargeType** is set to **PostPaid**. |
|ISP|String|No|BGP|The line type. Default value: **BGP**.

 -   If your account is in the single-path BGP whitelist, you can set the ISP field to **ChinaTelecom**, **ChinaUnicom**, or **ChinaMobile**.
-   This parameter is required if your workloads are deployed in China East 1 Finance. Set the value to **BGP\_FinanceCloud**. |
|Netmode|String|No|public|The type of network. Set the value to **public** \(Internet\).

 Default value: **public** \(Internet\). |
|AutoPay|Boolean|No|true|Specifies whether to enable automatic payment. Valid values:

 -   **false**: disables automatic payment. If you select this option, after the system generates an order, you must go to Billing Management to complete the payment.
-   **true**: enables automatic payment. If you select this option, after the system generates an order, the system automatically deducts funds from your account to pay for the order.

 This parameter is required when **InstanceChargeType** is set to **PrePaid**.

 Ignore this parameter when **InstanceChargeType** is set to **PostPaid**. |
|PricingCycle|String|No|Month|The billing cycle of a subscription EIP. Valid values:

 -   **Month**: Bills are paid on a monthly basis. This is the default value.
-   **Year**: Bills are paid on an annual basis.

 This parameter is required when **InstanceChargeType** is set to **PrePaid**. This parameter is not required when **InstanceChargeType** is set to **PostPaid**. |
|InstanceChargeType|String|No|PostPaid|The billing method of the specified EIP to be applied. Valid values:

 -   **PrePaid**: subscription.
-   **PostPaid**: pay-as-you-go. This is the default value.

 When**InstanceChargeType** is set to **PrePaid**, **InternetChargeType** must be set to **PayByBandwidth**.

 When**InstanceChargeType** is set to**PostPaid**,**InternetChargeType** can be set to **PayByBandwidth** or **PayByTraffic**. |
|InternetChargeType|String|No|PayByBandwidth|The billing method of the specified EIP to be applied. Valid values:

 -   **PayByBandwidth** \(default\): pay-by-bandwidth
-   **PayByTraffic**: pay-by-data-transfer

 When**InstanceChargeType** is set to **PrePaid**, **InternetChargeType** must be set to **PayByBandwidth**.

 When**InstanceChargeType** is set to**PostPaid**, **InternetChargeType** can be set to **PayByBandwidth** or **PayByTraffic**. |
|ResourceGroupId|String|No|rg-resourcegroup\*\*\*\*|The ID of the resource group to which the EIP belongs. |
|ClientToken|String|No|0c593ea1-3bea-11e9-b96b-88e9fe637760|The token used to ensure idempotence. You can use the client to generate a token, but you must make sure that it is unique among different requests. The token can contain only ASCII characters and cannot exceed 64 characters in length. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AllocationId|String|eip-25877c70gddh\*\*\*\*|The ID of the EIP. |
|EipAddress|String|123.xx.xx.206|The IP address of the EIP. |
|OrderId|Long|20190000|The ID of the order. |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |
|ResourceGroupId|String|rg-resourcegroup\*\*\*\*|The ID of the resource group to which the EIP belongs. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AllocateEipAddressPro
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample responses

`XML` format

```
<AllocateEipAddressProResponse>
      <RequestId>473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E</RequestId>
      <AllocationId>eip-25877c70gddh****</AllocationId>
      <EipAddress>123.xx.xx.206</EipAddress>
      <OrderId>20190000</OrderId>
      <ResourceGroupId>rg-resourcegroup****</ResourceGroupId>
</AllocateEipAddressProResponse>
```

`JSON` format

```
{
	"RequestId":"473469C7-AA6F-4DC5-B3DB-A3DC0DE3C83E",
    "AllocationId":"eip-25877c70gddh****",
    "EipAddress":"123.xx.xx.206",
    "OrderId":"20190000",
    "ResourceGroupId":"rg-resourcegroup****"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|The error message returned because you are unauthorized to perform this operation on the specified resource. You can apply for the permissions and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|The error message returned because the number of EIPs exceeds the quota. To apply for more EIPs, submit a ticket. We recommend that you use NAT gateways.|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|The error message returned because the specified value of the InternetChargeType parameter is invalid.|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|The error message returned because the specified maximum bandwidth value is invalid.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your account has an insufficient balance. Top up your account and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|The error message returned because the number of EIPs exceeds the quota. To apply for more EIPs, submit a ticket. We recommend that you use NAT gateways.|
|400|ReserveIpFail|Reserve eip failed.|The error message returned because the system failed to reserve the specified EIP.|
|400|InvalidRegion.NotSupport|The specified region does not support.|The error message returned because the region with the specified ID does not support this operation.|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|The error message returned because the specified value of the ResourceGroupId parameter does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

