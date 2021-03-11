# 设置多EIP网卡可见模式

弹性公网IP EIP（Elastic IP Address）以多EIP网卡可见模式绑定辅助弹性网卡，辅助弹性网卡的私网IP和公网IP同时可用，您可以在操作系统的网卡中查看EIP信息。

开始前，请确保满足以下条件：

-   目前，多EIP网卡可见模式不再对未使用的用户开放，已公测的用户可以继续使用。
-   您已经创建了专有网络类型的辅助弹性网卡，且辅助弹性网卡的地域与EIP的地域相同。更多信息，请参见[创建弹性网卡](/intl.zh-CN/网络/弹性网卡/创建弹性网卡.md)。
-   要绑定的辅助弹性网卡未绑定任何ECS实例。

    如果已经绑定，请先解绑，在设置多EIP网卡可见模式后，再绑定到ECS实例上。更多信息，请参见[解绑弹性网卡](/intl.zh-CN/网络/弹性网卡/解绑弹性网卡.md)。


EIP本质上是一个NAT IP。由于普通模式（NAT模式）下的公网IP存在于网关设备，并不在ECS实例的网卡上，所以在操作系统内看不到公网IP，只能看到网卡上的私网IP。这种情况下，运维人员需要手工维护一份网卡与公网IP或服务器与公网IP的对应关系。此外，EIP作为普通模式部署时，不支持H.323、SIP、DNS、RTSP等协议。

**多EIP网卡可见模式**功能使EIP在网卡上可见，解决了上述问题。在多EIP网卡可见模式下：

-   辅助弹性网卡的私网功能仍然可用。
-   EIP在辅助弹性网卡上可见，在操作系统配置静态IP后，可通过ifconfig或ipconfig获取网卡上的公网IP地址。
-   EIP可支持全部IP协议类型，支持FTP、H.323、SIP、DNS、RTSP、TFTP等协议。
-   一个辅助弹性网卡支持绑定10个EIP。

1.  登录[弹性公网IP管理控制台](https://vpc.console.aliyun.com/eip)。

2.  在顶部菜单栏处，选择EIP的地域。

    **说明：** 您可以在华南1（深圳）、华东2（上海）、华北2（北京）、华北3（张家口）、西南1（成都）、新加坡、德国（法兰克福）、印度（孟买）、美国（弗吉利亚）和英国（伦敦）地域设置多EIP网卡可见模式。

3.  在**弹性公网IP**页面，找到目标EIP，单击**操作**列下的**绑定资源**。

4.  在**绑定弹性公网IP至资源**对话框，完成以下配置，然后单击**确定**。

    |配置|说明|
    |--|--|
    |**实例类型**|选择**辅助弹性网卡**。|
    |**绑定模式**|选择**多EIP网卡可见模式**。|
    |**选择要绑定的**|选择要绑定的辅助弹性网卡。|

5.  重复以上步骤，依次绑定多个EIP到辅助弹性网卡。

6.  绑定成功后，单击绑定的辅助弹性网卡链接。

    ![查看绑定的弹性网卡](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/9059039951/p33382.png)

7.  在网卡列表页面，单击**绑定实例**将弹性网卡绑定到ECS实例上。

    **说明：**

    -   EIP以多EIP网卡可见模式绑定辅助弹性网卡，辅助弹性网卡绑定到ECS实例，ECS实例必须为以下实例规格族：ecs.c5-618、ecs.d1ne、ecs.db11-se1ne、ecs.ebma1、ecs.ebmc4、ecs.ebmg4、ecs.ebmg5、ecs.ebmg5ne、ecs.ebmgn5i、ecs.ebmgn5t、ecs.ebmhfg4、ecs.ebmhfg5、ecs.ebmi2、ecs.ebmi3、ecs.ebmr4、ecs.ebmr5、ecs.elmd1ne、ecs.elmdb、ecs.f1、ecs.f2、ecs.g5-618、ecs.gn3、ecs.gn5d、ecs.gn5i、ecs.gn5t、ecs.gn6p、ecs.gn6v、ecs.i2、ecs.r1、ecs.re4、ecs.re4e、ecs.sccg5、ecs.sccgn6、ecs.scch5、ecs.x1.i2、ecs.x1.i5、ecs.x1.i6、ecs.x1.i8、ecs.g5、ecs.c5、ecs.r5、ecs.t5、ecs.sn2ne、ecs.se1ne、ecs.sn1ne。更多信息，请参见[实例规格族](/intl.zh-CN/实例/实例规格族.md)。
    -   设置多EIP网卡可见模式后，辅助弹性网卡绑定的ECS实例必须开启DHCP功能，多EIP网卡可见模式才生效。
8.  调用DescribeEipGatewayInfo接口查询EIP的网关和子网掩码。更多信息，请参见[DescribeEipGatewayInfo](/intl.zh-CN/API参考/弹性公网IP/DescribeEipGatewayInfo.md)。

9.  登录ECS实例，为ECS实例配置多个EIP。更多信息，请参见[为Windows实例配置EIP地址](/intl.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md)和[为Linux实例配置EIP地址](/intl.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md)。

    **说明：** 参见上述链接为ECS实例配置多个EIP时，将辅助私网IP修改为EIP，将辅助私网IP的网关和掩码修改为EIP的网关和掩码。

    配置EIP地址后，您可以通过ifconfig或ipconfig命令查看配置的EIP。


