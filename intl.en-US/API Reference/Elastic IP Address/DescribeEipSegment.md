# DescribeEipSegment

You can call this operation to query a contiguous Elastic IP address group.

## Debugging

[OpenAPI Explorer automatically calculates the signature value. For your convenience, we recommend that you call this operation in OpenAPI Explorer. OpenAPI Explorer dynamically generates the sample code of the operation for different SDKs.](https://api.aliyun.com/#product=Vpc&api=DescribeEipSegment&type=RPC&version=2016-04-28)

## Request parameters

|Parameter|Type|Required|Example|Description|
|---------|----|--------|-------|-----------|
|Action|String|Yes|DescribeEipSegment|The operation that you want to perform. Set the value to **DescribeEipSegment**. |
|RegionId|String|Yes|cn-hangzhou|The ID of the region to which the contiguous Elastic IP address group belongs. You can call the [DescribeRegions](~~36063~~) operation to query the region ID. |
|ClientToken|String|No|02fb3da4-130e-11e9-8e44-001sdfg|The client token that is used to ensure the idempotence of the request. You can use the client to generate a token, but you must ensure that the token is unique among different requests. The token must be a maximum of 64 characters in length and can contain only ASCII characters. |
|SegmentInstanceId|String|No|eipsg-2zett8ba055tbsxme\*\*\*\*|The ID of the instance to query. The contiguous Elastic IP address group is associated with the instance. |
|PageNumber|Integer|No|1|The number of the page to return. Pages start from page 1. Default value: **1**. |
|PageSize|Integer|No|10|The number of entries to return on each page. Valid values: 1 to **50**. Default value: **10**. |

## Response parameters

|Parameter|Type|Example|Description|
|---------|----|-------|-----------|
|EipSegments|Array| |The details about the contiguous Elastic IP address group. |
|EipSegment| | | |
|CreationTime|String|2020-03-06T12:30:07Z|The time when the contiguous Elastic IP address group was created. The time follows the ISO 8601 standard in the yyyy-MM-ddTHH:mm:ssZ format. The time is displayed in UTC. |
|Description|String|MyEipSegment|The description of the contiguous Elastic IP address group. |
|InstanceId|String|eipsg-2zett8ba055tbsxme\*\*\*\*|The ID of the instance with which the contiguous Elastic IP address group is associated. |
|IpCount|String|28|The number of IP addresses contained in the contiguous Elastic IP address group. |
|Name|String|MyEipSegment|The name of the contiguous Elastic IP address group. |
|RegionId|String|cn-hangzhou|The ID of the region to which the contiguous Elastic IP address group belongs. |
|Segment|String|161.xx.xx.32/28|The CIDR block and mask of the contiguous Elastic IP address group. |
|Status|String|Allocated|The status of the contiguous Elastic IP address group. Valid values:

-   **Allocating**: The contiguous Elastic IP address group is being allocated.
-   **Allocated**: The contiguous Elastic IP address group is allocated.
-   **Releasing**: The contiguous Elastic IP address group is being released.
-   **Released**: The contiguous Elastic IP address group is released. |
|PageNumber|Integer|2|The page number of the returned page. |
|PageSize|Integer|10|The number of entries returned per page. |
|RequestId|String|F7A6301A-64BA-41EC-8284-8F4838C15D1F|The ID of the request. |
|TotalCount|Integer|1|The total number of entries returned. |

## Examples

Sample requests

```
http(s)://[Endpoint]/? Action=DescribeEipSegment
&RegionId=cn-hangzhou
&<Common request parameters>
```

Sample success responses

`XML` format

```
<DescribeEipSegmentResponse>
  <EipSegments>
        <EipSegment>
              <Status>Allocated</Status>
              <Description></Description>
              <IpCount>16</IpCount>
              <InstanceId>eipsg-t4nr90yik5oy38xdy****</InstanceId>
              <CreationTime>2020-03-06T12:30:07Z</CreationTime>
              <RegionId>ap-southeast-1</RegionId>
              <Segment>161.xx.xx.32/28</Segment>
              <Name></Name>
        </EipSegment>
  </EipSegments>
  <TotalCount>1</TotalCount>
  <PageSize>50</PageSize>
  <RequestId>A4862138-CCF6-4A24-BDE4-39055DFEFB92</RequestId>
  <PageNumber>1</PageNumber>
</DescribeEipSegmentResponse>
```

`JSON` format

```
{
    "EipSegments": {
        "EipSegment": [
            {
                "Status": "Allocated",
                "Description": "",
                "IpCount": 16,
                "InstanceId": "eipsg-t4nr90yik5oy38xdy****",
                "CreationTime": "2020-03-06T12:30:07Z",
                "RegionId": "ap-southeast-1",
                "Segment": "161.xx.xx.32/28",
                "Name": ""
            }
        ]
    },
    "TotalCount": 1,
    "PageSize": 50,
    "RequestId": "A4862138-CCF6-4A24-BDE4-39055DFEFB92",
    "PageNumber": 1
}
```

## Error codes

For a list of error codes, visit the [API Error Center](https://error-center.alibabacloud.com/status/product/Vpc).

