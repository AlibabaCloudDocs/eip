# AllocateEipSegmentAddress

Applies for contiguous elastic IP addresses \(EIPs\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=AllocateEipSegmentAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|AllocateEipSegmentAddress|The operation that you want to perform. Set the value to **AllocateEipSegmentAddress**. |
|EipMask|String|Yes|/32|The mask of the contiguous EIP group. Valid values:

 -   **28**: 16 contiguous EIPs are allocated for one call.
-   **27**: 32 contiguous EIPs are allocated for one call.
-   **26**: 64 contiguous EIPs are allocated for one call.
-   **25**: 128 contiguous EIPs are allocated for one call.
-   **24**: 256 contiguous EIPs are allocated for one call.

 **Note:** The actual number of assigned EIPs may be less than the expected number because one, three, or four EIPs may be reserved. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the contiguous EIPs belongs. You can call the [DescribeRegions](~~36063~~) operation to query the region IDs. |
|ClientToken|String|No|02fb3da4-130e-11e9-8e44-001sdfg|The client token that is used to ensure the idempotence of the request. Each client generates a unique token to identify different requests. The token can contain only ASCII characters and cannot exceed 64 characters in length. |
|Bandwidth|String|No|5|The maximum bandwidth of the contiguous EIPs. Unit: Mbit/s. Default value: **5**. |
|Netmode|String|No|public|The network type. Valid values:

 -   **public**: the Internet. This is the default value. After contiguous EIPs are associated with cloud resources, the cloud resources can access the Internet by using the EIPs.
-   **hybrid**: the hybrid cloud. After contiguous EIPs are associated with cloud resources, the cloud resources can access the hybrid cloud by using the EIPs.

 **Note:** This network type is available only to users who are added to the whitelist. To use this network type, contact your customer manager. |
|InternetChargeType|String|No|PayByBandwidth|The metering method of the contiguous EIPs. Valid values:

 -   **PayByBandwidth**: Fees are charged based on bandwidth usage. This is the default value.
-   **PayByTraffic**: Fees are charged based on data transfer.

 **Note:** If the **Netmode** parameter is set to **hybrid**, **InternetChargeType** is set to **PayByBandwidth**. |
|ResourceGroupId|String|No|rg-bp67acfmxazb4ph\*\*\*\*|The ID of the resource group to which the EIPs belong. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipSegmentInstanceId|String|eipsg-2zett8ba055tbsxme\*\*\*\*|The ID of the contiguous EIP group. |
|OrderId|Long|20190000|The ID of the order. |
|RequestId|String|F7A6301A-64BA-41EC-8284-8F4838C15D1F|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=AllocateEipSegmentAddress
&EipMask=/32
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AllocateEipSegmentAddressResponse>
      <RequestId>F7A6301A-64BA-41EC-8284-8F4838C15D1F</RequestId>
      <EipSegmentInstanceId>eipsg-2zett8ba055tbsxme****</EipSegmentInstanceId>
      <OrderId>20190000</OrderId>
</AllocateEipSegmentAddressResponse>
```

`JSON` format

```
{
    "RequestId":"F7A6301A-64BA-41EC-8284-8F4838C15D1F",
    "EipSegmentInstanceId":"eipsg-2zett8ba055tbsxme****",
    "OrderId":"20190000"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|The error message returned because you are not authorized to perform this operation on the specified resource. You can apply for the permissions and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|The error message returned because the number of EIPs exceeds the threshold. To obtain more EIPs, submit a ticket. We recommend that you use NAT gateways.|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|The error message returned because the specified InternetChargeType parameter value is invalid.|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|The error message returned because the specified bandwidth value is invalid.|
|400|InsufficientBalance|Your account does not have enough balance.|The error message returned because your account has an insufficient balance. Top up your account and try again.|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|The error message returned because the number of EIPs exceeds the threshold. To obtain more EIPs, submit a ticket. We recommend that you use NAT gateways.|
|400|ReserveIpFail|Reserve eip failed.|The error message returned because the reservation for the specified elastic IP address failed.|
|400|InvalidRegion.NotSupport|The specified region does not support.|The error message returned because the region with the specified ID does not support this operation.|
|409|OperationConflict|Request was denied due to conflict with a previos request.|The error message returned because a request conflict occurs. Try again later or submit a ticket.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

