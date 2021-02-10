# ModifyEipAddressAttribute

Modifies the name, description, and maximum bandwidth value of a pay-as-you-go elastic IP address \(EIP\). You cannot call this operation to modify the name, description, or maximum bandwidth value of a subscription EIP.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=ModifyEipAddressAttribute&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|ModifyEipAddressAttribute|The operation that you want to perform. Set the value to **ModifyEipAddressAttribute**. |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d\*\*\*\*|The ID of the pay-as-you-go EIP. |
|Bandwidth|String|No|100|Enter a maximum bandwidth value for the EIP. Valid values:

-   **1** to **200**: pay-by-data-transfer. Unit: Mbit/s.
-   **1** to **500**: pay-by-bandwidth. Unit: Mbit/s. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the EIP belongs. |
|Name|String|No|Test123|Enter a name for the EIP.

The name must be 2 to 128 characters in length, and can contain, digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter. The name cannot start with `http://` or `https://`. |
|Description|String|No|abc|Enter a description for the EIP.

The description must be 2 to 256 characters in length, and must start with a letter. The description cannot start with `http://` or `https://`. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|The ID of the request. |

## Examples

Sample requests

```
http(s)://vpc.aliyuncs.com/? Action=ModifyEipAddressAttribute
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<ModifyEipAddressAttributeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyEipAddressAttributeResponse>
```

`JSON` format

```
{ 
    "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InsufficientBalance.Eip|Your account does not have enough balance.|The error message returned because your account balance is insufficient. Top up your account and try again.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The error message returned because the specified EIP does not exist. Check whether the specified value of the parameter is valid.|
|400|InvalidParameter|Specified value of "Bandwidth" is not supported.|The error message returned because the specified maximum bandwidth value is invalid.|
|500|InternalError|The request processing has failed due to some unknown error.|The error message returned because unknown errors have occurred.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The error message returned because the state of the EIP does not support this operation.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found..|The error message returned because the specified EIP does not exist. Check whether the specified value of the parameter is valid.|
|400|InvalidParameter|The parameter is invalid.|The error message returned because a parameter is set to an invalid value.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The error message returned because the specified region does not exist. Check whether the specified region ID is valid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

