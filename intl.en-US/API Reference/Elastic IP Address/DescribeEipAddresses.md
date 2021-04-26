# DescribeEipAddresses

Queries elastic IP addresses \(EIPs\) created in a specific region.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=DescribeEipAddresses&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEipAddresses|The operation that you want to perform. Set the value to **DescribeEipAddresses**. |
|RegionId|String|Yes|cn-hangzhou|The region ID of the EIPs. You can call the [DescribeRegions](~~36063~~)operation to query the most recent region list. |
|IncludeReservationData|Boolean|No|true|Specify whether to return data of orders that have not taken effect. Valid values:

 -   **false**: Data of orders that have not taken effect is not returned. This is the default value.
-   **true**: Data of orders that have not taken effect is returned. |
|Status|String|No|Available|The state of the EIP. Valid values:

 -   **Associating**: The EIP is being associated.
-   **Unassociating**: The EIP is being disassociated.
-   **InUse**: The EIP is allocated.
-   **Available**: The EIP is available. |
|EipAddress|String|No|116.XX.XX.28|The IP address of the EIP that you want to query.

 You can enter the IP addresses of up to 50 EIPs. Separate multiple IP addresses with commas \(,\).

 **Note:** If both the **EipAddress** and **AllocationId** parameters are set, you can enter the IP addresses of 50 EIPs in **EipAddress**, and enter the IDs of the 50 EIPs in **AllocationId**. |
|AllocationId|String|No|eip-2zeerraiwb7ujxscd\*\*\*\*|The ID of the EIP that you want to query.

 You can enter IDs of up to 50 EIPs. Separate multiple IDs with commas \(,\).

 **Note:** If both the **EipAddress** and **AllocationId** parameters are set, you can enter the IDs of up to 50 EIP instances in **AllocationId**, and enter the IP addresses of the 50 EIPs in **EipAddress**. |
|SegmentInstanceId|String|No|eipsg-t4nr90yik5oy38xdy\*\*\*\*|The IDs of contiguous EIPs. |
|ResourceGroupId|String|No|rg-acfmxazb4pcdvf\*\*\*\*|The ID of the resource group to which the EIPs belongs. |
|PageNumber|Integer|No|10|The number of the page to return. Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page. Maximum value: **100**. Default value: **10**. |
|ISP|String|No|BGP|The line type. Valid values:

 -   **BGP**: BGP \(Multi-ISP\) lines.

Up to 89 high-quality BGP lines are available worldwide. Direct connections with multiple Internet service providers \(ISPs\), including Telecom, Unicom, Mobile, Railcom, Netcom, CERNET, China Broadcast Network, Dr. Peng, and Founder, can be established in all regions in mainland China.

-   **BGP\_PRO**: BGP \(Multi-ISP\) Pro lines.

BGP \(Multi-ISP\) Pro lines optimize data transmission to China and improve connection quality for international services. Compared with BGP \(Multi-ISP\), when BGP \(Multi-ISP\) Pro provides services to clients in China \(excluding data centers\), cross-border connections are established without using international ISP services. This reduces network latency.


 BGP \(Multi-ISP\) lines are supported in all regions. BGP \(Multi-ISP\) Pro lines are supported only in the China \(Hong Kong\) region.

 **Note:** If your Alibaba Cloud account is included in the BGP \(single line\) whitelist, you can set the ISP field to **ChinaTelecom**, **ChinaUnicom**, or **ChinaMobile**. If your workloads are deployed in China East 1 Finance. Set the value to **BGP\_FinanceCloud**. |
|Filter.1.Key|String|No|CreationStartTime|The filter key used to query resources. Set the value to **CreationStartTime** \(the start time when resources are created\). |
|Filter.2.Key|String|No|CreationEndTime|The filter key used to query resources. Set the value to **CreationEndTime** \(the end time when resources are created\). |
|Filter.1.Value|String|No|2018-01-22T09:12Z|The filter value used to query resources. Specify the time in the ISO 8601 standard in YYYY-MM-DDThh:mmZ format. The time must be in UTC. |
|Filter.2.Value|String|No|2018-01-22T09:15Z|The filter value used to query resources. Specify the time in the ISO 8601 standard in YYYY-MM-DDThh:mmZ format. The time must be in UTC. |
|LockReason|String|No|financial|The reason why the EIP is locked. Valid values:

 -   **financial**: The EIP is locked due to overdue payments.
-   **security**: The EIP is locked for security reasons. |
|AssociatedInstanceType|String|No|EcsInstance|The type of the cloud resource with which you want to associate the EIP. Valid values:

 -   **EcsInstance**: an Elastic Compute Service \(ECS\) instance deployed in a virtual private cloud \(VPC\). This is the default value.
-   **SlbInstance**: a Server Load Balancer \(SLB\) instance in a VPC
-   **Nat**: a NAT gateway
-   **HaVip**: a high-availability virtual IP address \(HAVIP\)
-   **NetworkInterface**: a secondary elastic network interface \(ENI\)

You can associate only one EIP with each ECS instance, SLB instance, or HAVIP. You can associate multiple EIPs with each NAT gateway. The number of EIPs that you can associate with a secondary ENI depends on the EIP mode. For more information, see [EIP overview](~~88991~~). |
|AssociatedInstanceId|String|No|i-2zebb08phyccdvf\*\*\*\*|The ID of the instance. |
|ChargeType|String|No|PostPaid|The billing method of the EIP. Valid values:

 **PostPaid**: pay-as-you-go |
|DryRun|Boolean|No|false|Specify whether to precheck only this request. Valid values:

 -   **true**: The request is prechecked but resources are not queried. The system checks whether your AccessKey pair is valid, whether the RAM user is authorized, and whether required parameters are set. If the request fails to pass the precheck, the corresponding error is returned. If the request passes the precheck, the DryRunOperation error code is returned.
-   **false**: The request is checked. This is the default value. If the request passes the precheck, a 2XX HTTP status code is returned and the resource is queried. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipAddresses|Array of EipAddress| |The details about the EIP. |
|EipAddress| | | |
|AllocationId|String|eip-2zeerraiwb7ujcdvf\*\*\*\*|The ID of the EIP. |
|AllocationTime|String|2019-04-23T01:37:38Z|The time when the EIP was created. |
|AvailableRegions|List|cn-hangzhou|The ID of the region to which the EIP belongs. |
|Bandwidth|String|5|The maximum bandwidth of the EIP. Unit: Mbit/s. |
|BandwidthPackageBandwidth|String|50|The bandwidth value of the EIP bandwidth plan with which the EIP is associated. |
|BandwidthPackageId|String|cbwp-bp1ego3i4j07ccdvf\*\*\*\*|The ID of the EIP bandwidth plan. |
|BandwidthPackageType|String|CommonBandwidthPackage|The type of the bandwidth. Only **CommonBandwidthPackage** \(an EIP bandwidth plan\) is returned. |
|BusinessStatus|String|Normal|The state of the EIP. Valid values:

 -   **Normal**: The EIP is working as expected.
-   **FinancialLocked**: The EIP is locked. |
|ChargeType|String|PostPaid|The billing method of the EIP. Valid values:

 -   **PrePaid**: subscription
-   **PostPaid**: pay-as-you-go |
|DeletionProtection|Boolean|true|Indicates whether deletion protection is enabled. Valid values:

 -   **true**: enabled
-   **false**: disabled |
|Descritpion|String|abc|The description of the EIP. |
|EipBandwidth|String|101|The bandwidth value of the EIP when it is not associated with an EIP bandwidth plan. |
|ExpiredTime|String|2019-04-29T02:00Z|The expiration date. The time follows the ISO 8601 standard and is displayed in UTC. Format: YYYY-MM-DDThh:mmZ. |
|HDMonitorStatus|String|false|Indicates whether fine-grained monitoring is enabled for the EIP. Valid values:

 -   **false**: disabled
-   **true**: enabled |
|HasReservationData|String|false|Indicates whether renewal data is included.

 This parameter returns **true** only when the parameter **IncludeReservationData** is set to **true**, and some orders have not taken effect. |
|ISP|String|BGP|The Internet service provider \(ISP\). |
|InstanceId|String|i-bp15zckdt37cdvf\*\*\*\*|The ID of the instance with which the EIP is associated. |
|InstanceRegionId|String|cn-hangzhou|The region ID of the associated resource. |
|InstanceType|String|EcsInstance|The type of the instance with which the EIP is associated. Valid values:

 -   **EcsInstance**: an ECS instance in a VPC
-   **SlbInstance**: an SLB instance in a VPC
-   **Nat**: a NAT gateway
-   **HaVip**: an HAVIP
-   **NetworkInterface**: a secondary ENI |
|InternetChargeType|String|PayByBandwidth|The metering method of the EIP. Valid values:

 -   **PayByBandwidth**: pay-by-bandwidth
-   **PayByTraffic**: pay-by-data-transfer |
|IpAddress|String|116.XX.XX.28|The IP address of the EIP. |
|Name|String|test|The name of the EIP. |
|Netmode|String|public|The network type. |
|OperationLocks|Array of LockReason| |The details about the locked EIP. |
|LockReason| | | |
|LockReason|String|financial|The reason why the EIP is locked. Valid values:

 -   **financial**: The EIP is locked due to overdue payments.
-   **security**: The EIP is locked for security reasons. |
|RegionId|String|cn-hangzhou|The ID of the region to which the EIP belongs. |
|ReservationActiveTime|String|2019-03-11T16:00:00Z|The time when the renewal takes effect. |
|ReservationBandwidth|String|12|The bandwidth after the renewal takes effect. |
|ReservationInternetChargeType|String|PayByBandwidth|The metering method of the renewal. Valid values:

 -   **PayByBandwidth**: pay-by-bandwidth
-   **PayByTraffic**: pay-by-data-transfer |
|ReservationOrderType|String|RENEWCHANGE|The type of the renewal order. Valid values:

 -   **RENEWCHANGE**: upgrade or downgrade
-   **TEMP\_UPGRADE**: temporary upgrade
-   **UPGRADE**: upgrade |
|ResourceGroupId|String|rg-acfmxazcdxs\*\*\*\*|The ID of the resource group. |
|SecondLimited|Boolean|false|Indicates whether level-2 throttling is configured.

 -   **true**: yes
-   **false**: no |
|SegmentInstanceId|String|eipsg-t4nr90yik5oy38xd\*\*\*\*|The IDs of the contiguous EIPs.

 This value is returned only when contiguous EIPs are specified. |
|ServiceManaged|Integer|0|Indicates whether the resource is created by the service account. Valid values:

 -   **0**: no
-   **1**: yes |
|Status|String|Associating|The status of the EIP. Valid values:

 -   **Associating**: The EIP is being associated.
-   **Unassociating**: The EIP is being disassociated.
-   **InUse**: The EIP is allocated.
-   **Available**:The EIP is available. |
|TotalCount|Integer|10|The number of entries returned. |
|PageNumber|Integer|10|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|The ID of the request. |

## Examples

Sample requests

```
  
 
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeEipAddressesResponse>
  <TotalCount>10</TotalCount>
  <PageSize>10</PageSize>
  <RequestId>4EC47282-1B74-4534-BD0E-403F3EE64CAF</RequestId>
  <EipAddresses>
        <EipAddress>
              <HDMonitorStatus>false</HDMonitorStatus>
              <ServiceManaged>0</ServiceManaged>
              <ResourceGroupId>rg-acfmxazcdxs****</ResourceGroupId>
              <AllocationId>eip-2zeerraiwb7ujcdvf****</AllocationId>
              <SecondLimited>false</SecondLimited>
              <BusinessStatus>Normal</BusinessStatus>
              <Name>test</Name>
              <SegmentInstanceId>eipsg-t4nr90yik5oy38xd****</SegmentInstanceId>
              <ReservationOrderType>RENEWCHANGE</ReservationOrderType>
              <InstanceRegionId> cn-hangzhou</InstanceRegionId>
              <ExpiredTime>2019-04-29T02:00Z</ExpiredTime>
              <Bandwidth>5</Bandwidth>
              <BandwidthPackageId>cbwp-bp1ego3i4j07ccdvf****</BandwidthPackageId>
              <ReservationActiveTime>2019-03-11T16:00:00Z</ReservationActiveTime>
              <InstanceType>EcsInstance</InstanceType>
              <ReservationBandwidth>12</ReservationBandwidth>
              <Status>Associating</Status>
              <InstanceId>i-bp15zckdt37cdvf****</InstanceId>
              <ISP>BGP</ISP>
              <HasReservationData>false</HasReservationData>
              <DeletionProtection>true</DeletionProtection>
              <BandwidthPackageType>CommonBandwidthPackage</BandwidthPackageType>
              <BandwidthPackageBandwidth>50</BandwidthPackageBandwidth>
              <ReservationInternetChargeType>PayByBandwidth</ReservationInternetChargeType>
              <InternetChargeType>PayByBandwidth</InternetChargeType>
              <AllocationTime>2019-04-23T01:37:38Z</AllocationTime>
              <Descritpion>abc</Descritpion>
              <EipBandwidth>101</EipBandwidth>
              <Netmode>public</Netmode>
              <ChargeType>PostPaid</ChargeType>
              <IpAddress>116.XX.XX.28</IpAddress>
              <RegionId>cn-hangzhou</RegionId>
              <OperationLocks>
                    <LockReason>
                          <LockReason>financial</LockReason>
                    </LockReason>
              </OperationLocks>
              <AvailableRegions>
                    <AvailableRegion>cn-hangzhou</AvailableRegion>
              </AvailableRegions>
        </EipAddress>
  </EipAddresses>
  <PageNumber>10</PageNumber>
</DescribeEipAddressesResponse>
```

`JSON` format

```
{
    "TotalCount": 10,
    "PageSize": 10,
    "RequestId": "4EC47282-1B74-4534-BD0E-403F3EE64CAF",
    "EipAddresses": {
        "EipAddress": {
            "HDMonitorStatus": false,
            "ServiceManaged": 0,
            "ResourceGroupId": "rg-acfmxazcdxs****",
            "AllocationId": "eip-2zeerraiwb7ujcdvf****",
            "SecondLimited": false,
            "BusinessStatus": "Normal",
            "Name": "test",
            "SegmentInstanceId": "eipsg-t4nr90yik5oy38xd****",
            "ReservationOrderType": "RENEWCHANGE",
            "InstanceRegionId": "cn-hangzhou",
            "ExpiredTime": "2019-04-29T02:00Z",
            "Bandwidth": 5,
            "BandwidthPackageId": "cbwp-bp1ego3i4j07ccdvf****",
            "ReservationActiveTime": "2019-03-11T16:00:00Z",
            "InstanceType": "EcsInstance",
            "ReservationBandwidth": 12,
            "Status": "Associating",
            "InstanceId": "i-bp15zckdt37cdvf****",
            "ISP": "BGP",
            "HasReservationData": false,
            "DeletionProtection": true,
            "BandwidthPackageType": "CommonBandwidthPackage",
            "BandwidthPackageBandwidth": 50,
            "ReservationInternetChargeType": "PayByBandwidth",
            "InternetChargeType": "PayByBandwidth",
            "AllocationTime": "2019-04-23T01:37:38Z",
            "Descritpion": "abc",
            "EipBandwidth": 101,
            "Netmode": "public",
            "ChargeType": "PostPaid",
            "IpAddress": "116.XX.XX.28",
            "RegionId": "cn-hangzhou",
            "OperationLocks": {
                "LockReason": {
                    "LockReason": "financial"
                }
            },
            "AvailableRegions": {
                "AvailableRegion": "cn-hangzhou"
            }
        }
    },
    "PageNumber": 10
}
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The error message returned because the specified region does not exist. Check whether the specified region ID is valid.|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|The error message returned because the reason why the EIP is locked is unknown.|
|400|InvalidIAssociatedInstanceType.ValueNotSupported|The specified value of AssociatedInstanceType is not supported.|The error message returned because AssociatedInstanceType is set to an invalid value. Check whether the value is valid.|
|400|InvalidChargeType.ValueNotSupported|The specified ChargeType is not supported.|The error message returned because the specified billing method is not supported. Select a supported billing method.|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|The error message returned because the specified resource group ID does not exist.|
|400|OperationUnsupported.ResourceGroupId|ResourceGroup is not supported in this region.|The error message returned because the resource group feature is not enabled.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

