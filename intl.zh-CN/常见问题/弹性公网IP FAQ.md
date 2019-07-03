# 弹性公网IP FAQ {#concept_o35_55m_vdb .concept}

弹性公网IP（EIP）的常见问题和解答。

-   一般性问题
    -   [什么EIP？](#section_qzu_vp2_jki)
    -   [EIP有什么优势？](#section_mgn_p84_nly)
    -   [EIP与ECS公网IP有什么区别？](#section_dfd_cvm_vdb)
    -   [为什么申请EIP时提示：eip frequent purchase？](#section_n0q_mn4_66y)
    -   [为什么无法访问EIP？](#section_v69_jpi_fxd)
    -   [新申请的EIP的分配策略是什么？](#section_7qp_8nq_isj)
-   预付费EIP FAQ
    -   [\#section\_owz\_hcc\_124](#section_owz_hcc_124)
    -   [\#section\_bue\_yuk\_t6s](#section_bue_yuk_t6s)
-   后付费EIP FAQ
    -   [已经释放了后付费EIP，为什么还会产生费用？](#section_1nh_ax9_e2l)
    -   [为什么要为后付费-按流量计费的EIP设置带宽峰值？](#section_am7_sfw_w5y)
    -   [\#section\_wba\_mrz\_6hb](#section_wba_mrz_6hb)
    -   [\#section\_sar\_kti\_nbs](#section_sar_kti_nbs)
-   EIP限制FAQ
    -   [一个账号可以申请多少个EIP？](#section_hrm_9q9_8fg)
    -   [一个EIP同时能绑定多个云资源吗？](#section_12o_yti_nld)
    -   [EIP的API调用次数有限制吗？](#section_r68_ghp_dft)
-   绑定EIP FAQ
    -   [EIP可以绑定到哪些云资源？](#section_274_5mv_ycx)
    -   [为什么EIP无法绑定到NAT网关上？](#section_6st_c7i_glg)
    -   [为什么EIP无法绑定到ECS实例上？](#section_49i_4mq_g42)
    -   [EIP绑定ECS实例后，为什么在ECS网卡上看不到EIP？](#section_rd3_w5m_vdb)

## 什么是EIP？ {#section_qzu_vp2_jki .section}

EIP是可以独立购买和持有的公网IP地址资源。目前，EIP可绑定到ECS实例、私网SLB实例、辅助弹性网卡、NAT网关和高可用虚拟IP上（ECS实例、私网SLB实例和辅助弹性网卡必须为专有网络类型）。

EIP是一种NAT IP，它实际位于阿里云的公网网关上，通过NAT方式映射到了被绑定的云资源上。和云资源绑定后，云资源可以通过EIP与公网通信。

## EIP有什么优势？ {#section_mgn_p84_nly .section}

EIP的优势如下：

-   独立购买与持有

    您可以单独持有一个EIP，作为您账户下一个独立的资源存在，无需与其它计算资源或存储资源绑定购买。

-   弹性绑定

    您可以在需要时将EIP绑定到云资源上；在不需要时，将EIP解绑并释放，避免不必要的计费。

-   可配置的网络能力

    您可以根据需要随时调整EIP的带宽值，带宽的修改即时生效。


## EIP与ECS公网IP有什么区别？ {#section_dfd_cvm_vdb .section}

EIP与ECS公网IP的区别如下表：

|比较点|EIP|ECS公网IP|
|:--|:--|:------|
|支持的网络环境|专有网络|专有网络和经典网络|
|是否能够单独持有|支持|不支持|
|是否支持在ECS上的弹性插拔|支持|不支持|
|ECS实例网卡上是否能看到该IP|**EIP网卡可见模式**和**多EIP网卡可见模式**下可见| 经典网络：能看到

 专有网络VPC：看不到

 |

## 为什么申请EIP时提示：eip frequent purchase？ {#section_n0q_mn4_66y .section}

原因：阿里云识别您在近期出现频繁申请并更换EIP的行为，已触发阿里云非正常购买行为安全告警，阿里云将暂时限制您的EIP购买权限。

解决方法：请确保未来一周内申请EIP的个数不超过您账户允许保有的最大EIP个数，EIP购买权限可在一周后自动恢复。关于如何查看账户可保有的eip个数，请参见[管理配额](../../../../intl.zh-CN/用户指南/管理配额.md#)。

## 为什么无法访问EIP？ {#section_v69_jpi_fxd .section}

无法访问EIP的原因如下：

-   EIP没有绑定到云资源。
-   ECS实例配置了安全策略。例如ECS实例所在的安全组策略禁止80端口的访问，则无法访问该EIP的80端口。
-   EIP已经欠费。

## 新申请的EIP的分配策略是什么？ {#section_7qp_8nq_isj .section}

默认是随机分配EIP，但对于频繁申请又释放的用户，会优先分配之前使用过的EIP。

## 已经释放了后付费EIP，为什么还会产生费用？ {#section_1nh_ax9_e2l .section}

对于后付费的EIP，账单是在下一个小时产生。您会在释放EIP后收到账单，但其实已经停止了计费。例如：

一个按使用流量计费的EIP实例，如果您在10：30释放EIP实例，那么您在释放后会收到10点到11点的流量费的账单。

## 为什么要为后付费-按流量计费的EIP设置带宽峰值？ {#section_am7_sfw_w5y .section}

对于后付费-按流量计费的EIP，可以通过设置带宽峰值避免产生过多的出方向流量，以达到控制成本的目的。

后付费-按流量计费的EIP实例的带宽峰值不提供任何服务质量承诺。例如一个按流量计费的EIP的带宽峰值设置为200Mbps，不承诺带宽峰值一定可以达到200Mbps。如果希望使用有服务质量承诺的带宽峰值，您需要购买按带宽计费的EIP或共享带宽。

## 一个账号可以申请多少个EIP？ {#section_hrm_9q9_8fg .section}

一个账号最多可以申请20个EIP。如需申请更多EIP，请提交工单。

## 一个EIP同时能绑定多个云资源吗？ {#section_12o_yti_nld .section}

不能，一个EIP同时只能绑定一个云资源。

## EIP的API调用次数有限制吗？ {#section_r68_ghp_dft .section}

有限制，如果对EIP的API调用次数过于频繁会触发API调用次数限速。每用户每天调用API的次数如果大于500就会触发API限速。

## EIP可以绑定到哪些云资源？ {#section_274_5mv_ycx .section}

目前，EIP支持绑定到专有网络类型的ECS实例、专有网络类型的私网SLB实例、专有网络类型的辅助弹性网卡、NAT网关和高可用虚拟IP上。

## 为什么EIP无法绑定到NAT网关上？ {#section_6st_c7i_glg .section}

对于2018年1月26日之前账号下存在NAT带宽包的用户，您仍需使用NAT带宽包为该NAT网关提供公网IP。如需绑定EIP，请提交工单。

## 为什么EIP无法绑定到ECS实例上？ {#section_49i_4mq_g42 .section}

EIP无法绑定到ECS实例的原因如下：

-   EIP只能绑定到专有网络类型的ECS实例上。如果您当前的ECS实例不是专有网络类型，则无法绑定。
-   EIP的地域和ECS实例的地域不同。
-   只有运行中或者已停止状态的ECS实例才能绑定EIP。
-   该ECS实例已经分配了公网IP或绑定了其他EIP。

## EIP绑定ECS实例后，为什么在ECS网卡上看不到EIP？ {#section_rd3_w5m_vdb .section}

EIP配置在Internet网关设备上，通过NAT方式映射到了ECS实例的私网网卡，所以在ECS实例的私网网卡上无法查看到EIP。

当EIP绑定到一个辅助弹性网卡上时，您可以选择EIP网卡可见模式和多EIP网卡可见模式。

-   EIP网卡可见模式

    此模式下，EIP替换辅助弹性网卡的私网IP，辅助弹性网卡将变为一个纯公网网卡，私网功能不再可用。EIP在操作系统内部的弹性网卡上可见，可直接通过ifconfig或ipconfig获取网卡上的公网IP地址。详细信息，请参见[设置EIP网卡可见模式](../../../../intl.zh-CN/用户指南/绑定云资源/绑定辅助弹性网卡/设置EIP网卡可见模式.md#)。

-   多EIP网卡可见模式

    此模式下，辅助弹性网卡的私网功能仍然可用。EIP在弹性网卡上可见，在操作系统配置静态IP后，可通过ifconfig或ipconfig获取网卡上的公网IP地址。详细信息，请参见[设置多EIP网卡可见模式](../../../../intl.zh-CN/用户指南/绑定云资源/绑定辅助弹性网卡/设置多EIP网卡可见模式.md#)。


