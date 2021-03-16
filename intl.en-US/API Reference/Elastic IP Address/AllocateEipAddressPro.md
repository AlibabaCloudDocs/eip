# AllocateEipAddressPro

Applies for a specific elastic IP address \(EIP\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=AllocateEipAddressPro&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|AllocateEipAddressPro|The operation that you want to perform. Set the value to **AllocateEipAddressPro**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the EIP that you want to apply for belongs.

 You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |
|IpAddress|String|No|12.XX.XX.23|The IP address of the EIP to be requested.

 Set **IpAddress** or **InstanceId**. If you leave both parameters empty, the system randomly allocates an EIP. |
|InstanceId|String|No|eip-25877c70gddh\*\*\*\*|The ID of the EIP to be requested.

 Set **IpAddress** or **InstanceId**. If you leave both parameters empty, the system randomly allocates an EIP. |
|Bandwidth|String|No|5|The maximum bandwidth of the EIP to be requested. Unit: Mbit/s.

 Default value: **5** Mbit/s. |
|Period|Integer|No|1|The subscription duration of the EIP.

 -   If**PricingCycle** is set to **Month**, **Period** can be set from **1 to 9**.
-   If**PricingCycle** is set to **Year**, **Period** can be set from **1 to 3**.

 If **InstanceChargeType** is set to **PrePaid**, this parameter is required.

 If **InstanceChargeType** is set to **PostPaid**, ignore this parameter. |
|ISP|String|No|BGP|The line type. Default value: **BGP**.

 -   If your Alibaba Cloud account is allowed to activate single-ISP bandwidth, you can set the ISP field to **ChinaTelecom**, **ChinaUnicom**, or **ChinaMobile**.
-   This parameter is required if your workloads are deployed in the China East 1 Finance region. Set the value to **BGP\_FinanceCloud**. |
|Netmode|String|No|public|The type of network. Set the value to **public** \(Internet\).

 Default value: **public** \(Internet\). |
|AutoPay|Boolean|No|true|Specifies whether to enable automatic payments. Valid values:

 -   **false**: disables automatic payments. After an order is generated, you must go to the order center to complete the payment.
-   **true**: enables automatic payments. After an order is generated, the system automatically deducts your account balance to pay for the order.

 If **InstanceChargeType** is set to **PrePaid**, this parameter is required.

 If **InstanceChargeType** is set to **PostPaid**, ignore this parameter. |
|PricingCycle|String|No|Month|The billing cycle of a subscription EIP. Valid values:

 -   **Month**: Bills are paid on a monthly basis. This is the default value.
-   **Year**: Bills are paid on an annual basis.

 This parameter is required if **InstanceChargeType** is set to **PrePaid**. This parameter is not required if **InstanceChargeType** is set to **PostPaid**. |
|InstanceChargeType|String|No|PostPaid|The billing method of the specified EIP to be requested. Valid values:

 -   **PrePaid**: subscription.
-   **PostPaid**: pay-as-you-go. This is the default value.

 If**InstanceChargeType** is set to **PrePaid**, **InternetChargeType** must be set to **PayByBandwidth**.

 If**InstanceChargeType** is set to**PostPaid**,**InternetChargeType** can be set to **PayByBandwidth** or **PayByTraffic**. |
|InternetChargeType|String|No|PayByBandwidth|The metering method of the specified EIP to be requested. Valid values:

 -   **PayByBandwidth** \(default\): pay-by-bandwidth
-   **PayByTraffic**: pay-by-data-transfer

 If**InstanceChargeType** is set to **PrePaid**, **InternetChargeType** must be set to **PayByBandwidth**.

 If**InstanceChargeType** is set to**PostPaid**, **InternetChargeType** can be set to **PayByBandwidth** or **PayByTraffic**. |
|ResourceGroupId|String|No|rg-resourcegroup\*\*\*\*|The ID of the resource group to which the EIP belongs. |
|ClientToken|String|No|0c593ea1-3bea-11e9-b96b-88e9fe6\*\*\*\*|The client token that is used to ensure the idempotence of the request. You can use the client to generate the value, but you must ensure that it is unique among different requests. `ClientToken` can contain only ASCII characters. It must be 1 to 64 characters in length. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|AllocationId|String|eip-25877c70gddh\*\*\*\*|The ID of the EIP. |
|EipAddress|String|12.XX.XX.23|The IP address of the EIP. |
|OrderId|Long|20190000|The ID of the order. |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |
|ResourceGroupId|String|rg-resourcegroup\*\*\*\*|The ID of the resource group. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AllocateEipAddressPro
&RegionId=cn-hangzhou
&<Common Request Parameters>
```

Sample success responses

`XML` format

```
<AllocateEipAddressProResponse>
  <ResourceGroupId>rg-resourcegroup****</ResourceGroupId>
  <RequestId>4EC47282-1B74-4534-BD0E-403F3EE64CAF</RequestId>
  <AllocationId>eip-25877c70gddh****</AllocationId>
  <EipAddress>12.XX.XX.23</EipAddress>
  <OrderId>20190000</OrderId>
</AllocateEipAddressProResponse>
```

`JSON` format

```
{
    "ResourceGroupId": "rg-resourcegroup****",
    "RequestId": "4EC47282-1B74-4534-BD0E-403F3EE64CAF",
    "AllocationId": "eip-25877c70gddh****",
    "EipAddress": "12.XX.XX.23",
    "OrderId": 20190000
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|The error message returned because you do not have the permissions to perform this operation on the specified resource. You can apply for the permissions and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|The error message returned because the number of EIPs has reached the upper limit. To apply for more EIPs, submit a ticket. We recommend that you use NAT gateways.|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|The error message returned because InternetChargeType is set to an invalid value.|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|The error message returned because the specified maximum bandwidth value is invalid.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your Alibaba Cloud account has an insufficient balance. Top up your Alibaba Cloud account and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|The error message returned because the number of EIPs has reached the upper limit. To apply for more EIPs, submit a ticket. We recommend that you use NAT gateways.|
|400|ReserveIpFail|Reserve eip failed.|The error message returned because the system failed to reserve the specified EIP.|
|400|InvalidRegion.NotSupport|The specified region does not support.|The error message returned because the specified region ID does not support this operation.|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|The error message returned because the specified ID of the resource group does not exist.|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

