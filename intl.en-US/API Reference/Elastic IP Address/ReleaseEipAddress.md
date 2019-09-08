# ReleaseEipAddress {#doc_api_Vpc_ReleaseEipAddress .reference}

Releases an Elastic IP Address \(EIP\).

**Note:** Only EIPs in the **Available** state can be released.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Vpc&api=ReleaseEipAddress&type=RPC&version=2016-04-28)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|ReleaseEipAddress| The name of this action.

 Value: **ReleaseEipAddress**

 |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d0fo3| The ID of the EIP to be released.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the EIP belongs. To query the region ID, call [DescribeRegions](~~36063~~).

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|748C38F6-9A3D-482E-83FB-DB6C39C68AEA| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=ReleaseEipAddress
&AllocationId=eip-25877c70x
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<<? xml version="1.0" encoding="UTF-8" ? >
<ReleaseEipAddressResponse>
    <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
</ReleaseEipAddressResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
}
```

## Errors {#section_czg_ejg_m5d .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The specified public IP address does not exist.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The status of the specified EIP does not permit this operation.|
|500|InternalError|The request processing has failed due to some unknown error.|The request failed to be processed due to unknown errors.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|
|400|Forbidden.ChargeTypeIsPrepaid|It's forbidden to release a prepaid EIP|Subscription EIPs cannot be released.|
|400|Forbbiden|The eip instance owener error|You are not authorized to release the specified EIP.|
|400|TaskConflict.AssociateGlobalAccelerationInstance|Operate too frequent.|Too many requests were sent.|

