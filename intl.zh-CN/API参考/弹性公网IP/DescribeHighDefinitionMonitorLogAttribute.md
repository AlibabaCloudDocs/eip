# DescribeHighDefinitionMonitorLogAttribute

调用DescribeHighDefinitionMonitorLogAttribute接口查询EIP高精度秒级监控的配置信息。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=DescribeHighDefinitionMonitorLogAttribute&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|DescribeHighDefinitionMonitorLogAttribute|要执行的操作，取值：**DescribeHighDefinitionMonitorLogAttribute**。 |
|InstanceId|String|是|eip-wz9fi6qboho9fwgx7\*\*\*\*|查询高精度秒级监控的实例ID。 |
|RegionId|String|是|cn-hangzhou|实例所在的地域ID。

您可以通过调用[DescribeRegions](36063)接口获取地域ID。 |
|InstanceType|String|否|EIP|实例的类型。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|InstanceId|String|eip-wz9fi6qboho9fwgx7\*\*\*\*| |
|InstanceType|String|EIP| |
|LogProject|String|hdmonitor-cn-shenzhen-1658206966225390|日志服务LogProjec的名称。 |
|LogStore|String|hdmonitor|日志服务Logstore的名称。 |
|RequestId|String|54B48E3D-DF70-471B-AA93-08E683A1B457|请求ID。 |
|Success|String|true|结果是否调用成功。

-   **true**：调用成功。
-   **false**：调用失败。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=DescribeHighDefinitionMonitorLogAttribute
&InstanceId=eip-wz9fi6qboho9fwgx7****
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML`格式

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

`JSON`格式

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

## 错误码

访问[错误中心](https://error-center.alibabacloud.com/status/product/Vpc)查看更多错误码。

