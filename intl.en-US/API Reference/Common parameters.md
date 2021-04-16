# Common parameters

Common parameters include common request parameters and common response parameters.

## Common request parameters

Common request parameters must be included in all Virtual Private Cloud \(VPC\) API requests.

|Parameter|Type|Required|Description|
|:--------|:---|:-------|:----------|
|Format|String|No|The format in which to return the response. Valid values: JSON and XML. Default value: JSON. |
|Version|String|Yes|The version number of the API. Format: `YYYY-MM-DD`. Set the value to 2016-04-28. |
|AccessKeyId|String|Yes|The AccessKey ID provided by Alibaba Cloud.|
|Signature|String|Yes|The signature string of the current request.|
|SignatureMethod|String|Yes|The encryption method of the signature string. Set the value to HMAC-SHA1. |
|Timestamp|String|Yes|The timestamp of the request. Specify the time in the ISO 8601 standard in the `YYYY-MM-DDThh:mm:ssZ` format. The time must be in UTC. For example, 2013-01-10T12:00:00Z specifies 20:00:00 on January 10, 2013 \(UTC+8\). |
|SignatureVersion|String|Yes|The version of the signature encryption algorithm. Set the value to 1.0. |
|SignatureNonce|String|Yes|A unique, random number that is used to prevent replay attacks. You must use different random numbers for different requests. |

## Common response parameters

API responses use the HTTP response format. A 2XX status code indicates a successful call and a 4XX or 5XX status code indicates a failed call. Responses can be returned in JSON or XML format. The default response format is JSON. You can specify the format when you call an operation.

Each response returns a unique RequestId regardless of whether the call is successful.

-   XML format

    ```
    <? xml version="1.0" encoding="utf-8"? > 
        <!-Result Root Node-->
        <Interface Name+Response>
            <!-Return Request Tag-->
            <RequestId>4C467B38-3910-447D-87BC-AC049166F216</RequestId>
            <!-Return Result Data-->
        </Interface Name+Response>
                        
    ```

-   JSON format

    ```
    {
        "RequestId":"4C467B38-3910-447D-87BC-AC049166F216",
        /*Return Result Data*/
        }
    ```


