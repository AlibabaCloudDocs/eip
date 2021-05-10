# ListIpGeolocations

调用ListIpGeolocations查询IP归属地。

## 限制说明

-   如果需要使用全网的IP归属地查询服务，请使用阿里云[IP地理位置库](https://www.aliyun.com/product/dns/geoip)产品，该产品覆盖了全量IP的定位数据。
-   本接口暂不支持在OpenAPIExplorer中运行调用。如果您想使用OpenAPI Explorer来调用该接口，请先[提交工单](https://selfservice.console.aliyun.com/ticket/category/eip/today)获取调用权限。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Netana&api=ListIpGeolocations&type=RPC&version=2020-10-16)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|否|ListIpGeolocations|要执行的操作，取值：**ListIpGeolocations**。 |
|CountryCode|String|否|CN|公网IP所在的国家，该参数值符合ISO 3166定义，您可以自行查询。 |
|CityCode|String|否|HK|公网IP所在的城市，该参数值符合ISO 3166定义，您可以自行查询。 |
|Ipv4Prefix|String|否|203.0.XX.XX/24|要查询的IPv4地址段。

 例如：`203.0.XX.XX/24`，如只输入`203.0.XX.XX`，则查询`203.0.XX.XX/32`。 |
|ResourcePoolName|String|否|Alibaba\_Cloud|资源池名称，取值：**Alibaba\_Cloud**或**Alibaba\_CDN**。 |
|NextToken|String|否|caeba0bbb2be03f84eb48b699f0a4883|查询凭证（Token），取值为上一次API调用返回的NextToken参数值。如果没有下一个查询，请勿传参。 |
|MaxResults|Integer|否|50|分页查询时每页条数。

 最大值：**100**。

 默认值：**20**。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|IpGeolocationModels|Array of IpGeolocationModel| |IP归属地列表。 |
|IpGeolocationModel| | | |
|CityCode|String|HK|公网IP所在的城市，参数值符合ISO 3166定义。 |
|CountryCode|String|CN|公网IP所在的国家，参数值符合ISO 3166定义。 |
|Ipv4Prefix|String|203.0.XX.XX/24|IPv4地址段。 |
|ResourcePoolName|String|Alibaba\_Cloud|资源池名称。 |
|MaxResults|Integer|50|分页查询时每页显示条数。 |
|NextToken|String|caeba0bbb2be03f84eb48b699f0a4883|下一个查询开始的Token，为空表示没有下一个。 |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|请求ID。 |
|TotalCount|Integer|100|查询到归属地的IP总数。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ListIpGeolocations
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<ListIpGeolocationsResponse>
  <IpGeolocationModels>
        <IpGeolocationModel>
              <CityCode>HK</CityCode>
              <ResourcePoolName>Alibaba_Cloud</ResourcePoolName>
              <CountryCode>CN</CountryCode>
              <Ipv4Prefix>203.0.XX.XX/24</Ipv4Prefix>
        </IpGeolocationModel>
  </IpGeolocationModels>
  <TotalCount>100</TotalCount>
  <NextToken>caeba0bbb2be03f84eb48b699f0a4883</NextToken>
  <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId>
  <MaxResults>50</MaxResults>
</ListIpGeolocationsResponse>
```

`JSON`格式

```
{
    "ListIpGeolocationsResponse": {
        "IpGeolocationModels": {
            "IpGeolocationModel": {
                "CityCode": "HK",
                "ResourcePoolName": "Alibaba_Cloud",
                "CountryCode": "CN",
                "Ipv4Prefix": "203.0.XX.XX/24"
            }
        },
        "TotalCount": 100,
        "NextToken": "caeba0bbb2be03f84eb48b699f0a4883",
        "RequestId": "365F4154-92F6-4AE4-92F8-7FF34B540710",
        "MaxResults": 50
    }
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|400|OperationFailed.QueryIpPoolFailed|Failed to query IP resource pool.|查询IP资源库失败|
|400|OperationFailed.InvokeApi|Failed to invoke the API operation.|调用API失败|
|400|OperationFailed.InternalError|An internal error occurred.|内部错误|
|400|IllegalParam.Ipv4Prefix|The parameter Ipv4Prefix is invalid.|参数Ipv4Prefix非法|
|400|IllegalParam.ResourcePoolName|The parameter ResourcePoolName is invalid.|参数ResourcePoolName非法|
|400|OperationFailed.NoPermission|You are not authorized to call the API operation.|没有接口调用权限|

访问[错误中心](https://error-center.alibabacloud.com/status/product/Netana)查看更多错误码。

