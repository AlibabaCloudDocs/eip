# DescribeEipMonitorData

Queries the monitoring data of an elastic IP address \(EIP\).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=DescribeEipMonitorData&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEipMonitorData|The operation that you want to perform. Set the value to **DescribeEipMonitorData**. |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6idcfv\*\*\*\*|The ID of the EIP. |
|EndTime|String|Yes|2017-01-05T04:05:10Z|The end of the time range to query. The time must be in UTC. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. Example: 2013-01-10T12:00:00Z, which specifies 20:00:00 on January 10, 2013 \(UTC+8\).

If the value of seconds \(ss\) is not 00, the end time is automatically rounded up to the next minute. |
|StartTime|String|Yes|2017-01-05T02:05:05Z|The beginning of the time range to query. The time must be in UTC. Specify the time in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. Example: 2013-01-10T12:00:00Z, which specifies 20:00:00 on January 10, 2013 \(UTC+8\).

If the value of seconds \(ss\) is not 00, the end time is automatically rounded up to the next minute. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the EIP belongs. |
|Period|Integer|No|60|The duration of a monitoring data entry. Valid values: **60**, **300**, **900**, and **3600**. Unit: seconds. Default value: 60.

-   If the value of \(EndTime-StartTime\) divided by Period is greater than 200, a maximum of 200 monitoring data entries are returned.
-   If the value of \(EndTime-StartTime\) divided by Period is equal to or smaller than 200, only monitoring data entries within the specified time range are returned. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipMonitorDatas|Array of EipMonitorData| |Detailed information about the EIP monitoring data. |
|EipMonitorData| | | |
|EipBandwidth|Integer|10|The bandwidth of the EIP. This value is equal to EipFlow/60. Unit: Bit/s. |
|EipFlow|Integer|675|The sum of inbound and outbound bandwidth. |
|EipPackets|Integer|3434|The number of data packets. |
|EipRX|Long|122|The inbound bandwidth. Unit: Bit/s. |
|EipTX|Long|343|The outbound bandwidth. Unit: Bit/s. |
|TimeStamp|String|2010-01-21T09:50:23Z|The timestamp of the monitoring data. The time is in the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. For example, 2018-12-20T03:14:00Z. |
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9|The ID of the request. |

## Examples

Sample requests

```
http(s)://vpc.aliyuncs.com/? Action=DescribeEipMonitorData
&AllocationId=eip-2zeerraiwb7uj6idcfv****
&EndTime=2017-01-05T04:05:10Z
&StartTime=2017-01-05T02:05:05Z
&<Common request parameters>
```

Sample responses

`XML` format

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

`JSON` format

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

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|404|InvalidInstanceId.NotFound|The InstanceId provided does not exist in our records.|The error message returned because the specified Elastic Compute Service \(ECS\) instance does not belong to the specified virtual private cloud \(VPC\).|
|400|InvalidStartTime.Malformed|The specified parameter "StartTime" is not valid.|The error message returned because the value of the StartTime parameter is invalid.|
|400|InvalidEndTime.Malformed|The specified parameter "EndTime" is not valid.|The error message returned because the value of the EndTime parameter is invalid.|
|400|InvalidPeriod.ValueNotSupported|The specified parameter "Period" is not valid.|The error message returned because the value of the Period parameter is invalid.|
|400|InvalidStartTime.TooEarly|The specified parameter "StartTime" is too early.|The error message returned because the value of the StartTime parameter is invalid.|
|400|InvalidAllocationId.NotFound|Specified allocation id is not found.|The error message returned because the specified EIP does not exist. Check whether the specified ID is correct.|
|400|OperationDenied.TooManyDataQueried|Specified operation is denied as too many data to return.|The error message returned because the number of data entries to be returned exceeds the upper limit.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The error message returned because the specified region does not exist. Check whether the specified region ID is valid.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

