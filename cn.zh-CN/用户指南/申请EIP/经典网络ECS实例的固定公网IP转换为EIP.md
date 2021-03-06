---
keyword: [经典网络, 公网ip, 转换公网ip, 网络迁移, eip]
---

# 经典网络ECS实例的固定公网IP转换为EIP

手动释放经典网络类型ECS实例时，您可以将公网IP转换为弹性公网IP（Elastic IP Address，简称EIP）。EIP可绑定到专有网络VPC类型的ECS实例上，适用于网络迁移、弹性绑定、灵活升降带宽等场景。只有在手动释放实例时，才能转换经典网络公网IP为EIP，自动释放实例时，不支持转换。

经典网络公网IP转换为EIP前，请确保ECS实例满足以下要求：

-   已分配了公网IP地址。
-   所在可用区不能是中国杭州可用区C（cn-hangzhou-c）。
-   计费方式为按量付费时，实例必须处于**已停止**状态，且账号不能处于欠费状态。
-   计费方式为包年包月时，实例必须处于**已过期**或**过期回收中**状态。
-   计费方式为包年包月时，公网带宽计费方式必须是**按使用流量**计费。**按固定带宽**计费的公网带宽可以先通过升降配变更计费方式，详情请参见[升降配方式概述](/cn.zh-CN/实例/升降配实例/升降配方式概述.md)。
-   如果预约过网络迁移，不支持转换公网IP。更多信息，请参见[经典网络迁移至专有网络]()。
-   操作过实例规格变更时，请等待变更生效后再转换公网IP地址。
-   已创建快照以备份数据，防止操作失误导致数据丢失。更多信息，请参见[创建快照](/cn.zh-CN/快照/使用快照/创建一个云盘快照.md)。

经典网络公网IP转换为EIP后：

-   采用按使用流量计费方式。
-   公网带宽值和原ECS实例保持一致，您可以按需在专有网络管理控制台上升配EIP的公网带宽。但是，如果转换前经典网络类型ECS实例带宽为0Mbit/s，转换后的EIP带宽自动升级为1Mbit/s。
-   不能挂载到经典网络类型ECS实例上。
-   不同于专有网络VPC类型ECS实例，经典网络类型ECS实例具有公网网卡。如果您将经典网络公网IP转换为EIP，则无法保留该公网网卡和相应的Mac地址。

1.  登录[ECS管理控制台](https://ecs.console.aliyun.com)。

2.  在左侧导航栏，选择**实例与镜像** \> **实例**。

3.  在顶部菜单栏左上角处，选择地域。

4.  找到目标经典网络类型ECS实例，根据实例计费方式选择释放操作。

    -   释放一台包年包月实例：在**操作**列中，单击**释放**。
    -   释放一台按量付费实例：在**操作**列中，选择**更多** \> **实例状态** \> **释放设置**。
5.  选择**立即释放**，并勾选**保留经典网络公网IP并将其转换为弹性公网IP（未绑定实例的弹性公网IP会产生配置费用）**，然后单击**下一步**。

    ![保留经典网络公网IP并将其转换为弹性公网IP（未绑定实例的弹性公网IP会产生配置费用）](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6876649951/p51065.png)

6.  单击**确定**。


经典网络公网IP转换为EIP后，ECS实例会被释放，您可以在专有网络管理控制台查看新增的EIP。

![查看新增的EIP地址](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/6876649951/p51066.png)

经典网络公网IP转换为EIP后，您可以绑定EIP到ECS实例。更多信息，请参见[绑定ECS实例](/cn.zh-CN/用户指南/绑定云资源/绑定ECS实例.md)。

