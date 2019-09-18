# 普通模式下网卡多EIP {#concept_269613 .concept}

在EIP绑定辅助弹性网卡的普通模式下，您可以将多个EIP绑定到一个辅助弹性网卡。辅助弹性网卡绑定多个EIP，可以实现流量转移，提高ECS实例的利用率。

## 前提条件 {#section_c2k_9h5_mbp .section}

在EIP绑定辅助弹性网卡的普通模式（NAT模式）下，多个EIP绑定一个辅助弹性网卡需要满足以下条件：

-   您已经创建了ECS实例。详细信息，请参见[使用向导创建实例](../../../../intl.zh-CN/实例/创建实例/使用向导创建实例.md#)。
-   您已经创建了辅助弹性网卡。详细信息，请参见[创建弹性网卡](../../../../intl.zh-CN/网络/弹性网卡/创建弹性网卡.md#)。

## 步骤一 分配多个辅助私网IP {#section_nbm_39r_jyz .section}

完成以下操作，为辅助弹性网卡分配多个辅助私网IP。

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com/#/home)。
2.  在左侧导航栏中，单击**网络和安全** \> **弹性网卡**。
3.  在网卡列表页面，选择弹性网卡所属的地域。
4.  找到目标弹性网卡，单击**操作**列下的**管理辅助私网IP**。
5.  在管理辅助私网IP页面，连续单击**分配新IP**，分配多个辅助私网IP。

    **说明：** 您可以手动输入辅助私网IP，取值在**IPv4私网网段**内即可。如果您不输入IP值，系统会从**IPv4私网网段**随机分配IP。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83258/156876973147047_zh-CN.png)

6.  单击**修改**。

## 步骤二 将EIP绑定到辅助私网IP {#section_nom_quj_d1f .section}

完成以下操作，将EIP绑定到辅助弹性网卡的辅助私网IP上。

1.  登录[专有网络管理控制台](https://vpcnext.console.aliyun.com)。
2.  在左侧导航栏，单击**弹性公网IP**。
3.  选择弹性公网IP的地域。
4.  在弹性公网IP页面，找到目标弹性公网IP，单击**操作**列下的**绑定**。
5.  在绑定弹性公网IP页面，完成以下配置，然后单击**确定**。
    -   **实例类型**：选择**辅助弹性网卡**。
    -   **资源组**：选择该EIP所属的资源组。
    -   **绑定模式**：选择**普通模式**。
    -   **辅助弹性网卡**：选择要绑定的辅助私网IP。
6.  重复上述步骤，将多个EIP分别绑定到一个辅助弹性网卡的辅助私网IP上。

## 步骤三 将弹性网卡绑定到ECS实例 {#section_lgd_nts_85o .section}

将EIP绑定到辅助弹性网卡的辅助私网IP后，您需要绑定弹性网卡到ECS实例上。详细信息，请参见[为已有实例绑定弹性网卡](../../../../intl.zh-CN/网络/弹性网卡/绑定弹性网卡.md#section_bwf_mqs_lgb)。

## 步骤四 配置辅助私网IP {#section_h3w_i8m_svn .section}

绑定弹性网卡到ECS实例后，您需要为ECS实例配置辅助私网IP。详细信息，请参见[为Windows实例配置辅助私网IP地址](../../../../intl.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md#section_y4b_krk_ggb)和[为Linux实例配置辅助私网IP地址](../../../../intl.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md#section_b2x_hlb_3gb)。

**说明：** 为ECS实例配置辅助私网IP需要获取私网IP的网关和子网掩码。详细信息，请参见[获取实例元数据](../../../../intl.zh-CN/实例/管理实例/使用实例元数据/获取实例元数据.md#)。

配置辅助私网IP后，您可以通过ip address命令查看配置的辅助私网IP。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222560/156876973147722_zh-CN.png)

## 步骤五 测试网络连通性 {#section_6l6_t3r_azk .section}

完成以下步骤，测试ECS实例的网络连通性。本操作以在Linux实例配置eth1网卡的静态路由为例。

1.  登录ECS实例。
2.  执行`/sbin/iproute add <目的网络>/<子网前缀长度> via <辅助私网IP的网关> eth1 src <辅助私网IP>`，配置eth1网卡的静态路由。
3.  执行`ping <目的网络> -I <辅助私网IP>`，验证辅助私网IP到目的网络的连通性。

    若检测网络可达，即EIP绑定辅助私网IP生效。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222560/156876973149832_zh-CN.png)


