# 设置EIP普通模式 {#task_268615 .task}

当弹性公网IP（EIP）绑定到一个弹性网卡实例上时，您可以选择**普通模式**。在普通模式（NAT模式）下，弹性网卡的私网IP和公网IP同时可用，EIP在弹性网卡上不可见。

-   您已经创建了弹性网卡。详细信息，请参见[创建弹性网卡](../../../../cn.zh-CN/网络/弹性网卡/创建弹性网卡.md#)。

EIP普通模式下：

-   EIP以NAT模式和弹性网卡绑定，弹性网卡的私网IP和公网IP同时可用。
-   EIP在操作系统内部不可见，需要通过DescribeEipAddresses接口查询出具体网卡上绑定的公网IP地址。详细信息，请参见[DescribeEipAddresses](../../../../cn.zh-CN/API参考/弹性公网IP/DescribeEipAddresses.md#)。
-   不支持需要做NAT ALG的协议，如H.323，SIP，DNS，RTSP，TFTP等协议。

1.  登录[专有网络管理控制台](https://vpcnext.console.aliyun.com)。
2.  在左侧导航栏，单击**弹性公网IP**。
3.  在弹性公网IP页面，选择目标EIP的所属地域。
4.  找到目标EIP，然后单击**操作**列下的**绑定**。
5.  在绑定弹性公网IP页面，完成以下配置，然后单击**确定**。 

    |配置|是否必选|说明|
    |:-|:---|:-|
    |实例类型|是|选择**辅助弹性公网IP**。|
    |资源组|否|选择该EIP所属的资源组。|
    |绑定模式|否|选择**普通模式**。|
    |辅助弹性网卡|是|选择要绑定的辅助弹性网卡。|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221988/155909975947638_zh-CN.png)


