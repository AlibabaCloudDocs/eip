# 绑定NAT网关

您可以将弹性公网IP EIP（Elastic IP Address）绑定到NAT网关上。NAT网关绑定EIP后，可以使用EIP配置DNAT和SNAT条目。

您已经创建了NAT网关。更多信息，请参见[创建NAT网关]()。

1.  登录[弹性公网IP管理控制台](https://vpc.console.aliyun.com/eip)。

2.  在顶部菜单栏处，选择弹性公网IP的地域。

3.  在**弹性公网IP**页面，找到目标弹性公网IP，单击**操作**列下的**绑定资源**。

4.  在**绑定弹性公网IP至资源**对话框，完成以下配置，然后单击**确定**。

    |配置|说明|
    |--|--|
    |**实例类型**|选择**NAT网关**。|
    |**选择要绑定的**|选择要绑定的NAT网关实例。要绑定的NAT网关实例必须满足以下条件：

    -   NAT网关所属的账号在2018年1月26日前没有购买过NAT带宽包。如有购买，请使用NAT带宽包绑定NAT网关。
    -   NAT网关的地域必须和EIP的地域相同。
    -   一个NAT网关最多可以绑定20个EIP，其中最多支持绑定10个按使用流量计费的EIP。如需绑定更多的EIP，请提升配额。更多信息，请参见[管理配额](/intl.zh-CN/用户指南/管理配额.md)。 |


**相关文档**  


[AssociateEipAddress](/intl.zh-CN/API参考/弹性公网IP/AssociateEipAddress.md)

