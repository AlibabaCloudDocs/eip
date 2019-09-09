# 绑定NAT网关 {#task_593039 .task}

您可以将弹性公网IP绑定到NAT网关上。NAT网关绑定弹性公网IP后，可以使用弹性公网IP配置DNAT和SNAT条目。

1.  登录[专有网络管理控制台](https://vpcnext.console.aliyun.com)。
2.  在左侧导航栏，单击**弹性公网IP**。
3.  选择弹性公网IP的地域。
4.  在弹性公网IP页面，找到目标弹性公网IP，单击**操作**列下的**绑定**。
5.  在绑定弹性公网IP页面，完成以下配置，然后单击**确定**。 

    |配置|说明|
    |:-|:-|
    |**实例类型**|选择NAT网关。 要绑定的NAT网关必须满足以下条件：

    -   NAT网关的所属账号在2018年1月26日前没有购买过NAT带宽包。
    -   NAT网关的地域必须和EIP的地域相同。
    -   一个NAT网关最多可以绑定20个EIP。如需绑定更多的EIP，请提交工单。
 |
    |**NAT网关**|选择要绑定的NAT网关实例。|


**相关文档**  


[AssociateEipAddress](../../../../intl.zh-CN/API参考/弹性公网IP/AssociateEipAddress.md#)

