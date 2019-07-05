# DescribeEipGatewayInfo {#doc_api_Vpc_DescribeEipGatewayInfo .reference}

Queries the gateway address and subnet mask of an EIP.

You can only query the gateway address and subnet mask of an EIP that is associated with a secondary Elastic Network Interface \(ENI\) in the multi-EIP to ENI mode.

## Debug {#apiExplorer .section}

Use [OpenAPI Explorer](https://api.aliyun.com/#product=Vpc&api=DescribeEipGatewayInfo) to perform debug operations and generate SDK code examples.

## Request parameters {#parameters .section}

|Parameter|Type|Required?|Example value|Description|
|---------|----|---------|-------------|-----------|
|Action|String|Yes|DescribeEipGatewayInfo| The name of this action. Value: **DescribeEipGatewayInfo**

 |
|InstanceId|String|Yes|eni-bp1d66qjxb3qoin3xxxx| The ID of the ENI with which the EIP is associated.

 |
|RegionId|String|Yes|cn-zhangjiakou| The region ID of the EIP. To query the region ID, call [DescribeRegions](~~36063~~).

 |

## Response parameters {#resultMapping .section}

|Parameter|Type|Example value|Description|
|---------|----|-------------|-----------|
|Code|String|200| The status code of the request.

 |
|EipInfos| | | The details of the EIP.

 |
|Ip|String|47.xx.xx.236| The IP address of the EIP.

 |
|IpGw|String|47.xx.xx.1| The gateway address of the EIP.

 |
|IpMask|String|255.255.255.0| The subnet mask of the EIP.

 |
|Message|String|successful| The message indicating whether the request is successful.

 |
|RequestId|String|C0FD0EED-F90D-4479-803D-DD62335357E5| The ID of the request.

 |

## Examples {#demo .section}

Request example

``` {#request_demo}

http(s)://vpc.aliyuncs.com/? Action=DescribeEipGatewayInfo
&InstanceId=eni-bp1d66qjxb3qoin3****
&RegionId=cn-zhangjiakou
&<CommonParameters>

```

Response examples

`XML` format

``` {#xml_return_success_demo}
<DescribeEipGatewayInfoResponse>
  <Message>successful</Message>
  <RequestId>0ED8D006-F706-4D23-88ED-E11ED28DCAC0</RequestId>
  <EipInfos>
    <EipInfo>
      <IP>47.xx.xx. 236</IP>
      <IpMask>255.255.255.0</IpMask>
      <IpGw>47.xx.xx. 1</IpGw>
    </EipInfo>
  </EipInfos>
  <Code>200</Code>
</DescribeEipGatewayInfoResponse>

```

`JSON` format

``` {#json_return_success_demo}
{
	"Message":"successful",
	"RequestId":"0ED8D006-F706-4D23-88ED-E11ED28DCAC0",
	"EipInfos":{
		"EipInfo":[
			{
				"IpMask":"255.255.255.0",
				"IP":"47.xx.xx. 236",
				"IpGw":"47.xx.xx. 1"
			}
		]
	},
	"Code":"200"
}
```

## Error codes {#section_6d8_2uc_6h4 .section}

|HTTP status code|Error code|Error message|Description|
|----------------|----------|-------------|-----------|
|403|Forbbiden|User not authorized to operate on the specified resource.|You are not authorized to operate on this resource.|

