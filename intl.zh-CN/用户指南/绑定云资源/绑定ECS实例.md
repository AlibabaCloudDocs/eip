# 绑定ECS实例

您可以将弹性公网IP EIP（Elastic IP Address）绑定到专有网络类型的ECS实例上。ECS实例绑定EIP后，ECS实例可以和公网通信。

您已经创建了ECS实例。具体操作，请参见[使用向导创建实例](/intl.zh-CN/实例/创建实例/使用向导创建实例.md)。

1.  登录[弹性公网IP管理控制台](https://vpc.console.aliyun.com/eip)。

2.  在顶部菜单栏处，选择EIP的地域。

3.  在**弹性公网IP**页面，找到目标EIP，单击**操作**列下的**绑定资源**。

4.  在**绑定弹性公网IP至资源**对话框，完成以下配置，然后单击**确定**。

    |配置|说明|
    |--|--|
    |**实例类型**|选择**云服务器ECS实例**。|
    |**绑定模式**|选择EIP绑定ECS实例的绑定模式。目前，仅支持普通模式。在普通模式下：

    -   EIP以NAT模式和ECS实例绑定，ECS实例的私网IP地址和公网IP地址同时可用。
    -   EIP在操作系统内部不可见，需要通过DescribeInstances接口查询ECS实例绑定的公网IP地址。更多信息，请参见[DescribeInstances](/intl.zh-CN/API参考/实例/DescribeInstances.md)。
    -   不支持做NAT ALG的协议，例如H.323、SIP、DNS、RTSP、TFTP等协议。 |
    |**选择要绑定的**|选择要绑定的ECS实例。要绑定的ECS实例必须满足以下条件：

    -   ECS实例的网络类型必须是专有网络。
    -   ECS实例必须处于运行中或停止状态。
    -   一个ECS实例只能绑定一个EIP。
    -   ECS实例的地域必须和要绑定的EIP的地域相同。
    -   ECS实例没有配置固定公网IP且没有绑定其他EIP。 |


**相关文档**  


[AssociateEipAddress](/intl.zh-CN/API参考/弹性公网IP/AssociateEipAddress.md)

