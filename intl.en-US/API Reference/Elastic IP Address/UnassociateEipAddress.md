# UnassociateEipAddress

Disassociates an elastic IP address \(EIP\) from a cloud resource.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=UnassociateEipAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|UnassociateEipAddress|The operation that you want to perform. Set the value to **UnassociateEipAddress**. |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6i0d\*\*\*\*|The ID of the EIP that you want to disassociate. You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |
|Force|Boolean|No|false|Specifies whether to disassociate the EIP from a NAT gateway if a DNAT or SNAT entry is added to the NAT gateway. Valid values:

-   **false** \(default\): does not disassociate the EIP from a NAT gateway if a DNAT or SNAT entry is added to the NAT gateway.
-   **true**: disassociates the EIP from a NAT gateway if a DNAT or SNAT entry is added to the NAT gateway. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the EIP that you want to disassociate belongs. |
|InstanceId|String|No|i-hp3akk9irtd69jad\*\*\*\*|The ID of the cloud resource from which you want to disassociate the EIP. |
|InstanceType|String|No|EcsInstance|The type of the cloud resource from which you want to disassociate the EIP. Valid values:

-   **EcsInstance** \(default\): an Elastic Compute Service \(ECS\) instance that is deployed in a virtual private cloud \(VPC\)
-   **SlbInstance**: a Server Load Balancer \(SLB\) instance that is deployed in a VPC
-   **NetworkInterface**: a secondary elastic network interface \(ENI\) that is deployed in a VPC
-   **Nat**: a NAT gateway
-   **HaVip** a high-availability virtual IP address \(HAVIP\) |
|PrivateIpAddress|String|No|192.XX.XX.2|The private IP address of the ECS instance or the secondary ENI from which you want to disassociate the EIP. |
|ClientToken|String|No|02fb3da4-130e-11\*\*\*\*|The client token that is used to ensure the idempotence of the request. You can use the client to generate the value, but you must ensure that it is unique among different requests.`ClientToken` can contain only ASCII characters and cannot exceed 64 characters in length. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|The ID of the request. |

## Examples

Sample requests

```
  
 
&<Common request parameters>
```

Sample success responses

`XML` format

```
<UnassociateEipAddressResponse>
      <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</UnassociateEipAddressResponse>
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
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The error message returned because the specified EIP does not exist. Check whether the specified value of the parameter is valid.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|The error message returned because the state of the EIP does not support this operation.|
|400|InvalidInstanceId.NotFound|Specified instance does not exist.|The error message returned because the specified instance does not exist. Check whether the specified instance is valid.|
|400|IncorrectInstanceStatus|The current status of instance does not support this operation.|The error message returned because the state of the instance does not support this operation.|
|400|InvalidInstanceType.ValueNotSupported|The specified value of InstanceType is not supported.|The error message returned because the specified value of the InstanceType parameter is invalid.|
|400|IncorrectHaVipStatus|This operation is denied because satus of the specified HaVip is neither Available nor InUse.|The error message returned because you cannot perform the operation when the specified HAVIP is in the Available or InUse state.|
|400|OperationDenied|Eip of default vpc not allow this operation|The error message returned because you cannot perform the operation when the EIP is associated with a cloud resource in the default VPC.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The error message returned because the specified region ID does not exist. Check whether the specified region ID is valid.|
|400|InvalidParameter|The specified parameter is not valid.|The error message returned because the specified value of the parameter is invalid.|
|400|Forbbiden|The eip instance owener error|The error message returned because you are not authorized to perform this operation on the EIP. Check whether you have permissions to call this operation.|
|400|InvalidBindingStatus|The eip binding status invalid.|The error message returned because the EIP is in an invalid state.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

