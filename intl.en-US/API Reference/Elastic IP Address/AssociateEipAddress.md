# AssociateEipAddress

Associates an elastic IP address \(EIP\) with an instance in the same region.

## Descriptions

When you call this operation, take note of the following limits:

-   You can associate an EIP with an Elastic Compute Service \(ECS\) instance, a Server Load Balancer \(SLB\) instance, a secondary elastic network interface \(ENI\), or a NAT gateway. These cloud resources must be deployed in virtual private clouds \(VPCs\). In addition, the cloud resources and the EIP must belong to the same region.
-   To associate an EIP with a NAT gateway, make sure that your Alibaba Cloud account does not have a NAT bandwidth plan purchased before November 3, 2017.

    If your Alibaba Cloud account has a NAT bandwidth plan purchased before November 3, 2017, to associate an EIP with a NAT gateway, perform the steps in [Why am I unable to associate an EIP in the NAT Gateway console?](~~187955~~).


## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=AssociateEipAddress&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|AssociateEipAddress|The operation that you want to perform. Set the value to **AssociateEipAddress**. |
|AllocationId|String|Yes|eip-2zeerraiwb7ujsxdc\*\*\*\*|The ID of the EIP to be associated with your cloud resource. |
|InstanceId|String|Yes|i-2zebb08phyczzawe\*\*\*\*|The ID of the cloud resource with which the EIP is associated.

 NAT gateways, SLB instances, ECS instances, secondary ENIs, and high-availability virtual IP addresses \(HAVIPs\) are supported. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the EIP belongs. |
|InstanceType|String|No|EcsInstance|The type of instance with which you want to associate the EIP. Valid values:

 -   **Nat**: a NAT gateway
-   **SlbInstance**: an SLB instance
-   **EcsInstance**: an ECS instance
-   **NetworkInterface**: a secondary ENI
-   **HaVip**: an HAVIP |
|InstanceRegionId|String|No|cn-hangzhou|The ID of the region where the cloud resource is deployed.

 **Note:** This parameter is required only if the EIP is associated with a shared-bandwidth Global Accelerator \(GA\) instance. |
|PrivateIpAddress|String|No|192.1.XX.XX|An IP address in the CIDR block of the vSwitch.

 If you do not set this parameter, the system allocates a private IP address based on the VPC ID and vSwitch ID. |
|Mode|String|No|NAT|The mode in which you associate the EIP. Valid values:

 -   **NAT** \(default\): the standard NAT mode
-   **MULTI\_BINDED**: the Multi-EIP to ENI mode
-   **BINDED**: the cut-through mode

 This parameter is required only when **InstanceType** is set to **NetworkInterface**. |
|ClientToken|String|No|0c593ea1-3bea-11e9-b96b-88e9fe63\*\*\*\*|The client token that is used to ensure the idempotence of the request. You can use the client to generate the value, but you must ensure that it is unique among different requests. `ClientToken` can contain only ASCII characters. It must be 1 to 64 characters in length. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|RequestId|String|0ED8D006-F706-4D23-88ED-E11ED28DCAC0|The ID of the request. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=AssociateEipAddress
&AllocationId=eip-2zeerraiwb7ujsxdc****
&InstanceId=i-2zebb08phyczzawe****
&<Common request parameters>
```

Sample success responses

`XML` format

```
<AssociateEipAddressResponse>
  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
</AssociateEipAddressResponse>
```

`JSON` format

```
{
    "RequestId": "0ED8D006-F706-4D23-88ED-E11ED28DCAC0"
}
```

## Errors codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|InvalidAssociation.Duplicated|Specified instance already is associated.|The error message returned because an EIP or a GA instance is already associated with this instance. Disassociate the EIP or GA instance from the instance before another EIP or GA instance can be associated with the instance.|
|400|OperationDenied|Specified instance is not in VPC.|The error message returned because the specified instance does not exist in the VPC.|
|400|InvalidParameter.Mismatch|Specified elastic IP address and ECS instance are not in the same region.|The error message returned because the specified EIP and ECS instance are not in the same region.|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation|The error message returned because the state of the EIP does not support the operation.|
|404|InvalidInstanId.NotFound|Specified instance does not exist.|The error message returned because the specified instance does not exist. Check whether the instance ID is valid.|
|400|IncorrectInstanceStatus|Current instance status does not support this operation.|The error message returned because the state of the instance does not support this operation.|
|400|InvalidInstanceType.ValueNotSupported|The specified value of InstanceType is not supported.|The error message returned because the specified value of the InstanceType parameter is invalid.|
|400|IncorrectHaVipStatus|HaVip can be operated by this action only when it's status is Available or InUse.|The error message returned because the state of the HAVIP does not support the operation. You can perform the operation only when the HAVIP is in the Available or InUse state.|
|400|InvalidParameter|The specified parameter is not valid.|The error message returned because the specified value of the parameter is invalid.|
|400|OperationDenied|Eip of default vpc not allow this operation|The error message returned because the operation is not supported by EIPs in the default VPC.|
|400|Forbbiden|The eip instance owener error|The error message returned because you are not authorized to perform this operation on the EIP. Check whether you have permissions to call this operation.|
|400|InvalidBindingStatus|The eip binding status invalid.|The error message returned because the EIP is in an invalid state.|
|400|BIND\_INSTANCE\_HAVE\_PORTMAP\_OR\_BIND\_EIP|The instance may have portMap or already bind eip.|The error message returned because the ECS instance already has a port forwarding rule configured. Delete the port forwarding rule and try again.|
|400|BIND\_INSTANCE\_OWENER\_ERROR|Cannot operate the eip.|The error message returned because you are unauthorized to manage the specified EIP.|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|The error message returned because the specified EIP does not exist. Check whether the specified value of the parameter is valid.|
|400|InvalidParams.NotFound|instance not found|The error message returned because the specified instance does not exist.|
|503|ServiceUnavailable|The request has failed due to a temporary failure of the server.|The error message returned because the request failed due to a temporary malfunction of the server.|
|400|OperationDenied.CloudBoxResourceExist|The operation is not allowed because there are resources related to the cloud box in VPC.|The error message returned because the VPC contains cloud box-related resources and the operation is not allowed.|
|400|OperationDenied.CloudBoxVSwitchExist|The operation is not allowed because a cloud box type vSwitch exists in VPC.|The error message returned because the VPC contains a vSwitch of the cloud box type and the operation is not allowed.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

