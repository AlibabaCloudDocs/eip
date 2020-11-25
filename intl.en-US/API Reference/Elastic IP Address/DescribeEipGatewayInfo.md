# DescribeEipGatewayInfo

Queries the gateway address and subnet mask of an Elastic IP address.

## API description

You can only query the gateway address and subnet mask of an Elastic IP address that is associated with a secondary Elastic Network Interface \(ENI\) in the multi-EIP to ENI mode.

## Make the API call

[You can use OpenAPI Explorer to make API calls, search for API calls, perform debugging, and generate SDK example code.](https://api.aliyun.com/#product=Vpc&api=DescribeEipGatewayInfo&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|DescribeEipGatewayInfo|The name of this action. Value:**DescribeEipGatewayInfo**. |
|InstanceId|String|Yes|eni-bp1d66qjxb3qoin3\*\*\*\*|The ID of the secondary ENI associated with the Elastic IP address. |
|RegionId|String|Yes|cn-zhangjiakou|The ID of the region to which the Elastic IP address belongs. To query the region ID, call [DescribeRegions](~~36063~~). |

## Response parameters

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Code|String|200|The status code of the request. |
|EipInfos|Array| |The details of the Elastic IP address. |
|EipInfo| | |The details of the Elastic IP address. |
|Ip|String|47.xx.xx.236|The IP address of the Elastic IP address. |
|IpGw|String|47.xx.xx.1|The gateway address of the Elastic IP address. |
|IpMask|String|255.255.255.0|The subnet mask of the Elastic IP address. |
|Message|String|successful|The message indicating whether the request is successful. |
|RequestId|String|C0FD0EED-F90D-4479-803D-DD62335357E5|The ID of the request. |

## Examples

Request example

```

http(s)://vpc.aliyuncs.com/? Action=DescribeEipGatewayInfo
&InstanceId=eni-bp1d66qjxb3qoin3****
&RegionId=cn-zhangjiakou
&<CommonParameters>

```

Response example

`XML` format

```
<DescribeEipGatewayInfoResponse>
	  <Message>successful</Message>
	  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
	  <EipInfos>
		    <EipInfo>
			      <IP>47.xx.xx.236</IP>
			      <IpMask>255.255.255.0</IpMask>
			      <IpGw>47.xx.xx.1</IpGw>
		    </EipInfo>
	  </EipInfos>
	  <Code>200</Code>
</DescribeEipGatewayInfoResponse>
```

`JSON` format

```
{
	"Message":"successful",
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0",
	"EipInfos":{
		"EipInfo":[
			{
				"IpMask":"255.255.255.0",
				"IP":"47.xx.xx.236",
				"IpGw":"47.xx.xx.1"
			}
		]
	},
	"Code":"200"
}
```

## Errors

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

