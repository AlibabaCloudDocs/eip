# DescribeEipAddresses {#doc_api_Vpc_DescribeEipAddresses .reference}

Queries the created EIPs in a specified region.

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Vpc&api=DescribeEipAddresses&type=RPC&version=2016-04-28)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|DescribeEipAddresses| The name of this action. Value: **DescribeEipAddresses**

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to be queried. To query the region ID, call [DescribeRegions](~~36063~~).

 |
|AllocationId|String|No|eip-2zeerraiwb7ujxxxxxxxx| Optional. The ID of the EIP to be queried.

 |
|AssociatedInstanceId|String|No|i-2zebb08phycxxxxxxxx| Optional. The ID of the cloud instance associated with the EIP.

 |
|AssociatedInstanceType|String|No|EcsInstance| Optional. The type of the cloud instance associated with the EIP.

 -   **EcsInstance** \(default\): ECS instances of the VPC network
-   **SlbInstance**: Server Load Balancer \(SLB\) instances of the VPC network
-   **Nat**: NAT Gateways
-   **HaVip**: High-Availability Virtual IP Addresses \(HaVips\)

Each ECS instance, SLB instance, and HaVip can only be associated with one EIP. One NAT Gateway can be associated with multiple EIPs.


 |
|ChargeType|String|No|PostPaid| Optional. The billing method of the EIP. Value:

 **Postpaid**: Pay-As-You-Go

 |
|EipAddress|String|No|116.xx.xx.28| Optional. The IP address of the EIP. If you specify this parameter, you can view the information of a specific EIP.

 |
|Filter.1.Key|String|No|Filter.1.Name| Optional. The filter condition.

 |
|Filter.1.Value|String|No|value1| Optional. The value of the corresponding filter condition.

 |
|Filter.2.Key|String|No|Filter.2.Description| Optional. The filter condition.

 |
|Filter.2.Value|String|No|value2| Optional. The value of the corresponding filter condition.

 |
|ISP|String|No|BGP| Optional. The service provider. The value is usually BGP.

 |
|IncludeReservationData|Boolean|No|true| Optional. Indicates whether to include orders that have not taken effect. Default value: False.

 |
|LockReason|String|No|financial| Optional. The reason why the EIP is locked. Valid values:

 -   **financial**: The EIP is locked due to overdue payments.
-   **security**: The EIP is locked for security reasons.

 |
|PageNumber|Integer|No|10| Optional. The page number. Default value: **1**

 |
|PageSize|Integer|No|10| Optional. The number of entries per page in the case of a paged query result. Maximum value: **50**. Default value: **10**

 |
|ResourceGroupId|String|No|rg-acfmxazb4pxxxxxxxx| Optional. The ID of the resource group.

 |
|Status|String|No|Available| Optional. The status of the EIP. Valid values:

 -   **Associating**: The EIP is being associated with a cloud instance.
-   **Unassociating**: The EIP is being disassociated from a cloud instance.
-   **InUse**: The EIP is already allocated.
-   **Available**: The EIP is available.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|EipAddresses| | | A list of EIPs.

 |
|AllocationId|String|eip-2zeerraiwb7ujxxxxxxxx| The ID of the EIP.

 |
|AllocationTime|String|2019-04-23T01:37:38Z| The time when the EIP is created.

 |
|AvailableRegions| |cn-hangzhou| The ID of the region to which the EIP belongs.

 |
|Bandwidth|String|5| The peak bandwidth of the EIP. Unit: Mbit/s

 |
|BandwidthPackageId|String|cbwp-bp1ego3i4j07cxxxxxxxx| The ID of the Internet Shared Bandwidth instance to which the EIP is added.

 |
|BandwidthPackageType|String|CommonBandwidthPackage| The type of the Internet Shared Bandwidth instance.

 |
|ChargeType|String|PostPaid| The billing method of the EIP.

 |
|Descritpion|String|Overview| The description of the EIP.

 |
|EipBandwidth|String|101| The bandwidth of the EIP before the EIP is added to or after the EIP is removed from the Internet Shared Bandwidth instance.

 |
|ExpiredTime|String|2019-04-29T02:37:38Z| The time when the EIP expires, which follows the ISO 8601 standard and uses UTC time. It is in the format of YYYY-MM-DDThh:mmZ.

 |
|HDMonitorStatus|String|false| Indicates whether high granularity monitoring is enabled for the EIP.

 |
|HasReservationData|String|wweayhddrhht| The value is **true** only when the request parameter**IncludeReservationData** is set to **true** and orders that have not taken effect exit.

 |
|ISP|String|BGP| The service provider. The value is usually BGP.

 |
|InstanceId|String|vpc-bp15zckdt37xxxxxxxx| The ID of the cloud instance that is associated with the EIP.

 |
|InstanceRegionId|String|cn-hangzhou| The region ID of the cloud instance that is associated with the EIP.

 |
|InstanceType|String|EcsInstance| The type of the cloud instance that is associated with the EIP.

 |
|InternetChargeType|String|PayByBandwidth| The billing method of the EIP.

 |
|IpAddress|String|101.xx.xx.36| The IP address of the EIP.

 |
|Name|String|Elastic IP| The name of the EIP.

 |
|OperationLocks| | | The details of a locked EIP.

 |
|LockReason|String|financial| The reason why the EIP is locked. Valid values:

 -   **financial**: The EIP is locked due to overdue payments.
-   **security**: The EIP is locked for security reasons.

 |
|RegionId|String|cn-hangzhou| The ID of the region to which the EIP belongs.

 |
|ReservationActiveTime|String|2019-03-11T16:00:00Z| The time when a renewal takes effect.

 |
|ReservationBandwidth|String|12| The bandwidth of the EIP after the renewal.

 |
|ReservationInternetChargeType|String|PayByBandwidth| The payment method of the renewal.

 |
|ReservationOrderType|String|RENEWCHANGE| The type of the renewal order. Valid values:

 -   **RENEWCHANGE**: Change the specification.
-   **TEMP\_UPGRADE**: Temporarily upgrade the EIP.
-   **UPGRADE**: Upgrade the EIP.

 |
|ResourceGroupId|String|rg-acfmxazxxxxxxxx| The ID of the resource group.

 |
|Status|String|Associating| The status of the EIP. Valid values:

 -   **Associating**: The EIP is being associated with a cloud instance.
-   **Unassociating**: The EIP is being disassociated from a cloud instance.
-   **InUse**: The EIP is already allocated.
-   **Available**: The EIP is available.

 |
|TotalCount|Integer|10| The total number of queried entries.

 |
|PageNumber|Integer|10| The current page number.

 |
|PageSize|Integer|10| The number of entries per page.

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF| The request ID.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=DescribeEipAddresses
&RegionId=cn-hangzhou
&CommonParameters

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeEipAddressesResponse>
	  <RequestId>7EEF2D6B-D207-4197-AE37-01279C888757</RequestId>
	  <PageNumber>1</PageNumber>
	  <EipAddresses>
		    <EipAddress>
			      <ChargeType>PostPaid</ChargeType>
			      <AllocationTime>2018-01-15T11:17:30Z</AllocationTime>
			      <ResourceGroupId>rg-acfmxazxxxxxxxxx</ResourceGroupId>
			      <InstanceId></InstanceId>
			      <Description></Description>
			      <IpAddress>59.110.xx.xx</IpAddress>
			      <AllocationId>eip-2ze88m67qx5zxxxxx</AllocationId>
			      <InternetChargeType>PayByTraffic</InternetChargeType>
			      <InstanceType></InstanceType>
			      <Name></Name>
			      <Status>Available</Status>
			      <BandwidthPackageId></BandwidthPackageId>
			      <InstanceRegionId></InstanceRegionId>
			      <BandwidthPackageType></BandwidthPackageType>
			      <RegionId>cn-beijing</RegionId>
			      <OperationLocks></OperationLocks>
			      <ExpiredTime></ExpiredTime>
			      <AvailableRegions>
				        <AvailableRegion>cn-beijing</AvailableRegion>
			      </AvailableRegions>
              <Bandwidth>1</Bandwidth>
		    </EipAddress>
	  </EipAddresses>
	  <TotalCount>1</TotalCount>
	  <PageSize>10</PageSize>
</DescribeEipAddressesResponse>
```

`JSON` format

``` {#json_return_success_demo}
{
	"DescribeEipAddressesResponse":{
		"PageNumber":"1",
		"EipAddresses":{
			"EipAddress":{
				"ChargeType":"PostPaid",
				"Status":"Available",
				"RegionId":"cn-beijing",
				"ResourceGroupId":"rg-acfmxazxxxxxxxx",
				"AllocationTime":"2018-01-15T11:17:30Z",
				"IpAddress":"59.110.xx.xx",
				"AllocationId":"eip-2ze88m67qx5zxxxxx",
				"AvailableRegions":{
					"AvailableRegion":"cn-beijing"
				},
				"InternetChargeType":"PayByTraffic",
				"Bandwidth":"1"
			}
		},
		"TotalCount":"1",
		"PageSize":"10",
		"RequestId":"7EEF2D6B-D207-4197-AE37-01279C888757"
	}
}
```

## Errors {#section_r0v_nsw_3qr .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist. Please check if the specified region is correct.|
|404|InvalidFilterKey.NotFound| |The specified filter key is invalid.|
|404|InvalidFilterValue| |The specified filter value is invalid.|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|The reason why the EIP is locked is unknown.|
|400|InvalidIAssociatedInstanceType.ValueNotSupported|The specified value of AssociatedInstanceType is not supported.|The specified value of AssociatedInstanceType is invalid.|
|400|InvalidChargeType.ValueNotSupported|The specified ChargeType is not supported.|The specified billing method is not supported. Please select another billing method.|

