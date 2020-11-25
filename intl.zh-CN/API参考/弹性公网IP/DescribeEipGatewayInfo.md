# DescribeEipGatewayInfo

调用DescribeEipGatewayInfo接口查询EIP的网关和掩码信息。

## API描述

仅支持查询以多EIP网卡可见模式绑定辅助弹性网卡的EIP的网关和掩码信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeEipGatewayInfo&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEipGatewayInfo|要执行的操作，取值：**DescribeEipGatewayInfo**。 |
|InstanceId|String|是|eni-bp1d66qjxb3qoin3\*\*\*\*|要查询的EIP绑定的辅助弹性网卡的ID。 |
|RegionId|String|是|cn-zhangjiakou|要查询的EIP所属的地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|操作状态码。 |
|EipInfos|Array| |EIP详细信息。 |
|EipInfo| | |EIP详细信息。 |
|Ip|String|47.xx.xx.236|EIP的IP地址。 |
|IpGw|String|47.xx.xx.1|EIP的网关地址。 |
|IpMask|String|255.255.255.0|EIP的子网掩码。 |
|Message|String|successful|传递的操作信息。 |
|RequestId|String|C0FD0EED-F90D-4479-803D-DD62335357E5|请求ID。 |

## 示例

请求示例

```

http(s)://vpc.aliyuncs.com/?Action=DescribeEipGatewayInfo
&InstanceId=eni-bp1d66qjxb3qoin3****
&RegionId=cn-zhangjiakou
&<公共请求参数>

```

正常返回示例

`XML` 格式

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

`JSON` 格式

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

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden|User not authorized to operate on the specified resource.|您没有权限操作该资源，请您申请操作权限后再试。|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

