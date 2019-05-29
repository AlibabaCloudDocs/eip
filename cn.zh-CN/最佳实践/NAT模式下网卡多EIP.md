# NAT模式下网卡多EIP {#concept_269613 .concept}

在NAT模式下，您可以将多个EIP绑定到一个辅助弹性网卡。辅助弹性网卡绑定多个EIP，可以实现流量转移，提高ECS实例的利用率。

## 前提条件 {#section_c2k_9h5_mbp .section}

NAT模式（普通模式）下，多个EIP绑定一个辅助弹性网卡需要满足以下条件。

-   您需要提交工单。在NAT模式下，申请多个EIP绑定一个辅助弹性网卡的权限。
-   您已经创建了ECS实例。详细信息，请参见[使用向导创建实例](../../../../cn.zh-CN/实例/创建实例/使用向导创建实例.md#)。
-   您已经创建了辅助弹性网卡。详细信息，请参见[创建弹性网卡](../../../../cn.zh-CN/网络/弹性网卡/创建弹性网卡.md#)。

## 使用限制 {#section_n30_2j0_2cd .section}

目前仅华北2（北京）、华北3（张家口）、新加坡、德国（法兰克福）、印度（孟买）地域支持在NAT模式下设置网卡多EIP。

## 步骤一 分配多个辅助私网IP {#section_nbm_39r_jyz .section}

完成以下操作，为辅助弹性网卡分配多个辅助私网IP。

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com/#/home)。
2.  在左侧导航栏中，单击**网络和安全** \> **弹性网卡**。
3.  在网卡列表页面，选择弹性网卡所属的地域。
4.  找到目标弹性网卡，单击**操作**列下的**管理辅助私网IP**。
5.  在管理辅助私网IP页面，连续单击**分配新IP**，分配多个辅助私网IP地址。

    **说明：** 您可以手动输入辅助私网IP地址，取值在**IPv4私网网段**内即可。如果您不输入IP值，系统会从**IPv4私网网段**随机分配IP地址。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83258/155910005847047_zh-CN.png)

6.  单击**修改**。

## 步骤二 绑定EIP到网卡的主/辅助私网IP {#section_nom_quj_d1f .section}

完成以下操作，将EIP绑定到辅助弹性网卡的主私网IP和辅助私网IP上。

1.  登录[阿里云OpenAPI Explorer](https://api.aliyun.com)。
2.  在左侧导航栏中，单击**专有网络**。
3.  在搜索框中搜索**AssociateEipAddress**，然后单击**AssociateEipAddress**。
4.  根据以下信息，配置AssociateEipAddress参数，然后单击**发起调用**。
    -   **RegionId**：EIP所属的地域ID。
    -   **InstanceId**：要绑定的实例ID，本示例输入辅助弹性网卡的实例ID。
    -   **AllocationId**：EIP的ID。
    -   **InstanceType**：要绑定的云产品实例的类型。本示例输入NetworkInterface。
    -   **InstanceRegionId**（可选）：要绑定的实例所属的地域ID，本示例输入辅助弹性网卡所属的实例ID。
    -   **PrivateIpAddress**：输入分配的辅助弹性网卡的主私网IP或辅助私网IP。
    -   **Mode**：绑定模式，本示例输入NAT。
5.  重复上述步骤，将多个EIP依次绑定到辅助弹性网卡的主私网IP和辅助私网IP上。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222560/155910005847718_zh-CN.png)


## 步骤三 附加弹性网卡到ECS实例 {#section_lgd_nts_85o .section}

将EIP绑定到辅助弹性网卡的主私网IP和辅助私网IP后，您需要附加弹性网卡到ECS实例上。详细信息，请参见[为已有实例绑定弹性网卡](../../../../cn.zh-CN/网络/弹性网卡/绑定弹性网卡.md#section_bwf_mqs_lgb)。

## 步骤四 配置辅助私网IP地址 {#section_h3w_i8m_svn .section}

附加弹性网卡到ECS实例后，您需要为ECS实例配置辅助私网IP地址。详细信息，请参见[为Windows实例配置辅助私网IP地址](../../../../cn.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md#section_y4b_krk_ggb)和[为Linux实例配置辅助私网IP地址](../../../../cn.zh-CN/网络/弹性网卡/分配辅助私网IP地址.md#section_b2x_hlb_3gb)。

**说明：** 为ECS实例配置辅助私网IP地址需要获取私网IP的网关和子网掩码。详细信息，请参加[获取实例元数据](../../../../cn.zh-CN/实例/管理实例/使用实例元数据/获取实例元数据.md#)。

配置辅助私网IP地址后，您可以通过ip address命令查看配置的辅助私网IP地址。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222560/155910005847722_zh-CN.png)

