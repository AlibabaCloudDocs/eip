# ReleaseEipAddress

调用ReleaseEipAddress接口释放指定的弹性公网IP（EIP）。

## API描述

释放EIP前，请确保满足以下条件：

-   只有处于**Available**状态的EIP才可以被释放。
-   仅按量计费类型的EIP支持释放，包年包月类型的EIP不支持释放。

## 调试

[您可以在OpenAPI Explorer中直接运行该接口，免去您计算签名的困扰。运行成功后，OpenAPI Explorer可以自动生成SDK代码示例。](https://api.aliyun.com/#product=Vpc&api=ReleaseEipAddress&type=RPC&version=2016-04-28)

## 请求参数

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|Action|String|是|ReleaseEipAddress|要执行的操作，取值：**ReleaseEipAddress**。 |
|AllocationId|String|是|eip-2zeerraiwb7uj6i0d\*\*\*\*|要释放的EIP的ID。 |
|RegionId|String|是|cn-hangzhou|要释放的EIP所在的地域ID。您可以通过调用[DescribeRegions](~~36063~~)接口获取地域ID。 |

## 返回数据

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|748C38F6-9A3D-482E-83FB-DB6C39C68AEA|请求ID。 |

## 示例

请求示例

```
http(s)://[Endpoint]/?Action=ReleaseEipAddress
&AllocationId=eip-2zeerraiwb7uj6i0d****
&<公共请求参数>
```

正常返回示例

`XML`格式

```
<ReleaseEipAddressResponse>
      <RequestId>748C38F6-9A3D-482E-83FB-DB6C39C68AEA</RequestId>
</ReleaseEipAddressResponse>
```

`JSON`格式

```
{
  "RequestId": "748C38F6-9A3D-482E-83FB-DB6C39C68AEA"
}
```

## 错误码

|HttpCode|错误码|错误信息|描述|
|--------|---|----|--|
|404|InvalidAllocationId.NotFound|Specified allocation ID is not found|指定的公网 IP 不存在，请您检查您填写的参数是否正确。|
|400|IncorrectEipStatus|Current elastic IP status does not support this operation.|指定的EIP状态不支持此操作。|
|500|InternalError|The request processing has failed due to some unknown error.|请求处理由于某些未知错误失败。|
|404|Forbidden.RegionNotFound|Specified region is not found during access authentication.|指定 Region 不存在，请您检查该 Region 是否正确。|
|400|Forbidden.ChargeTypeIsPrepaid|It's forbidden to release a prepaid EIP|预付费的 EIP 实例不能释放。|
|400|Forbbiden|The eip instance owener error|EIP 不属于当前调用者，请您检查该 EIP 是否可被您调用。|
|400|TaskConflict.AssociateGlobalAccelerationInstance|Operate too frequent.|操作过于频繁。|

访问[错误中心](https://error-center.aliyun.com/status/product/Vpc)查看更多错误码。

