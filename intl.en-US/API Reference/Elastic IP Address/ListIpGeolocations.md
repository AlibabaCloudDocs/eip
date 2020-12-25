# ListIpGeolocations

Call ListIpGeolocations queries the IP geolocations.

## Limits

This operation cannot be called directly in OpenAPI Explorer.

If you want to use OpenAPI Explorer to invoke the interface, please [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to obtain the call permission.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. You can use OpenAPI Explorer to search for API operations, call API operations, and dynamically generate SDK sample code.](https://api.aliyun.com/#product=Netana&api=ListIpGeolocations&type=RPC&version=2020-10-16)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListIpGeolocations|The operation that you want to perform. Set the value to **listIpGelocations**. |
|CountryCode|String|No|CN|The country id of the public IP address. The returned value complies with the ISO 3166 definition. |
|CityCode|String|No|HK|The city where the public IP address resides. The value of this parameter complies with the ISO 3166 definition. |
|Ipv4Prefix|String|No|203.0.113.0/24|The IPv4 CIDR block to be queried. For example: 203.0.113.0/24. |
|ResourcePoolName|String|No|Alibaba\_Cloud|Resource pool name. Value: **Alibaba\_Cloud** Or **Alibaba\_CDN**. |
|NextToken|String|No|caeba0bbb2be03f84eb48b699f0a4883|The query token. Set this parameter to the NextToken parameter value that is returned in the last API call. If no subsequent request is sent, you do not need to set this parameter. |
|MaxResults|Integer|No|50|The number of entries to return on each page.

Maximum value: **100** ,

Default value: **20** . |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|IpGeolocationModels|Array of IpGeolocationModel| |The IP location list. |
|IpGeolocationModel| | | |
|CityCode|String|HK|The city where the public IP address resides. The value of this parameter complies with the ISO 3166 definition. |
|CountryCode|String|CN|The country id of the public IP address. The returned value complies with the ISO 3166 definition. |
|Ipv4Prefix|String|203.0.113.0/24|IPv4 address segment. |
|ResourcePoolName|String|Alibaba\_Cloud|The name of the resource pool. |
|MaxResults|Integer|50|The number of entries to return on each page. |
|NextToken|String|caeba0bbb2be03f84eb48b699f0a4883|The start Token for the next query. If the value is null, there is no next Token. |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request. |
|TotalCount|Integer|100|The total number of IP addresses that are located in the specified geographical location. |

## Examples

Sample request

```

     http(s)://[Endpoint]/? Action=ListIpGeolocations &<common request parameters> 
   
```

Sample success responses

`XML` format

```

     <IpGeolocationModelsResponse> <IpGeolocationModels> <IpGeolocationModel> <CityCode>HK</CityCode> <ResourcePoolName>Alibaba_Cloud</ResourcePoolName> <CountryCode>CN</CountryCode> <Ipv4Prefix>203.0.113.0/24</Ipv4Prefix> </IpGeolocationModel> </IpGeolocationModels> <TotalCount>100</TotalCount> <NextToken>caeba0bbb2be03f84eb48b699f0a4883</NextToken> <RequestId>365F4154-92F6-4AE4-92F8-7FF34B540710</RequestId> <MaxResults>50</MaxResults> </IpGeolocationModelsResponse> 
   
```

`JSON`

```

     {"IpGeolocationModels":{"IpGeolocationModel":[{"CityCode":"HK","ResourcePoolName":"Alibaba_Cloud","CountryCode":"CN","Ipv4Prefix":"203.0.113.0/24"}]},"TotalCount":"100","NextToken":"caeba0bbb2be03f84eb48b699f0a4883","RequestId":"365F4154-92F6-4AE4-92F8-7FF34B540710","MaxResults":"50"} 
   
```

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|OperationFailed.QueryIpPoolFailed|Failed to query IP resource pool.|Failed to query the ip address repository.|
|400|OperationFailed.InvokeApi|Failed to invoke the API operation.|API call failed|
|400|OperationFailed.InternalError|An internal error occurred.|The error message returned because an internal error has occurred.|
|400|IllegalParam.Ipv4Prefix|The parameter Ipv4Prefix is invalid.|The specified Ipv4Prefix is invalid.|
|400|IllegalParam.ResourcePoolName|The parameter ResourcePoolName is invalid.|The parameter ResourcePoolName is invalid.|
|400|OperationFailed.NoPermission|You are not authorized to call the API operation.|You are not authorized to call the operation.|

For more information about error codes, see [error center](https://error-center.alibabacloud.com/status/product/Netana).

