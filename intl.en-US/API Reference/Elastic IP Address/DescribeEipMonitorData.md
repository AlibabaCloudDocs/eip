# DescribeEipMonitorData {#doc_api_Vpc_DescribeEipMonitorData .reference}

Queries the monitoring data of an Elastic IP address \(EIP\).

## Debug {#api_explorer .section}

[Use OpenAPI Explorer to perform debug operations and generate SDK code examples.](https://api.aliyun.com/#product=Vpc&api=DescribeEipMonitorData&type=RPC&version=2016-04-28)

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|DescribeEipMonitorData| The name of this action. Value: **DescribeEipMonitorData**

 |
|AllocationId|String|Yes|eip-2zeerraiwb7uj6ixxxxxxxx| The instance ID of the EIP.

 |
|EndTime|String|Yes|2017-01-05T01:05:10Z| The end time to retrieve data. This parameter uses the ISO 8601 format and is output in UTC+8. Format: YYYY-MM-DDThh:mm:ssZ. For example, 20:00:00 UTC+8 of January 10, 2013 should be in the format of 2013-01-10T12:00:00Z.

 If ss is not 00, the next minute is automatically used as the end time.

 |
|RegionId|String|Yes|cn-hangzhou| The ID of the region to which the EIP belongs.

 |
|StartTime|String|Yes|2017-01-05T02:05:05Z| The start time to retrieve data. This parameter uses the ISO 8601 format and is output in UTC+8. Format: YYYY-MM-DDThh:mm:ssZ. For example, 20:00:00 UTC+8 of January 10, 2013 should be in the format of 2013-01-10T12:00:00Z.

 If ss is not 00, the next minute is automatically used as the start time.

 |
|Period|Integer|No|60| Optional. The time length of each monitoring data point. Default value: 60. Valid values: 60 | 600 | 3600. Unit: seconds

 -   The value of \(EndTime – StartTime\)/Period must be larger than 200, that is, up to 200 points of monitoring data are returned.
-   If the value of \(EndTime – StartTime\) is smaller than 200, only the monitoring data collected at the start time is returned.

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|EipMonitorDatas| | | The details of EIP monitoring data.

 |
|EipBandwidth|Integer|10| The value of the bandwidth: EipFlow/60. Unit: bit/s.

 |
|EipFlow|Integer|675| The sum of the inbound and outbound bandwidth.

 |
|EipPackets|Integer|3434| The number of packets.

 |
|EipRX|Integer|122| The inbound bandwidth. Unit: Bytes.

 |
|EipTX|Integer|343| The outbound bandwidth. Unit: Bytes.

 |
|TimeStamp|String|2010-01-21T09:50:23Z| The timestamp of the query in ISO8601 format. Example value: 2018-12-20T03:14:00Z.

 |
|RequestId|String|C8B26B44-0189-443E-9816-D951F59623A9| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

https://vpc.aliyuncs.com/?Action=DescribeEipMonitorData
&AllocationId=eip-2zeerraiwb7uj6ixxxxxxxx
&EndTime=2017-01-05T01:05:10Z
&StartTime=2017-01-05T02:05:05Z
&<CommonParameters>

```

Response example

`XML` format

``` {#xml_return_success_demo}
<DescribeEipMonitorData>
	  <RequestId>B7D72D42-8A6C-4764-963B-5F7C049FA769</RequestId>
	  <EipMonitorDatas>
		    <EipMonitorData>
			      <TimeStamp>2019-05-29T03:39:00Z</TimeStamp>
			      <EipFlow>32666910</EipFlow>
			      <EipTX>140370</EipTX>
			      <EipPackets>23700</EipPackets>
			      <EipRX>32526540</EipRX>
			      <EipBandwidth>544448</EipBandwidth>
		    </EipMonitorData>
		    <EipMonitorData>
			      <TimeStamp>2019-05-29T03:40:00Z</TimeStamp>
			      <EipFlow>43020</EipFlow>
			      <EipTX>17730</EipTX>
			      <EipPackets>120</EipPackets>
			      <EipRX>25290</EipRX>
			      <EipBandwidth>717</EipBandwidth>
		    </EipMonitorData>
	  </EipMonitorDatas>
</DescribeEipMonitorData>
```

`JSON` format

``` {#json_return_success_demo}
{
	"RequestId":"B7D72D42-8A6C-4764-963B-5F7C049FA769",
	"EipMonitorDatas":{
		"EipMonitorData":[
			{
				"TimeStamp":"2019-05-29T03:39:00Z",
				"EipTX":140370,
				"EipFlow":32666910,
				"EipPackets":23700,
				"EipRX":32526540,
				"EipBandwidth":544448
			},
			{
				"TimeStamp":"2019-05-29T03:40:00Z",
				"EipTX":17730,
				"EipFlow":43020,
				"EipPackets":120,
				"EipRX":25290,
				"EipBandwidth":717
			}
		]
	}
}
```

## Errors {#section_26j_vpw_544 .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|404|InvalidInstanceId.NotFound|The InstanceId provided does not exist in our records.|The specified instance ID does not exist.|
|400|InvalidStartTime.Malformed|The specified parameter "StartTime" is not valid.|The format of the specified start time is invalid.|
|400|InvalidEndTime.Malformed|The specified parameter "EndTime" is not valid.|The format of the specified end time is invalid.|
|400|InvalidPeriod.ValueNotSupported|The specified parameter "Period" is not valid.|The specified period value is invalid.|
|400|InvalidStartTime.TooEarly|The specified parameter "StartTime" is too early.|The specified start time is invalid.|
|400|InvalidAllocationId.NotFound|Specified allocation id is not found.|The specified public IP address does not exist. Check if you have entered the correct public IP address.|
|400|OperationDenied.TooManyDataQueried|Specified operation is denied as too many data to return.|The operation cannot be performed because too much data is returned.|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|The specified region does not exist.|

