# 设置多EIP网卡可见模式 {#task_268616 .task}

多EIP网卡可见模式下，弹性网卡的私网IP和公网IP同时可用，您可以在操作系统的网卡信息中查看EIP。

设置多EIP网卡可见模式前，请确保满足以下条件：

-   辅助弹性网卡实例的地域必须和EIP的地域相同。
-   辅助弹性网卡实例的地域必须和EIP的地域相同。
-   要绑定的辅助弹性网卡未绑定任何ECS实例。

    如果已经绑定，请先解绑，在设置EIP网卡可见模式后，再绑定到ECS实例上。详细信息，请参见[分离弹性网卡](../../../../cn.zh-CN/网络/弹性网卡/分离弹性网卡.md#)。

-   在多EIP网卡可见模式下，辅助弹性网卡支持绑定10个EIP。如需提升配额，请[提交工单](https://selfservice.console.aliyun.com/ticket/createIndex.htm)

弹性公网IP本质上是一个NAT IP。由于普通模式（NAT模式）下的公网IP存在于网关设备，并不在ECS实例的网卡上，所以在操作系统内看不到公网IP，只能看到网卡上的私网IP。这样给运维带来了一定的复杂度，需要手工维护一份网卡/服务器和公网IP的对应关系。此外，EIP作为NAT ALG（NAT应用层网关）部署时，不支持如H.323、SIP、DNS、RTSP等协议。

**多EIP网卡可见模式**功能使EIP在网卡上可见，解决了上述问题。在多EIP网卡可见模式下：

-   辅助弹性网卡的私网功能仍然可用。
-   EIP在弹性网卡上可见，在操作系统配置静态IP后，可通过ifconfig或ipconfig获取网卡上的公网IP地址。
-   EIP可支持全部IP协议类型，支持FTP、H.323、SIP、DNS、RTSP、TFTP等协议。

1.  登录[专有网络管理控制台](https://vpcnext.console.aliyun.com)。
2.  在左侧导航栏，单击**弹性公网IP**。
3.  选择弹性公网IP的地域。 

    **说明：** 目前，仅华北3（张家口）、新加坡、德国（法兰克福）、印度（孟买）和英国（伦敦）地域支持设置多EIP网卡可见模式。

4.  在弹性公网IP页面，找到目标弹性公网IP，单击**操作**列下的**绑定**。
5.  在绑定弹性公网IP页面，完成以下配置，然后单击**确定**。 

    |配置|是否必选|说明|
    |--|----|--|
    |**实例类型**|是|选择**辅助弹性网卡**。|
    |**资源组**|否|选择该EIP所属的资源组。|
    |**绑定模式**|否|选择**多EIP网卡可见模式**。|
    |**辅助弹性网卡**|是|选择要绑定的辅助弹性网卡。|

    ![EIP绑定弹性网卡](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221990/156516367047675_zh-CN.png)

6.  重复以上步骤，依次绑定多个EIP到辅助弹性网卡。
7.  绑定成功后，单击绑定的弹性网卡链接。 

    ![查看绑定的弹性网卡](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/156516367033382_zh-CN.png)

8.  在弹性网卡列表页面，单击**绑定实例**将弹性网卡绑定到ECS实例上。 

    **说明：** 

    -   EIP以多EIP网卡可见模式绑定辅助弹性网卡，辅助弹性网卡绑定到ECS实例，ECS实例必须为以下实例规格族：ecs.c5-618、ecs.d1ne、ecs.db11-se1ne、ecs.ebma1、ecs.ebmc4、ecs.ebmg4、ecs.ebmg5、ecs.ebmg5ne、ecs.ebmgn5i、ecs.ebmgn5t、ecs.ebmhfg4、ecs.ebmhfg5、ecs.ebmi2、ecs.ebmi3、ecs.ebmr4、ecs.ebmr5、ecs.elmd1ne、ecs.elmdb、ecs.f1、ecs.f2、ecs.g5-618、ecs.gn3、ecs.gn5d、ecs.gn5i、ecs.gn5t、ecs.gn6p、ecs.gn6v、ecs.i2、ecs.r1、ecs.re4、ecs.re4e、ecs.sccg5、ecs.sccgn6、ecs.scch5、ecs.x1.i2、ecs.x1.i5、ecs.x1.i6、ecs.x1.i8、ecs.g5、ecs.c5、ecs.r5、ecs.t5、ecs.sn2ne、ecs.se1ne、ecs.sn1ne。详细信息，请参见[实例规格族](../../../../cn.zh-CN/实例/实例规格族.md#)。
    -   设置多EIP网卡可见模式后，辅助弹性网卡绑定的ECS实例必须开启DHCP功能，多EIP网卡可见模式才生效。
9.  调用DescribeEipGatewayInfo接口查询EIP的网关和子网掩码。详细信息，请参见[DescribeEipGatewayInfo](../../../../cn.zh-CN/API参考/弹性公网IP/DescribeEipGatewayInfo.md#)。
10. 登录ECS实例，为ECS实例配置多个EIP。详细信息，请参见[为Windows实例配置EIP地址](../../../../cn.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md#section_y4b_krk_ggb)和[为Linux实例配置EIP地址](../../../../cn.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md#section_b2x_hlb_3gb)。 

    **说明：** 参见上述链接为ECS实例配置多个EIP时，将辅助私网IP修改为EIP，将辅助私网IP的网关和掩码修改为EIP的网关和掩码。

    配置EIP地址后，您可以通过ifconfig或ipconfig命令查看配置的EIP。

11. （可选）设置多EIP网卡可见模式后，您可以测试网络连通性。详细信息，请参见[测试网络连通性](../../../../cn.zh-CN/最佳实践/普通模式下网卡多EIP.md#section_6l6_t3r_azk)。

