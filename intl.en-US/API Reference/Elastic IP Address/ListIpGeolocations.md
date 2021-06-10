# ListIpGeolocations

Queries the geographical locations of IP addresses.

## Limits

-   You can use the [GeoIP Databases](https://www.aliyun.com/product/dns/geoip) service of Alibaba Cloud to query the geographical locations of IP addresses provided by Alibaba Cloud and third-party service providers.
-   By default, you cannot call this operation in OpenAPI Explorer. To call this operation in OpenAPI Explorer, [submit a ticket](https://selfservice.console.aliyun.com/ticket/category/eip/today).

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Netana&api=ListIpGeolocations&type=RPC&version=2020-10-16)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|No|ListIpGeolocations|The operation that you want to perform. Set the value to **ListIpGeolocations**. |
|CountryCode|String|No|CN|The country to which the public IP addresses belong. Specify the country code in the ISO 3166 standard. |
|CityCode|String|No|HK|The city to which the public IP addresses belong. Specify the city code in the ISO 3166 standard. |
|Ipv4Prefix|String|No|203.0.XX.XX/24|The IPv4 CIDR block that you want to query.

 Example: `203.0.XX.XX/24`. If you specify only `203.0.XX.XX`, the system queries the geographical locations of `203.0.XX.XX/32`. |
|ResourcePoolName|String|No|Alibaba\_Cloud|The name of the IP address pool. Valid values: **Alibaba\_Cloud** and **Alibaba\_CDN**. |
|NextToken|String|No|caeba0bbb2be03f84eb48b699f0a4883|The query token. Set this parameter to the NextToken value that is returned in the last API call. If no subsequent queries are to be sent, leave this parameter empty. |
|MaxResults|Integer|No|50|The number of entries to return on each page.

 Maximum value: **100**.

 Default value: **20**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|IpGeolocationModels|Array of IpGeolocationModel| |The list of geographical locations. |
|IpGeolocationModel| | | |
|CityCode|String|HK|The city to which the public IP addresses belong. The value follows the ISO 3166 standard. |
|CountryCode|String|CN|The country to which the public IP addresses belong. The value follows the ISO 3166 standard. |
|Ipv4Prefix|String|203.0.XX.XX/24|The IPv4 CIDR block. |
|ResourcePoolName|String|Alibaba\_Cloud|The name of the IP address pool. |
|MaxResults|Integer|50|The number of entries returned per page. |
|NextToken|String|caeba0bbb2be03f84eb48b699f0a4883|The token that is used for the next query. If this parameter is not set, no subsequent requests are sent. |
|RequestId|String|365F4154-92F6-4AE4-92F8-7FF34B540710|The ID of the request. |
|TotalCount|Integer|100|The total number of IP addresses that are queried. |

## Examples

Sample requests

```
http(s)://[Endpoint]/?Action=ListIpGeolocations
&<Common request parameters>
```

Sample success responses

`XML` format

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

`JSON` format

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

## Error codes

|HttpCode|Error code|Error message|Description|
|--------|----------|-------------|-----------|
|400|OperationFailed.QueryIpPoolFailed|Failed to query IP resource pool.|The error message returned because the system failed to query the IP address pool.|
|400|OperationFailed.InvokeApi|Failed to invoke the API operation.|The error message returned because the system failed to call the API.|
|400|OperationFailed.InternalError|An internal error occurred.|The error message returned because an internal error occurred.|
|400|IllegalParam.Ipv4Prefix|The parameter Ipv4Prefix is invalid.|The error message returned because the specified IPv4 CIDR block is invalid.|
|400|IllegalParam.ResourcePoolName|The parameter ResourcePoolName is invalid.|The error message returned because the specified IP address pool is invalid.|
|400|OperationFailed.NoPermission|You are not authorized to call the API operation.|The error message returned because you are unauthorized to call the API.|

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Netana).

