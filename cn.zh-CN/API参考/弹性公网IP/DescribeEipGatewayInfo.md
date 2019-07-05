# DescribeEipGatewayInfo {#doc_api_Vpc_DescribeEipGatewayInfo .reference}

调用DescribeEipGatewayInfo接口查询EIP的网关和掩码信息。

仅支持查询以多EIP网卡可见模式绑定辅助弹性网卡的EIP的网关和掩码信息。

## 调试 {#apiExplorer .section}

前往【[API Explorer](https://api.aliyun.com/#product=Vpc&api=DescribeEipGatewayInfo)】在线调试，API Explorer 提供在线调用 API、动态生成 SDK Example 代码和快速检索接口等能力，能显著降低使用云 API 的难度，强烈推荐使用。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeEipGatewayInfo|要执行的操作，取值：**DescribeEipGatewayInfo**。

 |
|InstanceId|String|是|eni-bp1d66qjxb3qoin3xxxx|绑定EIP的弹性网卡的实例ID。

 |
|RegionId|String|是|cn-zhangjiakou|EIP的所属地域。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|Code|String|200|操作状态码。

 |
|EipInfos| | |EIP详细信息。

 |
|Ip|String|47.xx.xx.236|EIP的IP地址。

 |
|IpGw|String|47.xx.xx.1|EIP的网关地址。

 |
|IpMask|String|255.255.255.0|EIP的子网掩码。

 |
|Message|String|successful|传递的操作信息。

 |
|RequestId|String|C0FD0EED-F90D-4479-803D-DD62335357E5|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://vpc.aliyuncs.com/?Action=DescribeEipGatewayInfo
&InstanceId=eni-bp1d66qjxb3qoin3****
&RegionId=cn-zhangjiakou
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
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

``` {#json_return_success_demo}
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

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden|User not authorized to operate on the specified resource.|您没有权限操作该资源，请您申请操作权限后再试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

