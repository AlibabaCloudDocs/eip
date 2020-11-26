# DescribeEipAddresses

You can call this operation to query the Elastic IP addresses \(EIPs\) that are created in a specified region.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=DescribeEipAddresses&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEipAddresses|The operation that you want to perform. Set the value to **DescribeEipAddresses**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the EIPs are created. You can call the [DescribeRegions](~~36063~~) operation to query the region ID. |
|IncludeReservationData|Boolean|No|true|Specifies whether to return data of orders that have not taken effect. Valid values:

 -   **false**: Data of orders that have not taken effect is not returned. This is the default value.
-   **true**: Data of orders that have not taken effect is returned. |
|Status|String|No|Available|The status of the EIP. Valid values:

 -   **Associating**: The EIP is being bound to an instance.
-   **Unassociating**: The EIP is being unbound from an instance.
-   **InUse**: The EIP is allocated and in use.
-   **Available**: The EIP is available for use. |
|EipAddress|String|No|116.xx.xx.28|The IP address of the EIP to be queried.

 You can enter the IP addresses of up to 50 EIPs. Separate multiple IP addresses with commas \(,\).

 **Note:** If both the **EipAddress** and **AllocationId** parameters are set, you can enter the IP addresses of 50 EIPs in **EipAddress**, and enter the IDs of the 50 EIPs in **AllocationId**. |
|AllocationId|String|No|eip-2zeerraiwb7ujxscd\*\*\*\*|The ID of the EIP instance to be queried.

 You can enter IDs of up to 50 EIP instances. Separate the instance IDs with commas \(,\).

 **Note:** If both the **EipAddress** and **AllocationId** parameters are specified, you can enter the IDs of up to 50 EIP instances in **AllocationId**, and enter the IP addresses of the 50 EIPs in **EipAddress**. |
|SegmentInstanceId|String|No|eipsg-t4nr90yik5oy38xdy\*\*\*\*|The ID of the instance with which the contiguous EIP is associated. |
|ResourceGroupId|String|No|rg-acfmxazb4pcdvf\*\*\*\*|The ID of the resource group to which the EIP belongs. |
|PageNumber|Integer|No|10|The number of the page to return. Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page. Maximum value: **100**. Default value: **10**. |
|ISP|String|No|BGP|The type of connection. Valid values:

 -   **BGP**: BGP \(Multi-ISP\) lines.

Up to 89 high-quality BGP lines are available worldwide. Direct connections with multiple Internet Service Providers \(ISPs\), including Telecom, Unicom, Mobile, Railcom, Netcom, CERNET, China Broadcast Network, Dr. Peng, and Founder, can be established in all regions in mainland China.

-   **BGP\_PRO**: BGP \(Multi-ISP\) Pro lines.

BGP \(Multi-ISP\) Pro lines are provided to optimize data transmission to mainland China and improve connection quality for international services. Compared with traditional BGP \(Multi-ISP\) lines, BGP \(Multi-ISP\) Pro lines can be used to establish direct connection without using international ISPs services and reduce network latency.


 BGP \(Multi-ISP\) lines are supported in all regions. BGP \(Multi-ISP\) Pro lines are supported only in China \(Hong Kong\).

 **Note:** If your account is in the BGP \(single line\) whitelist, you can set the ISP field to**ChinaTelecom**,**ChinaUnicom**, or**ChinaMobile**. This parameter is required if you are connected to China East 1 Finance. Set the value to **BGP\_FinanceCloud**. |
|Filter.1.Key|String|No|CreationStartTime|The filter key used to query resources. Set the value to **CreationStartTime** to specify the start time when resources were created. |
|Filter.2.Key|String|No|CreationEndTime|The filter key used to query resources. Set the value to **CreationEndTime** to specify the end time when resources were created. |
|Filter.1.Value|String|No|2018-01-22T09:12Z|The filter value used to query resources. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|Filter.2.Value|String|No|2018-01-22T09:15Z|The filter value used to query resources. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. |
|LockReason|String|No|financial|The reason why the EIP is locked. Valid values:

 -   **financial**: The EIP is locked due to overdue payments.
-   **security**: The EIP is locked for security reasons. |
|AssociatedInstanceType|String|No|EcsInstance|The type of the instance to which you want to bind the EIP. Valid value:

 -   **EcsInstance**: an Elastic Compute Service \(ECS\) instance in a VPC network. This is the default value.
-   **SlbInstance**: an Server Load Balancer \(SLB\) instance in a VPC network.
-   **Nat**: a NAT gateway.
-   **HaVip**: a High-Availability Virtual IP Address \(HaVip\).
-   **NetworkInterface**: a secondary Elastic Network Interface \(ENI\).

Only one EIP can be bound to each ECS instance, SLB instance, or HaVip. You can bind multiple EIPs to a NAT gateway. The number of EIPs that you can bind to a secondary ENI depends on the EIP binding mode. For more information, see [Elastic IP Address overview](~~88991~~). |
|AssociatedInstanceId|String|No|i-2zebb08phyccdvf\*\*\*\*|The ID of the instance associated with the EIP. |
|ChargeType|String|No|PostPaid|The billing method of the EIP. Valid values:

 **PostPaid**: pay-as-you-go. |
|DryRun|Boolean|No|false|Specifies whether to precheck only this request. Valid values:

 -   **true**: The request is checked but instances are not queried. The system checks whether your AccessKey pair is valid, whether RAM users are authorized, and whether required parameters are specified. An error message is returned if you fail the check. If you pass the check, the DryRunOperation error code is returned.
-   **false**: The request is checked. This is the default value. If you pass the check, a 2XX HTTP status code is returned and resource availability is queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipAddresses|Array| |Details about the queried EIP. |
|EipAddress| | | |
|AllocationId|String|eip-2zeerraiwb7ujcdvf\*\*\*\*|The ID of the EIP. |
|AllocationTime|String|2019-04-23T01:37:38Z|The time when the EIP was created. |
|AvailableRegions|List|cn-hangzhou|The ID of the region to which the EIP belongs. |
|Bandwidth|String|5|The peak bandwidth of the EIP. Unit: Mbit/s. |
|BandwidthPackageBandwidth|String|50|The bandwidth value of the EIP Bandwidth Plan to which the EIP is added. |
|BandwidthPackageId|String|cbwp-bp1ego3i4j07ccdvf\*\*\*\*|The ID of the EIP Bandwidth Plan. |
|BandwidthPackageType|String|CommonBandwidthPackage|The type of the bandwidth. Only **CommonBandwidthPackage** \(EIP Bandwidth Plan\) is returned. |
|ChargeType|String|PostPaid|The billing method of the EIP.

 -   **PrePaid**: subscription.
-   **PostPaid**: pay-as-you-go. |
|DeletionProtection|Boolean|true|Indicates whether deletion protection is enabled.

 -   **true**: enabled.
-   **false**: disabled. |
|Descritpion|String|abc|The description of the EIP. |
|EipBandwidth|String|101|The bandwidth of the EIP before it is added to or after it is removed from the EIP Bandwidth Plan. |
|ExpiredTime|String|2019-04-29T02:00Z|The expiration date. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time must be in UTC. Format: YYYY-MM-DDThh:mmZ. |
|HDMonitorStatus|String|false|Indicates whether fine-grained monitoring is enabled for the EIP.

 -   **false**: Fine-grained monitoring is disabled for the EIP.
-   **true**: Fine-grained monitoring is enabled for the EIP. |
|HasReservationData|String|false|Indicates whether renewal data is included.

 This parameter returns **true** only when the parameter **IncludeReservationData** is set to **true**, and some orders have not taken effect. |
|ISP|String|BGP|The Internet service provider. |
|InstanceId|String|i-bp15zckdt37cdvf\*\*\*\*|The ID of the instance to which the EIP is bound. |
|InstanceRegionId|String|cn-hangzhou|The region ID of the bound resource. |
|InstanceType|String|EcsInstance|The type of the instance to which the EIP is bound.

 -   **EcsInstance**: an ECS instance in a VPC.
-   **SlbInstance**: an SLB instance in a VPC.
-   **Nat**: a NAT gateway.
-   **HaVip**: a High-Availability Virtual IP Address \(HaVip\).
-   **NetworkInterface**: a secondary ENI. |
|InternetChargeType|String|PayByBandwidth|The metering method of the EIP.

 -   **PayByBandwidth**: Fees are charged based on bandwidth usage.
-   **PayByTraffic**: Fees are charged based on data transfer. |
|IpAddress|String|101.xx.xx.36|The IP address of the EIP. |
|Name|String|test|The name of the EIP. |
|Netmode|String|public|The network type of the EIP. |
|OperationLocks|Array| |The details about the lock. |
|LockReason| | | |
|LockReason|String|financial|The reason why the instance was locked.

 -   **financial**: The EIP is locked due to overdue payments.
-   **security**: The EIP is locked for security reasons. |
|RegionId|String|cn-hangzhou|The ID of the region where the EIP is created. |
|ReservationActiveTime|String|2019-03-11T16:00:00Z|The time when the renewal takes effect. |
|ReservationBandwidth|String|12|The bandwidth after the EIP is renewed. |
|ReservationInternetChargeType|String|PayByBandwidth|The billing method that you choose when you renew the EIP.

 -   **PayByBandwidth**: Fees are charged based on bandwidth usage.
-   **PayByTraffic**: Fees are charged based on data transfer. |
|ReservationOrderType|String|RENEWCHANGE|The type of the renewal order.

 -   **RENEWCHANGE**: upgrade or downgrade.
-   **TEMP\_UPGRADE**: temporary upgrade.
-   **UPGRADE** : upgrade. |
|ResourceGroupId|String|rg-acfmxazcdxs\*\*\*\*|The ID of the resource group. |
|SecondLimited|Boolean|false|Indicates whether level-2 traffic throttling is configured.

 -   **true**: Level-2 traffic throttling is configured.
-   **false**: Level-2 traffic throttling is not configured. |
|SegmentInstanceId|String|eipsg-t4nr90yik5oy38xdyjth8|The ID of the instance to which the contiguous EIP is bound.

 This parameter value is returned only when the EIP belongs to a continuous CIDR block. |
|Status|String|Associating|The status of the EIP.

 -   **Associating**: The EIP is being bound to an instance.
-   **Unassociating**: The EIP is being unbound from an instance.
-   **InUse**: The EIP is allocated and in use.
-   **Available**: The EIP is available for use. |
|TotalCount|Integer|10|The total number of entries. |
|PageNumber|Integer|10|The current page number. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |

## Examples

Sample requests

```
https://vpc.aliyuncs.com/?Action=DescribeEipAddresses
&RegionId=cn-hangzhou
&Common request parameter
```

Sample success responses

`XML` format

```
<DescribeEipAddressesResponse>
  <PageNumber>1</PageNumber>
  <EipAddresses>
        <EipAddress>
              <HDMonitorStatus>OFF</HDMonitorStatus>
              <BandwidthPackageBandwidth>5</BandwidthPackageBandwidth>
              <HasReservationData>false</HasReservationData>
              <InstanceId>ngw-bp1kpih7t3izsxezx****</InstanceId>
              <ISP>BGP</ISP>
              <InternetChargeType>PayByBandwidth</InternetChargeType>
              <EipBandwidth>199</EipBandwidth>
              <BandwidthPackageType>CommonBandwidthPackage</BandwidthPackageType>
              <PrivateIpAddress></PrivateIpAddress>
              <SecondLimited>false</SecondLimited>
              <Bandwidth>5</Bandwidth>
              <ChargeType>PostPaid</ChargeType>
              <AllocationTime>2019-12-26T05:06:56Z</AllocationTime>
              <ResourceGroupId>rg-acfmxazb4ph****</ResourceGroupId>
              <Descritpion>abc</Descritpion>
              <IpAddress>47.xx.xx.184</IpAddress>
              <AllocationId>eip-bp1utfpg4zlhyodba****</AllocationId>
              <Mode>NAT</Mode>
              <InstanceType>Nat</InstanceType>
              <Name>vmeixme</Name>
              <SegmentInstanceId></SegmentInstanceId>
              <Status>InUse</Status>
              <InstanceRegionId>cn-hangzhou</InstanceRegionId>
              <BandwidthPackageId>cbwp-bp1k042riiv5aqkkq****</BandwidthPackageId>
              <RegionId>cn-hangzhou</RegionId>
              <DeletionProtection>false</DeletionProtection>
              <OperationLocks>
        </OperationLocks>
              <ExpiredTime></ExpiredTime>
              <AvailableRegions>
                    <AvailableRegion>cn-hangzhou</AvailableRegion>
              </AvailableRegions>
        </EipAddress>
  </EipAddresses>
  <TotalCount>1</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>27CEB319-8242-46A8-B96B-998BCDF87D97</RequestId>
</DescribeEipAddressesResponse>
```

`JSON` format

```
{
	"PageNumber": 1,
	"EipAddresses": {
		"EipAddress": [
			{
				"HDMonitorStatus": "OFF",
				"BandwidthPackageBandwidth": "5",
				"HasReservationData": false,
				"InstanceId": "ngw-bp1kpih7t3izsxezx****",
				"ISP": "BGP",
				"InternetChargeType": "PayByBandwidth",
				"EipBandwidth": "199",
				"BandwidthPackageType": "CommonBandwidthPackage",
				"PrivateIpAddress": "",
				"SecondLimited": false,
				"Bandwidth": "5",
				"ChargeType": "PostPaid",
				"AllocationTime": "2019-12-26T05:06:56Z",
				"ResourceGroupId": "rg-acfmxazb4ph****",
				"Descritpion": "abc",
				"IpAddress": "47.xx.xx.184",
				"AllocationId": "eip-bp1utfpg4zlhyodba****",
				"Mode": "NAT",
				"InstanceType": "Nat",
				"Name": "vmeixme",
				"SegmentInstanceId": "",
				"Status": "InUse",
				"InstanceRegionId": "cn-hangzhou",
				"BandwidthPackageId": "cbwp-bp1k042riiv5aqkkq****",
				"RegionId": "cn-hangzhou",
				"DeletionProtection": false,
				"OperationLocks": {
					"LockReason": []
				},
				"ExpiredTime": "",
				"AvailableRegions": {
					"AvailableRegion": [
						"cn-hangzhou"
					]
				}
			}
		]
	},
	"TotalCount": 1,
	"PageSize": 10,
	"RequestId": "27CEB319-8242-46A8-B96B-998BCDF87D97"
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The error message returned because the specified region does not exist. Check whether the region is valid.|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|The error message returned because the EIP is locked for an unknown reason.|
|400|InvalidIAssociatedInstanceType.ValueNotSupported|The specified value of AssociatedInstanceType is not supported.|The error message returned because the AssociatedInstanceType value is invalid. Check whether the value is supported.|
|400|InvalidChargeType.ValueNotSupported|The specified ChargeType is not supported.|The error message returned because the specified billing method is not supported. Select another billing method.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

