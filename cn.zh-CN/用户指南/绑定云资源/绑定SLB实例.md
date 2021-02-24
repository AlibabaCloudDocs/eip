# 绑定SLB实例

您可以将弹性公网IP EIP（Elastic IP Address）绑定到负载均衡SLB（Server Load Balancer）实例。SLB实例绑定EIP后，SLB实例可以转发来自公网的请求。

您已经创建了SLB实例。具体操作，请参见[创建负载均衡实例](/cn.zh-CN/CLB快速入门/创建负载均衡实例.md)。

1.  登录[弹性公网IP管理控制台](https://vpc.console.aliyun.com/eip)。

2.  在顶部菜单栏处，选择EIP的地域。

3.  在**弹性公网IP**页面，找到目标EIP，单击**操作**列下的**绑定资源**。

4.  在**绑定弹性公网IP至资源**对话框，完成以下配置，然后单击**确定**。

    |配置|说明|
    |--|--|
    |**实例类型**|选择**负载均衡SLB实例**。|
    |**资源组**|选择SLB实例所属的资源组。|
    |**选择要绑定的**|选择要绑定的SLB实例。要绑定的SLB实例必须满足以下条件：

    -   SLB实例的网络类型必须是专有网络。
    -   SLB实例的地域必须和EIP的地域相同。
    -   一个SLB实例仅支持绑定一个EIP。
**说明：** 当您将私网SLB绑定至EIP时，如该实例上有私网业务流量，会发生闪断，建议在业务低谷期操作，或将业务切至其他实例后再操作。 |


**相关文档**  


[AssociateEipAddress](/cn.zh-CN/API参考/弹性公网IP/AssociateEipAddress.md)

