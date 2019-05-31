# ReleaseEipAddress {#reference_i4w_xmt_ndb .reference}

Releases an Elastic IP Address \(EIP\).

**Note:** Only EIPs in the **Available** state can be released.

## Debug {#apiExplorer .section}

By using [API Explorer](https://api.aliyun.com/#product=Vpc&api=DescribeVpcAttribute), you can easily debug APIs, automatically generate SDK code examples, and quickly search for APIs.

## Request parameters {#section_cch_pjg_mdb .section}

|Parameter|Type|Required?|Example value|Description|
|:--------|:---|:--------|-------------|:----------|
|Action|String|Yes|ReleaseEipAddress| The name of this action. Value:

 ReleaseEipAddress

 |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d0fo3| The ID of the EIP.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the EIP belongs.

 |

## Response parameters {#section_ugs_f1g_cz .section}

|Parameter|Type|Example value|Description|
|:--------|:---|:------------|:----------|
|RequestId|String|748C38F6-9A3D-482E-83FB-DB6C39C68AEA|The ID of the request.|

## Examples {#section_ix5_h1g_cz .section}

**Request example**

``` {#createVPCpub}

https://vpc.aliyuncs.com/?Action=ReleaseEipAddress
&AllocationId=eip-25877c70x
&<CommonParameters>

```

**Response example**

-   XML format

    ```
    <<?xml version="1.0" encoding="UTF-8" ?>
    <ReleaseEipAddressResponse>
        <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
    </ReleaseEipAddressResponse>
    ```

-   JSON format

    ```
    {
    	"RequestId":"748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
    }
    ```


## Error codes {#section_kdj_4zr_5gb .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The specified public IP address does not exist.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The current status of the specified EIP address does not support this operation.|
|500|InternalError|The request processing has failed due to some unknown error.|An error occurred while the request was being processed.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|
|400|Forbidden.ChargeTypeIsPrepaid|It's forbidden to release a prepaid EIP|The subscription EIP addresses cannot be released.|
|400|Forbbiden|The eip instance owener error|You need to be authorized to use the specified EIP. Check that you have the appropriate permissions and try again.|
|400|TaskConflict.AssociateGlobalAccelerationInstance|Operate too frequent.|The server cannot process this many requests. Please try again later.|

[See common error codes](https://error-center.aliyun.com/status/product/Vpc)

