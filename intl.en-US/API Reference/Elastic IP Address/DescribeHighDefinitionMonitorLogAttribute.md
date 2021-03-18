# DescribeHighDefinitionMonitorLogAttribute

Queries fine-grained monitoring configurations about an EIP.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=DescribeHighDefinitionMonitorLogAttribute&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeHighDefinitionMonitorLogAttribute|The operation that you want to perform. Set the value to**DescribeHighDefinitionMonitorLogAttribute**. |
|InstanceId|String|Yes|eip-wz9fi6qboho9fwgx7\*\*\*\*|The ID of the fine-grained monitoring instance. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region where the instance is deployed.

You can call the [DescribeRegions](~~36063~~) operation to query region IDs. |
|InstanceType|String|No|EIP|The type of the instance. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|InstanceId|String|eip-wz9fi6qboho9fwgx7\*\*\*\*| |
|InstanceType|String|EIP| |
|LogProject|String|hdmonitor-cn-shenzhen-1658206966225390|The name of the log project of Log Service. |
|LogStore|String|hdmonitor|The name of the Logstore of Log Service. |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|The ID of the request. |
|Success|String|true|Indicates whether the call is successful.

-   **true**: The call is successful.
-   **false**: The call failed. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeHighDefinitionMonitorLogAttribute
&InstanceId=eip-wz9fi6qboho9fwgx7****
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeHighDefinitionMonitorLogAttributeResponse>
  <RequestId>54B48E3D-DF70-471B-AA93-08E683A1B457</RequestId>
  <LogStore>hdmonitor</LogStore>
  <InstanceId>eip-wz9fi6qboho9fwgx7****</InstanceId>
  <InstanceType>EIP</InstanceType>
  <LogProject>hdmonitor-cn-shenzhen-1658206966225390</LogProject>
  <Success>true</Success>
</DescribeHighDefinitionMonitorLogAttributeResponse>
```

`JSON` format

```
{
    "RequestId": "54B48E3D-DF70-471B-AA93-08E683A1B457",
    "LogStore": "hdmonitor",
    "InstanceId": "eip-wz9fi6qboho9fwgx7****",
    "InstanceType": "EIP",
    "LogProject": "hdmonitor-cn-shenzhen-1658206966225390",
    "Success": true
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

