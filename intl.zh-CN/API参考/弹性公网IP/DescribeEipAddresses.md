# DescribeEipAddresses

调用DescribeEipAddresses接口查询指定地域已创建的EIP。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeEipAddresses&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEipAddresses|要执行的操作，取值：**DescribeEipAddresses**。 |
|RegionId|String|是|cn-hangzhou|EIP所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|IncludeReservationData|Boolean|否|true|是否包含未生效的订购数据，取值：

 -   **false**（默认）：不包含未生效的订购数据。
-   **true**：包含未生效的订购数据。 |
|Status|String|否|Available|EIP的状态，取值：

 -   **Associating**：绑定中。
-   **Unassociating**：解绑中。
-   **InUse**：已分配。
-   **Available**：可用。 |
|EipAddress|String|否|116.xx.xx.28|要查询的EIP的IP地址。

 最多支持输入50个EIP的IP地址，IP地址之间用逗号（,）分隔。

 **说明：** 如果同时传入**EipAddress**和**AllocationId**参数，**EipAddress**可输入50个EIP的IP地址，**AllocationId**也可同时输入50个EIP实例ID。 |
|AllocationId|String|否|eip-2zeerraiwb7ujxscd\*\*\*\*|要查询的EIP实例的ID。

 最多支持输入50个EIP实例ID，实例ID之间用逗号（,）分隔。

 **说明：** 如果同时传入**EipAddress**和**AllocationId**参数，**AllocationId**可输入50个EIP实例ID，**EipAddress**也可同时输入50个EIP的IP地址。 |
|SegmentInstanceId|String|否|eipsg-t4nr90yik5oy38xdy\*\*\*\*|连续EIP的实例ID。 |
|ResourceGroupId|String|否|rg-acfmxazb4pcdvf\*\*\*\*|EIP所属的资源组的ID。 |
|PageNumber|Integer|否|10|列表的页码，默认值为**1**。 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**100**，默认值为**10**。 |
|ISP|String|否|BGP|线路类型，取值：

 -   **BGP**：BGP（多线）线路。

BGP（多线）线路在全球有多达89条优质BGP线路，在中国内地的每个地域均提供电信、联通、移动、铁通、网通、教育网、广电、鹏博士、方正宽带等多条线路的直连覆盖。

-   **BGP\_PRO**：BGP（多线）精品线路。

BGP（多线）精品线路是一种优化海外回国流量的公网线路，可以提高国际业务访问质量。相比普通BGP（多线）线路， BGP（多线）精品线路通过底层网络直连回国，无需绕行国际运营商出口，时延更低。


 目前，全部地域都支持BGP（多线）线路EIP，仅中国（香港）地域支持BGP（多线）精品线路EIP。

 **说明：** 如果是开通了单线带宽白名单的用户，ISP字段可以设置为**ChinaTelecom**（中国电信）、**ChinaUnicom**（中国联通）和**ChinaMobile**（中国移动）；如果是杭州金融云用户，该字段必填，取值：**BGP\_FinanceCloud**。 |
|Filter.1.Key|String|否|CreationStartTime|查询资源时的筛选键，必须取值为**CreationStartTime**（资源创建的开始时间）。 |
|Filter.2.Key|String|否|CreationEndTime|查询资源时的筛选键，必须取值为**CreationEndTime**（资源创建的结束时间）。 |
|Filter.1.Value|String|否|2018-01-22T09:12Z|查询资源时的筛选值。使用UTC时间，格式为：YYYY-MM-DDThh:mmZ。 |
|Filter.2.Value|String|否|2018-01-22T09:15Z|查询资源时的筛选值。使用UTC时间，格式为：YYYY-MM-DDThh:mmZ。 |
|LockReason|String|否|financial|锁定类型，取值：

 -   **financial**：因欠费被锁定。
-   **security**：因安全原因被锁定。 |
|AssociatedInstanceType|String|否|EcsInstance|要绑定的云产品实例的类型，取值：

 -   **EcsInstance**（默认值）：VPC类型的ECS实例。
-   **SlbInstance**：VPC类型的SLB实例。
-   **Nat**：NAT网关。
-   **HaVip**：高可用虚拟IP。
-   **NetworkInterface**：辅助弹性网卡。

每个ECS实例、负载均衡实例和HAVIP同时只能绑定一个EIP，NAT网关可以绑定多个EIP。辅助弹性网卡可以绑定EIP的个数受EIP绑定模式影响，详情请参见[弹性公网IP概述](~~88991~~)。 |
|AssociatedInstanceId|String|否|i-2zebb08phyccdvf\*\*\*\*|云产品的实例ID。 |
|ChargeType|String|否|PostPaid|弹性公网IP的计费方式，取值：

 **PostPaid**：按量计费。 |
|DryRun|Boolean|否|false|是否只预检此次请求，取值：

 -   **true**：发送检查请求，不会查询资源状况。检查项包括AccessKey是否有效、RAM用户的授权情况和是否填写了必需参数。如果检查不通过，则返回对应错误。如果检查通过，会返回错误码DryRunOperation。
-   **false**（默认值）：发送正常请求，通过检查后返回2XXHTTP状态码并直接查询资源状况。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|EipAddresses|Array| |EIP的详细信息。 |
|EipAddress| | | |
|AllocationId|String|eip-2zeerraiwb7ujcdvf\*\*\*\*|EIP的ID。 |
|AllocationTime|String|2019-04-23T01:37:38Z|EIP的创建时间。 |
|AvailableRegions|List|cn-hangzhou|EIP的地域ID。 |
|Bandwidth|String|5|EIP的带宽峰值，单位为Mbps。 |
|BandwidthPackageBandwidth|String|50|EIP加入的共享带宽的带宽值。 |
|BandwidthPackageId|String|cbwp-bp1ego3i4j07ccdvf\*\*\*\*|加入的共享带宽ID。 |
|BandwidthPackageType|String|CommonBandwidthPackage|带宽的类型，仅支持返回**CommonBandwidthPackage**（共享带宽）。 |
|ChargeType|String|PostPaid|弹性公网IP的计费模式。

 -   **PrePaid**：包年包月。
-   **PostPaid**：按量计费。 |
|DeletionProtection|Boolean|true|是否开启了删除保护功能。

 -   **true**：已开启。
-   **false**：未开启。 |
|Descritpion|String|abc|弹性公网IP的描述信息。 |
|EipBandwidth|String|101|EIP加入共享带宽之前或退出共享带宽之后的带宽。 |
|ExpiredTime|String|2019-04-29T02:00Z|到期时间，按照ISO8601标准表示，并需要使用UTC时间。格式为：YYYY-MM-DDThh:mmZ。 |
|HDMonitorStatus|String|false|EIP是否开启了秒级监控。

 -   **false**：未开启。
-   **true**：已开启。 |
|HasReservationData|String|false|是否有续费数据。

 只有在入参**IncludeReservationData**为**true**，且有未生效订购数据时才会为**true**。 |
|ISP|String|BGP|服务提供商。 |
|InstanceId|String|i-bp15zckdt37cdvf\*\*\*\*|当前绑定的实例的ID。 |
|InstanceRegionId|String|cn-hangzhou|当前绑定的资源的地域ID。 |
|InstanceType|String|EcsInstance|当前绑定的实例类型。

 -   **EcsInstance**：VPC类型的ECS实例。
-   **SlbInstance**：VPC类型的SLB实例。
-   **Nat**：NAT网关。
-   **HaVip**：高可用虚拟IP。
-   **NetworkInterface**：辅助弹性网卡。 |
|InternetChargeType|String|PayByBandwidth|EIP的计费方式。

 -   **PayByBandwidth**：按带宽计费。
-   **PayByTraffic**：按流量计费。 |
|IpAddress|String|101.xx.xx.36|弹性公网IP的IP地址。 |
|Name|String|test|弹性公网IP的名称。 |
|Netmode|String|public|网络类型。 |
|OperationLocks|Array| |锁定详情。 |
|LockReason| | | |
|LockReason|String|financial|锁定类型。

 -   **financial**：因欠费被锁定。
-   **security**：因安全原因被锁定。 |
|RegionId|String|cn-hangzhou|EIP所在的地域。 |
|ReservationActiveTime|String|2019-03-11T16:00:00Z|续费生效时间。 |
|ReservationBandwidth|String|12|续费带宽。 |
|ReservationInternetChargeType|String|PayByBandwidth|续费付费类型。

 -   **PayByBandwidth**：按带宽计费。
-   **PayByTraffic**：按流量计费。 |
|ReservationOrderType|String|RENEWCHANGE|续费订单类型。

 -   **RENEWCHANGE**：续费变配。
-   **TEMP\_UPGRADE**：短时升配。
-   **UPGRADE** ：升级。 |
|ResourceGroupId|String|rg-acfmxazcdxs\*\*\*\*|资源组ID。 |
|SecondLimited|Boolean|false|是否配置了二级限速。

 -   **true**：已配置。
-   **false**：未配置。 |
|SegmentInstanceId|String|eipsg-t4nr90yik5oy38xdyjth8|连续EIP的实例ID。

 仅EIP属于连续EIP时才会返回该参数值。 |
|Status|String|Associating|EIP的状态。

 -   **Associating**：绑定中。
-   **Unassociating**：解绑中。
-   **InUse**：已分配。
-   **Available**：可用。 |
|TotalCount|Integer|10|列表条目数。 |
|PageNumber|Integer|10|当前页码。 |
|PageSize|Integer|10|每页包含的条目数。 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。 |

## 示例

请求示例

```
https://vpc.aliyuncs.com/?Action=DescribeEipAddresses
&RegionId=cn-hangzhou
&公共请求参数
```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|锁定原因未找到。|
|400|InvalidIAssociatedInstanceType.ValueNotSupported|The specified value of AssociatedInstanceType is not supported.|AssociatedInstanceType的值不合法，请您检查该参数是正确。|
|400|InvalidChargeType.ValueNotSupported|The specified ChargeType is not supported.|该计费方式不支持，请您重新选择计费方式。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

