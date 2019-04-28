# 设置EIP网卡可见 {#task_ajy_m5p_yfb .task}

当把弹性公网IP（EIP）绑定到一个辅助弹性网卡实例上时，您可以选择**EIP网卡可见模式**。此模式下，EIP将替换掉弹性网卡的私网IP，网卡将变为一个纯公网网卡，可以在操作系统的网卡信息中查看到。

-   已经创建了弹性网卡。详细说明，请参见[创建弹性网卡](../../../../intl.zh-CN/网络/弹性网卡/创建弹性网卡.md#)。

-   要绑定的弹性网卡未绑定任何ECS实例。

    如果已经绑定，请先解绑，在设置EIP网卡可见模式后，再绑定到ECS实例上。详细说明，请参见[分离弹性网卡](../../../../intl.zh-CN/网络/弹性网卡/分离弹性网卡.md#)。

-   您申请的EIP为后付费类型的EIP，预付费类型的EIP不支持网卡可见功能。


弹性公网IP本质上是一个NAT IP。由于NAT模式下的公网IP存在于网关设备，并不在ECS实例的网卡上，所以在操作系统内看不到公网IP，只能看到网卡上的私网IP。这样给运维带来了一定的复杂度，需要手工维护一份网卡/服务器和公网IP的对应关系。此外，EIP作为NAT ALG（NAT应用层网关）部署时，不支持如H.323、SIP、DNS、RTSP等协议。

**EIP网卡可见模式**功能使EIP在网卡上可见，解决了上述问题。在EIP网卡可见模式下：

-   EIP会替换掉弹性网卡的私网IP，网卡将变为一个纯公网网卡，私网功能不再可用。
-   EIP在操作系统内部的弹性网卡上可见，可直接通过ifconfig/ipconfig获取网卡上的公网IP地址。
-   EIP可支持全部IP协议类型，支持FTP、H.323、SIP、DNS、RTSP、TFTP等协议。

1.  登录[专有网络控制台](https://vpcnext.console.aliyun.com)。
2.  在左侧导航栏，单击**弹性公网IP**，然后选择EIP的所属地域。
3.  找到目标EIP，然后单击**绑定**。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155641702633373_zh-CN.png)

4.  在弹出的页面，完成以下操作： 
    1.  **实例类型**：选择**辅助弹性网卡**。
    2.  **资源组**：选择该EIP所属的资源组。
    3.  **绑定模式**：选择**EIP网卡可见模式**。
    4.  **辅助弹性网卡**：选择要绑定的弹性网卡。 

        **说明：** 确保选择的弹性网卡未绑定ECS实例。

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155641702633380_zh-CN.png)

5.  绑定成功后，单击绑定的弹性网卡链接。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155641702733382_zh-CN.png)

6.  在弹性网卡列表页面，单击**绑定实例**将弹性网卡绑定到ECS实例上。 

    **说明：** 设置EIP网卡可见模式后，辅助弹性网卡绑定的ECS实例必须开启DHCP功能，EIP网卡可见模式才生效。

7.  使用绑定的EIP登录ECS实例，查看该实例的网络配置。 

    **说明：** 确保ECS实例的安全组配置允许远程访问。

    您可以看到该实例的本地IP地址已经变成了EIP的地址。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155641702733443_zh-CN.png)


