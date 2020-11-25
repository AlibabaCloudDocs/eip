# ModifyEipAddressAttribute

Modifies the name, description, and peak bandwidth of an Elastic IP address.

## Make the API call

[You can use OpenAPI Explorer to make API calls, search for API calls, perform debugging, and generate SDK example code.](https://api.aliyun.com/#product=Vpc&api=ModifyEipAddressAttribute&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|ModifyEipAddressAttribute|The name of this action. Value:**ModifyEipAddressAttribute**. |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d\*\*\*\*|The ID of the Elastic IP address to be modified. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the Elastic IP address belongs. |
|Bandwidth|String|No|100|The peak bandwidth of the Elastic IP address. Value range: **1** to **200**. Unit: Mbit/s. |
|Description|String|No|abc|The description of the Elastic IP address.

 The description must be 2 to 256 characters in length. It must start with a letter, and cannot start with `http://` or `https://`. |
|Name|String|No|Test123|The name of the Elastic IP address.

 The name must be 2 to 128 characters in length. It must start with a letter and can contain numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). It cannot start with `http://` or `https://`. |

## Response parameters

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |

## Examples

Request example

```

http(s)://vpc.aliyuncs.com/? Action=ModifyEipAddressAttribute
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<CommonParameters>

```

Response example

`XML` format

```
<ModifyEipAddressAttributeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyEipAddressAttributeResponse>
```

`JSON` format

```
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## Errors

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InsufficientBalance.Eip|Your account does not have enough balance.|Your account balance is insufficient.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The specified public IP address does not exist.|
|400|InvalidParameter|Specified value of "Bandwidth" is not supported.|The specified bandwidth is invalid.|
|500|InternalError|The request processing has failed due to some unknown error.|The request failed to be processed due to unknown errors.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The status of the specified Elastic IP address does not support this operation.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found..|The specified public IP address does not exist.|
|400|InvalidParameter|The parameter is invalid.|The value of the specified parameter is invalid.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

