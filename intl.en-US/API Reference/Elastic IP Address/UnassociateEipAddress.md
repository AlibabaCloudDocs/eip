# UnassociateEipAddress {#doc_api_Vpc_UnassociateEipAddress .reference}

Disassociates an Elastic IP Address \(EIP\) from a cloud resource.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Vpc&api=UnassociateEipAddress&type=RPC&version=2016-04-28)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|UnassociateEipAddress| The name of this action.

 Value: **UnassociateEipAddress**

 |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d0fo3| The instance ID of the EIP.

 |
|InstanceId|String|Yes|i-12345678| The instance ID of the cloud resource to be disassociated.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the EIP belongs.

 |
|InstanceType|String|No|EcsInstance| Optional. The type of the cloud resource instance to be disassociated. Valid values:

 -   EcsInstance \(default\): ECS instances of the VPC type
-   SlbInstance: Server Load Balancer \(SLB\) instances of the VPC type
-   Nat: NAT Gateways
-   HaVip: High-Availability Virtual IP Addresses \(HaVips\)

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|RequestId|String|220F3179-5238-47F0-A0CA-1272AA2BC41F| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=UnassociateEipAddress
&AllocationId=eip-25877c70x
&InstanceId=i-25skktcp4
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<UnassociateEipAddressResponse>
	  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</UnassociateEipAddressResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## Errors {#section_8iy_wtb_hcz .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The status of the specified EIP does not permit this operation.|
|400|InvalidInstanceId.NotFound|Specified instance does not exist.|The specified instance does not exist.|
|400|IncorrectInstanceStatus|The current status of instance does not support this operation.|The status of the instance does not permit this operation.|
|400|InvalidInstanceType.ValueNotSupported|The specified value of InstanceType is not supported.|The value of InstanceType is invalid.|
|400|IncorrectHaVipStatus|This operation is denied because status of the specified HaVip is neither Available nor InUse.|This operation cannot be performed because the HaVip is not in the Available or InUse state.|
|400|OperationDenied|Eip of default vpc not allow this operation|The EIP of the default VPC does not support this operation.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|
|400|InvalidParameter|The specified parameter is not valid.|The specified parameter value is invalid.|
|400|Forbbiden|The eip instance owener error|You are not authorized to call this EIP.|
|400|InvalidBindingStatus|The eip binding status invalid.|The associating status of the EIP is invalid.|

