# ReleaseEipAddress

Releases an Elastic IP address.

## API description

Note the following before you release an Elastic IP address:

-   Only the Elastic IP addresses that are in the **Available** state can be released.
-   Only pay-as-you-go Elastic IP addresses can be released. Subscription Elastic IP addresses cannot be released.

## Make the API call

[You can use OpenAPI Explorer to make API calls, search for API calls, perform debugging, and generate SDK example code.](https://api.aliyun.com/#product=Vpc&api=ReleaseEipAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String |Yes|ReleaseEipAddress|The name of this action. Value: **ReleaseEipAddress**. |
|AllocationId|String |Yes|eip-2zeerraiwb7uj6i0d\*\*\*\*|The ID of the Elastic IP address to be released. |
|RegionId|String |Yes|cn-hangzhou|The ID of the region to which the Elastic IP address belongs. To query the region ID, call [DescribeRegions](~~36063~~). |

## Response parameters

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String |748C38F6-9A3D-482E-83FB-DB6C39C68AEA|The ID of the request. |

## Examples

Request example

```

http(s)://vpc.aliyuncs.com/? Action=ReleaseEipAddress
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<CommonParameters>

```

Response example

`XML` format

```
<ReleaseEipAddressResponse>
      <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
</ReleaseEipAddressResponse>
```

`JSON` format

```
{
	"RequestId":"748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
}
```

## Errors

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The specified public IP address does not exist.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The status of the specified Elastic IP address does not support this operation.|
|500|InternalError|The request processing has failed due to some unknown error.|The request failed to be processed due to unknown errors.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|
|400|Forbidden.ChargeTypeIsPrepaid|It's forbidden to release a prepaid EIP|Subscription Elastic IP addresses cannot be released.|
|400|Forbbiden|The eip instance owener error|You are not authorized to operate on this Elastic IP address.|
|400|TaskConflict.AssociateGlobalAccelerationInstance|Operate too frequent.|Too many requests were sent.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

