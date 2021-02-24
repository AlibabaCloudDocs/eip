# AllocateEipSegmentAddress

调用AllocateEipSegmentAddress申请连续EIP。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=AllocateEipSegmentAddress&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|AllocateEipSegmentAddress|要执行的操作，取值：**AllocateEipSegmentAddress**。 |
|EipMask|String|是|28|连续EIP的掩码，取值：

-   **28**：单次调用，系统将分配16个连续EIP。
-   **27**：单次调用，系统将分配32个连续EIP。
-   **26**：单次调用，系统将分配64个连续EIP。
-   **25**：单次调用，系统将分配128个连续EIP。
-   **24**：单次调用，系统将分配256个连续EIP。

**说明：** 由于IP地址保留，实际申请到的连续EIP可能缺少1、3或者4个EIP。 |
|RegionId|String|是|cn-hangzhou|连续EIP所属的地域ID。可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |
|ClientToken|String|否|02fb3da4-130e-11e9-8e44-001\*\*\*\*|保证请求幂等性。从您的客户端生成一个参数值，确保不同请求间该参数值唯一。ClientToken只支持ASCII字符，且不能超过64个字符。 |
|Bandwidth|String|否|5|EIP的带宽峰值，单位为Mbps，默认值为**5** Mbps。 |
|Netmode|String|否|public|网络类型，取值：

-   **public**（默认）：公网。连续EIP和云资源绑定后，云资源可以通过EIP与公网通信。
-   **hybrid**：混合云。连续EIP和云资源绑定后，云资源可以通过EIP进行混合云通信。

**说明：** 仅具有混合云白名单的用户支持选择混合云类型，如需使用，请联系您的客户经理。 |
|InternetChargeType|String|否|PayByBandwidth|连续EIP的计费方式，取值：

-   **PayByBandwidth**（默认值）：按带宽计费。
-   **PayByTraffic**：按流量计费。

**说明：** 如果**Netmode**取值为**hybrid**时，**InternetChargeType**仅支持取值为**PayByBandwidth**。 |
|ResourceGroupId|String|否|rg-bp67acfmxazb4ph\*\*\*\*|资源组ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|EipSegmentInstanceId|String|eipsg-2zett8ba055tbsxme\*\*\*\*|连续EIP组的实例ID。 |
|OrderId|Long|20190000|订单ID。 |
|RequestId|String|F7A6301A-64BA-41EC-8284-8F4838C15D1F|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=AllocateEipSegmentAddress
&EipMask=28
&RegionId=cn-hangzhou
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<AllocateEipSegmentAddressResponse>
      <RequestId>F7A6301A-64BA-41EC-8284-8F4838C15D1F</RequestId>
      <EipSegmentInstanceId>eipsg-2zett8ba055tbsxme****</EipSegmentInstanceId>
      <OrderId>20190000</OrderId>
</AllocateEipSegmentAddressResponse>
```

`JSON`格式

```
{
    "RequestId":"F7A6301A-64BA-41EC-8284-8F4838C15D1F",
    "EipSegmentInstanceId":"eipsg-2zett8ba055tbsxme****",
    "OrderId":"20190000"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|403|Forbbiden|User not authorized to operate on the specified resource.|您没有权限操作该资源，请您申请操作权限后再试。|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded|弹性公网 IP 的个数超过额度限制，如果您有更多额度的需求，请提交工单申请增加限额，建议您考虑使用NAT网关。|
|400|InvalidParameter|Specified value of "InternetChargeType" is not valid|参数InternetChargeType的值不合法。|
|400|InvalidParameter|Specified value of "Bandwidth" is not valid.|该带宽不合法。|
|400|InsufficientBalance|Your account does not have enough balance.|账户余额不足，请先充值再操作。|
|400|QuotaExceeded.Eip|Elastic IP address quota exceeded.|弹性公网 IP 的个数超过额度限制，如果您有更多额度的需求，请提交工单申请增加限额，建议您考虑使用NAT网关。|
|400|ReserveIpFail|Reserve eip failed.|EIP预留失败。|
|400|InvalidRegion.NotSupport|The specified region does not support.|该 RegionId 不支持此操作。|
|400|InvalidResourceGroupId|The specified ResourceGroupId does not exist.|资源组ID不存在。|
|409|OperationConflict|Request was denied due to conflict with a previos request.|请求冲突，稍等一段时间重试，或者提交工单反馈。|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

