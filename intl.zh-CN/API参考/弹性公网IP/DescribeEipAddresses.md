# DescribeEipAddresses {#doc_api_Vpc_DescribeEipAddresses .reference}

调用DescribeEipAddresses接口查询指定地域已创建的EIP。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeEipAddresses&type=RPC&version=2016-04-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEipAddresses|要执行的操作，取值： **DescribeEipAddresses**。

 |
|RegionId|String|是|cn-hangzhou|EIP所在的地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|AllocationId|String|否|eip-2zeerraiwb7ujxxxxxxxx|EIP的ID。

 |
|AssociatedInstanceId|String|否|i-2zebb08phycxxxxxxxx|云产品的实例ID。

 |
|AssociatedInstanceType|String|否|EcsInstance|要绑定的云产品实例的类型，取值：

 -   **EcsInstance**（默认值）：VPC类型的ECS实例。
-   **SlbInstance**：VPC类型的SLB实例。
-   **Nat**：NAT网关。
-   **HaVip**：高可用虚拟IP。

每个ECS实例、负载均衡实例和HAVIP同时只能绑定一个EIP，NAT网关可以绑定多个EIP。


 |
|ChargeType|String|否|PostPaid| 弹性公网IP的计费方式，取值：

 **PostPaid**：后付费。

 |
|EipAddress|String|否|116.xx.xx.28|EIP的IP地址。指定后可查看指定IP地址的EIP的信息。

 |
|Filter.1.Key|String|否|Filter.1.Name|要使用的过滤条件。

 |
|Filter.1.Value|String|否|value1|对应过滤条件的取值。

 |
|Filter.2.Key|String|否|Filter.2.Description|要使用的过滤条件。

 |
|Filter.2.Value|String|否|value2|对应过滤条件的取值。

 |
|ISP|String|否|BGP|服务提供商，大部分是BGP。

 |
|IncludeReservationData|Boolean|否|true|是否包含未生效的订购数据，默认是否。

 |
|LockReason|String|否|financial|锁定类型，取值：

 -   **financial**：因欠费被锁定。
-   **security**：因安全原因被锁定。

 |
|PageNumber|Integer|否|10|列表的页码，默认值为**1**。

 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**50**，默认值为**10**。

 |
|ResourceGroupId|String|否|rg-acfmxazb4pxxxxxxxx|资源组ID。

 |
|Status|String|否|Available|EIP的状态，取值：

 -   **Associating**：绑定中。
-   **Unassociating**：解绑中。
-   **InUse**：已分配。
-   **Available**：可用。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|EipAddresses| | |EIP的详细信息。

 |
|AllocationId|String|eip-2zeerraiwb7ujxxxxxxxx|EIP的ID。

 |
|AllocationTime|String|2019-04-23T01:37:38Z|EIP的创建时间。

 |
|AvailableRegions| |cn-hangzhou|地域ID。

 |
|Bandwidth|String|5|EIP的带宽峰值，单位为Mbps。

 |
|BandwidthPackageId|String|cbwp-bp1ego3i4j07cxxxxxxxx|加入的共享带宽ID。

 |
|BandwidthPackageType|String|CommonBandwidthPackage|共享带宽类型。

 |
|ChargeType|String|PostPaid|弹性公网IP的计费模式。

 |
|Descritpion|String|概述|弹性公网IP的描述信息。

 |
|EipBandwidth|String|101|EIP加入共享带宽之前或退出共享带宽之后的带宽。

 |
|ExpiredTime|String|2019-04-29T02:37:38Z|到期时间，按照ISO8601标准表示，并需要使用UTC时间。格式为：YYYY-MM-DDThh:mmZ。

 |
|HDMonitorStatus|String|false|EIP是否开启了秒级监控。

 |
|HasReservationData|String|wweayhddrhht|只有在入参**IncludeReservationData**为**true**，且有未生效订购数据时才会为**true**。

 |
|ISP|String|BGP|服务提供商，大部分是BGP。

 |
|InstanceId|String|vpc-bp15zckdt37xxxxxxxx|当前绑定的实例的ID。

 |
|InstanceRegionId|String|cn-hangzhou|当前绑定的资源的地域ID。

 |
|InstanceType|String|EcsInstance|当前绑定的实例类型。

 |
|InternetChargeType|String|PayByBandwidth|EIP的计费方式。

 |
|IpAddress|String|101.xx.xx.36|弹性公网IP的IP地址。

 |
|Name|String|弹性公网IP|弹性公网IP的名称。

 |
|OperationLocks| | |锁定详情。

 |
|LockReason|String|financial|锁定类型，取值：

 -   **financial**：因欠费被锁定。
-   **security**：因安全原因被锁定。

 |
|RegionId|String|cn-hangzhou|EIP所在的地域。

 |
|ReservationActiveTime|String|2019-03-11T16:00:00Z|续费生效时间。

 |
|ReservationBandwidth|String|12|续费带宽。

 |
|ReservationInternetChargeType|String|PayByBandwidth|续费付费类型。

 |
|ReservationOrderType|String|RENEWCHANGE|续费订单类型，取值：

 -   **RENEWCHANGE**：续费变配。
-   **TEMP\_UPGRADE**：短时升配。
-   **UPGRADE** ：升级。

 |
|ResourceGroupId|String|rg-acfmxazxxxxxxxx|资源组ID。

 |
|Status|String|Associating|EIP的状态，取值：

 -   **Associating**：绑定中。
-   **Unassociating**：解绑中。
-   **InUse**：已分配。
-   **Available**：可用。

 |
|TotalCount|Integer|10|列表条目数。

 |
|PageNumber|Integer|10|当前页码。

 |
|PageSize|Integer|10|每页包含的条目数。

 |
|RequestId|String|4EC47282-1B74-4534-BD0E-403F3EE64CAF|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=DescribeEipAddresses
&RegionId=cn-hangzhou
&公共请求参数

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|
|404|InvalidFilterKey.NotFound| |该过滤器的Key值不合法|
|404|InvalidFilterValue| |该过滤器的Value值不合法|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|锁定原因未找到。|
|400|InvalidIAssociatedInstanceType.ValueNotSupported|The specified value of AssociatedInstanceType is not supported.|AssociatedInstanceType的值不合法，请您检查该参数是正确。|
|400|InvalidChargeType.ValueNotSupported|The specified ChargeType is not supported.|该计费方式不支持，请您重新选择计费方式。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

