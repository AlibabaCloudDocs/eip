# DescribeEipAddresses

调用DescribeEipAddresses接口查询指定地域已创建的EIP。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeEipAddresses&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEipAddresses|要执行的操作，取值：**DescribeEipAddresses**。 |
|RegionId|String|是|cn-hangzhou|EIP所在的地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|IncludeReservationData|Boolean|否|true|是否包含未生效的订购数据，取值：

 -   **false**（默认）：不包含未生效的订购数据。
-   **true**：包含未生效的订购数据。 |
|Status|String|否|Available|EIP的状态，取值：

 -   **Associating**：绑定中。
-   **Unassociating**：解绑中。
-   **InUse**：已分配。
-   **Available**：可用。 |
|EipAddress|String|否|116.XX.XX.28|要查询的EIP的IP地址。

 最多支持输入50个EIP的IP地址，IP地址之间用半角逗号（,）分隔。

 **说明：** 如果同时传入**EipAddress**和**AllocationId**参数，**EipAddress**可输入50个EIP的IP地址，**AllocationId**也可同时输入50个EIP的实例ID。 |
|AllocationId|String|否|eip-2zeerraiwb7ujxscd\*\*\*\*|要查询的EIP实例的ID。

 最多支持输入50个EIP实例ID，实例ID之间用半角逗号（,）分隔。

 **说明：** 如果同时传入**EipAddress**和**AllocationId**参数，**AllocationId**可输入50个EIP的实例ID，**EipAddress**也可同时输入50个EIP的IP地址。 |
|SegmentInstanceId|String|否|eipsg-t4nr90yik5oy38xdy\*\*\*\*|连续EIP的实例ID。 |
|ResourceGroupId|String|否|rg-acfmxazb4pcdvf\*\*\*\*|EIP所属的资源组的ID。 |
|PageNumber|Integer|否|10|列表的页码，默认值为**1**。 |
|PageSize|Integer|否|10|分页查询时每页的行数，最大值为**100**，默认值为**10**。 |
|ISP|String|否|BGP|线路类型，取值：

 -   **BGP**：BGP（多线）线路。

BGP（多线）线路在全球有多达89条优质BGP线路，在中国内地的每个地域均提供电信、联通、移动、铁通、网通、教育网、广电、鹏博士、方正宽带等多条线路的直连覆盖。

-   **BGP\_PRO**：BGP（多线）精品线路。

BGP（多线）精品线路是一种优化海外回中国内地流量的公网线路，可以提高国际业务访问质量。相比普通BGP（多线）线路， BGP（多线）精品线路在为中国内地终端客户（不包括中国内地数据中心）提供服务时，通过底层网络直连回中国内地，无需绕行国际运营商出口，时延更低。


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

每个ECS实例、SLB实例和高可用虚拟IP同时只能绑定一个EIP，NAT网关可以绑定多个EIP。辅助弹性网卡可以绑定EIP的个数受EIP绑定模式影响，更多信息，请参见[弹性公网IP概述](~~88991~~)。 |
|AssociatedInstanceId|String|否|i-2zebb08phyccdvf\*\*\*\*|云产品的实例ID。 |
|ChargeType|String|否|PostPaid|弹性公网IP的计费方式，取值：

 **PostPaid**：按量计费。

 **PrePaid**：包年包月。 |
|DryRun|Boolean|否|false|是否只预检此次请求，取值：

 -   **true**：发送检查请求，不会查询资源状况。检查项包括AccessKey是否有效、RAM用户的授权情况和是否填写了必需参数。如果检查不通过，则返回对应错误。如果检查通过，会返回错误码DryRunOperation。
-   **false**（默认值）：发送正常请求，通过检查后返回2xx HTTP状态码并直接查询资源状况。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|EipAddresses|Array of EipAddress| |EIP的详细信息。 |
|EipAddress| | | |
|AllocationId|String|eip-2zeerraiwb7ujcdvf\*\*\*\*|EIP的实例ID。 |
|AllocationTime|String|2019-04-23T01:37:38Z|EIP的创建时间。 |
|AvailableRegions|List|cn-hangzhou|EIP的地域ID。 |
|Bandwidth|String|5|EIP的带宽峰值，单位为Mbps。 |
|BandwidthPackageBandwidth|String|50|EIP加入的共享带宽的带宽值。 |
|BandwidthPackageId|String|cbwp-bp1ego3i4j07ccdvf\*\*\*\*|加入的共享带宽ID。 |
|BandwidthPackageType|String|CommonBandwidthPackage|带宽的类型，仅支持返回**CommonBandwidthPackage**（共享带宽）。 |
|BusinessStatus|String|Normal|EIP实例的业务状态，取值：

 -   **Normal**：正常。
-   **FinancialLocked**：被锁定。 |
|ChargeType|String|PostPaid|EIP的计费模式。

 -   **PrePaid**：包年包月。
-   **PostPaid**：按量计费。 |
|DeletionProtection|Boolean|true|是否开启了删除保护功能。

 -   **true**：已开启。
-   **false**：未开启。 |
|Descritpion|String|abc|EIP的描述信息。 |
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
|IpAddress|String|116.XX.XX.28|EIP的IP地址。 |
|Name|String|test|EIP的名称。 |
|Netmode|String|public|网络类型。 |
|OperationLocks|Array of LockReason| |锁定详情。 |
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
|SegmentInstanceId|String|eipsg-t4nr90yik5oy38xd\*\*\*\*|连续EIP的实例ID。

 仅EIP属于连续EIP时才会返回该参数值。 |
|ServiceManaged|Integer|0|是否为服务账号创建的资源。取值：

 -   **0**：非服务账号创建。
-   **1**：服务账号创建。 |
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

`XML`格式

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

`JSON`格式

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

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|
|404|InvalidLockReason.NotFound|The specified LockReason is not found|锁定原因未找到。|
|400|InvalidIAssociatedInstanceType.ValueNotSupported|The specified value of AssociatedInstanceType is not supported.|AssociatedInstanceType的值不合法，请您检查该参数是正确。|
|400|InvalidChargeType.ValueNotSupported|The specified ChargeType is not supported.|该计费方式不支持，请您重新选择计费方式。|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|资源组ID不存在。|
|400|OperationUnsupported.ResourceGroupId|ResourceGroup is not supported in this region.|资源组功能未打开。|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

