# DescribeEipMonitorData

调用DescribeEipMonitorData接口查看EIP的监控信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeEipMonitorData&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEipMonitorData|要执行的操作，取值： **DescribeEipMonitorData**。 |
|AllocationId|String|是|eip-2zeerraiwb7uj6idcfv\*\*\*\*|EIP的实例ID。 |
|EndTime|String|是|2017-01-05T04:05:10Z|获取数据的结束时间。使用UTC时间。按照ISO8601标准，格式为YYYY-MM-DDThh:mm:ssZ。例如，北京时间2013年1月10日20点0分0秒，表示为2013-01-10T12:00:00Z。

如果秒不是00，则自动取下一分钟为结束时间点。 |
|StartTime|String|是|2017-01-05T02:05:05Z|获取数据的起始时间。使用UTC时间。按照ISO8601标准，格式为YYYY-MM-DDThh:mm:ssZ。例如，北京时间2013年1月10日20点0分0秒，表示为2013-01-10T12:00:00Z。

如果秒不是00，则自动取下一分钟为起始时间点。 |
|RegionId|String|是|cn-hangzhou|EIP所属地域ID。 |
|Period|Integer|否|60|每条监控数据的时间长度，取值：**60**（默认值） 、**300** 、 **900** 、 **3600**，单位为秒。

-   如果（EndTime–StartTime）/ Peroid大于200，则最多返回200条监控数据。
-   如果（EndTime–StartTime）/ Peroid小于等于200，则只返回起始时间点到结束时间点的监控数据。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|EipMonitorDatas|Array of EipMonitorData| |EIP监控数据的详细信息。 |
|EipMonitorData| | | |
|EipBandwidth|Integer|10|带宽值，该值等于EipFlow/60，单位为Bps。 |
|EipFlow|Integer|675|流入和流出的带宽总和。 |
|EipPackets|Integer|3434|包数量。 |
|EipRX|Long|122|流入的带宽。单位为Byte。 |
|EipTX|Long|343|流出的带宽。单位为Byte。 |
|TimeStamp|String|2010-01-21T09:50:23Z|查询监控信息的时间戳。ISO8601格式，如2018-12-20T03:14:00Z。 |
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|请求ID。 |

## 示例

请求示例

```
http(s)://vpc.aliyuncs.com/?Action=DescribeEipMonitorData
&AllocationId=eip-2zeerraiwb7uj6idcfv****
&EndTime=2017-01-05T04:05:10Z
&StartTime=2017-01-05T02:05:05Z
&<公共请求参数>
```

正常返回示例

`XML` 格式

```
<DescribeEipMonitorData>
  <RequestId>C8B26B44-0189-443E-9816-D951F59623A9</RequestId>
  <EipMonitorDatas>
        <EipMonitorData>
              <EipPackets>3434</EipPackets>
              <EipBandwidth>10</EipBandwidth>
              <EipFlow>675</EipFlow>
              <EipTX>343</EipTX>
              <TimeStamp>2010-01-21T09:50:23Z</TimeStamp>
              <EipRX>122</EipRX>
        </EipMonitorData>
  </EipMonitorDatas>
</DescribeEipMonitorData>
```

`JSON` 格式

```
{
    "RequestId": "C8B26B44-0189-443E-9816-D951F59623A9",
    "EipMonitorDatas": {
        "EipMonitorData": {
            "EipPackets": 3434,
            "EipBandwidth": 10,
            "EipFlow": 675,
            "EipTX": 343,
            "TimeStamp": "2010-01-21T09:50:23Z",
            "EipRX": 122
        }
    }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|InvalidInstanceId.NotFound|The InstanceId provided does not exist in our records.|该 ECS 实例不存在（实例不在该 VPC 下）。|
|400|InvalidStartTime.Malformed|The specified parameter "StartTime" is not valid.|开始时间不合法。|
|400|InvalidEndTime.Malformed|The specified parameter "EndTime" is not valid.|该结束时间不合法。|
|400|InvalidPeriod.ValueNotSupported|The specified parameter "Period" is not valid.|参数Period的值不合法。|
|400|InvalidStartTime.TooEarly|The specified parameter "StartTime" is too early.|开始时间不合法。|
|400|InvalidAllocationId.NotFound|Specified allocation id is not found.|指定的公网 IP 不存在，请您检查填写的公网 IP 是否正确。|
|400|OperationDenied.TooManyDataQueried|Specified operation is denied as too many data to return.|一次查询返回的数据量过多。|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

