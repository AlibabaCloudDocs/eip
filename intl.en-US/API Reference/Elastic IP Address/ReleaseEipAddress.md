# ReleaseEipAddress

Releases a specific elastic IP address \(EIP\).

## Description

Before you release an EIP, make sure that the EIP meets the following requirements:

-   You can release only an EIP that is in the **Available** state.
-   You can release only pay-as-you-go EIPs. You cannot release subscription EIPs.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=ReleaseEipAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ReleaseEipAddress|The operation that you want to perform. Set the value to **ReleaseEipAddress**. |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d\*\*\*\*|The ID of the EIP that you want to release. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the EIP that you want to release belongs. You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|748C38F6-9A3D-482E-83FB-DB6C39C68AEA|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=ReleaseEipAddress
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ReleaseEipAddressResponse>
      <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
</ReleaseEipAddressResponse>
```

`JSON` format

```
{
  "RequestId": "748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The error message returned because the specified EIP does not exist. Check whether the specified value of the parameter is valid.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The error message returned because the specified state of the EIP does not support this operation.|
|500|InternalError|The request processing has failed due to some unknown error.|The error message returned because unknown errors have occurred.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The error message returned because the specified region ID does not exist. Check whether the specified region ID is valid.|
|400|Forbidden.ChargeTypeIsPrepaid|It's forbidden to release a prepaid EIP|The error message returned because you cannot release subscription EIPs.|
|400|Forbbiden|The eip instance owener error|The error message returned because you are not authorized to perform this operation on the EIP. Check whether you have permissions to call this operation.|
|400|TaskConflict.AssociateGlobalAccelerationInstance|Operate too frequent.|The error message returned because too many requests are sent.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

