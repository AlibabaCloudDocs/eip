# ModifyEipAddressAttribute {#doc_api_Vpc_ModifyEipAddressAttribute .reference}

Modifies the name, description, and peak bandwidth of an Elastic IP Address \(EIP\).

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Vpc&api=ModifyEipAddressAttribute&type=RPC&version=2016-04-28)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|ModifyEipAddressAttribute| The name of this action.

 Value: **ModifyEipAddressAttribute**

 |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d0fo3| The instance ID of the EIP.

 |
|RegionId|String|Yes|cn-hangzhou| The region ID of the VPC to which the route table belongs.

 |
|Bandwidth|String|No|100| Optional. The peak bandwidth of the EIP. Unit: Mbit/s

 |
|Description|String|No|Description| Optional. The description of the EIP. The description must be 2 to 256 characters in length. It must start with a letter. It cannot start with `http://` or `https://`.

 |
|Name|String|No|Test123| Optional. The name of the EIP. The name must be 2 to 128 characters in length. It must start with a letter. It can contain numbers, periods \(.\), underscores \(\_\), and hyphens \(-\). It cannot start with `http://` or `https://`.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=ModifyEipAddressAttribute
&AllocationId=eip-25877c70xxxxxxxx
&Name=eip1
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<ModifyEipAddressAttributeResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</ModifyEipAddressAttributeResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## Errors {#section_ksd_zi4_1g9 .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|InsufficientBalance.Eip|Your account does not have enough balance.|Your account balance is insufficient.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The specified public IP address does not exist.|
|400|InvalidParameter|Specified value of "Bandwidth" is not supported.|The specified bandwidth is invalid.|
|500|InternalError|The request processing has failed due to some unknown error.|The request failed to be processed due to unknown errors.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The status of the specified EIP does not permit this operation.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found..|The specified public IP address does not exist.|
|400|InvalidParameter|The parameter is invalid.|The specified parameter value is invalid.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|

