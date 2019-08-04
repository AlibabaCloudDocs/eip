# ModifyRouteEntry {#doc_api_Vpc_ModifyRouteEntry .reference}

调用ModifyRouteEntry修改一条自定义路由条目的名称。

## 调试 {#api_explorer .section}

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=ModifyRouteEntry&type=RPC&version=2016-04-28)

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ModifyRouteEntry|要执行的操作，取值：**ModifyRouteEntry**。

 |
|RegionId|String|是|cn-hangzhou|路由条目所在的地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。

 |
|RouteEntryId|String|是|rte-1234567890|自定义路由条目ID。

 |
|RouteEntryName|String|否|EntryName|路由条目的名称。

 长度为2~128个字符，必须以字母或中文开头，但不能以`http://`或`https://`开头。

 |

## 返回数据 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|861E6630-AEC0-4B2D-B214-6CB5E44B7F04|请求ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

http(s)://[Endpoint]/?Action=ModifyRouteEntry
&RegionId=cn-hangzhou
&RouteEntryId=rte-1234567890
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<ModifyRouteEntryResponse>
    <RequestId>861E6630-AEC0-4B2D-B214-6CB5E44B7F04</RequestId>
</ModifyRouteEntryResponse>
```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RequestId":"861E6630-AEC0-4B2D-B214-6CB5E44B7F04"
}
```

## 错误码 { .section}

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden|User not authorized to operate on the specified resource.|您没有权限操作该资源，请您申请操作权限后再试。|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

