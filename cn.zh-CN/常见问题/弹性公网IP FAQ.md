# 弹性公网IP FAQ {#concept_o35_55m_vdb .concept}

弹性公网IP（EIP）的常见问题和解答。

-   [EIP与ECS的公网IP有何区别？](#section_dfd_cvm_vdb)
-   [为什么在ECS网卡上看不到EIP？](#section_rd3_w5m_vdb)
-   [一个账号可以申请多少个EIP？](#section_sd3_w5m_vdb)
-   [EIP当前可以绑定到哪些云产品？](#section_td3_w5m_vdb)
-   [EIP是否支持绑在经典网络的ECS实例上？](#section_ud3_w5m_vdb)
-   [为什么无法访问EIP？](#section_wd3_w5m_vdb)
-   [为什么EIP无法绑定到ECS实例上？](#section_gk4_fvm_vdb)
-   [为什么EIP无法绑定到NAT网关上？](#section_a23_w5m_vdb)
-   [EIP支持按流量和按带宽互相切换吗？](#section_s5w_mrf_qgb)
-   [已经删除了EIP，为什么还会产生费用？](#section_wsh_44g_qgb)
-   [EIP实例占用费的收费策略是什么？](#section_v1d_jpg_qgb)
-   [按流量计费的EIP设置了带宽峰值有什么用？](#section_xry_qqg_qgb)
-   [EIP支持从后付费类型转换为预付费吗？](#section_uwq_1rg_qgb)
-   [EIP的API调用次数有限制吗？](#section_h4q_1sg_qgb)
-   [预付费类型的EIP支持批量续费吗？](#section_jz4_btg_qgb)
-   [新申请的EIP的分配策略是什么样的？](#section_xkm_2tg_qgb)

## EIP与ECS的公网IP有何区别？ {#section_dfd_cvm_vdb .section}

-   公网IP可以在ECS实例的网卡上看到， 而EIP是通过NAT方式将IP地址映射到ECS的位于私网的网卡上，所以在网卡上看不到EIP。

-   公网IP不可以与ECS实例解绑，而EIP可以随时解绑和绑定。

    您可以将ECS的固定公网IP转换为EIP，详情参见[ECS固定公网IP转换为EIP](../../../../../cn.zh-CN/用户指南/ECS固定公网IP转换为EIP.md#)。


## 为什么在ECS网卡上看不到EIP？ {#section_rd3_w5m_vdb .section}

EIP配置在Internet网关设备上，通过NAT方式映射到了ECS实例的私网网卡，所以在ECS实例的私网网卡上无法查看到EIP。

当把弹性公网IP（EIP）绑定到一个弹性辅助网卡实例上时，您可以选择 EIP网卡可见模式 。此模式下，EIP将替换掉弹性网卡的私网IP，网卡将变为一个纯公网网卡，可以在操作系统的网卡信息中查看到。配置说明，请参见[设置EIP网卡可见](../../../../../cn.zh-CN/用户指南/设置EIP网卡可见.md#)。

## 一个账号可以申请多少个EIP？ {#section_sd3_w5m_vdb .section}

一个账号最多可以申请20个EIP。如果您需更多EIP，可以提交工单申请。

## EIP当前可以绑定到哪些云产品？ {#section_td3_w5m_vdb .section}

目前支持绑定EIP的云产品实例包括专有网络类型的ECS和SLB实例、弹性网卡和NAT网关。

## EIP是否支持绑在经典网络的ECS实例上？ {#section_ud3_w5m_vdb .section}

不支持。

## 为什么无法访问EIP？ {#section_wd3_w5m_vdb .section}

可能原因如下：

-   EIP没有绑定到云产品实例上。
-   查看ECS实例是否有安全策略。例如ECS实例所在的安全组策略禁止80端口的访问，则无法访问该EIP的80端口。
-   您的EIP已经欠费。

## 为什么EIP无法绑定到ECS实例上？ {#section_gk4_fvm_vdb .section}

可能原因如下：

-   EIP只能绑定到专有网络类型的ECS实例上。如果您当前的ECS实例不是专有网络类型的，则无法绑定。
-   EIP的地域和ECS实例的地域不同。
-   只有运行中或者已停止状态的ECS实例才能绑定EIP。
-   该ECS实例已经绑定了EIP。
-   该ECS实例已经分配了公网IP。

## 为什么EIP无法绑定到NAT网关上？ {#section_a23_w5m_vdb .section}

对于2017年11月3日之前账号下存在NAT带宽包的用户，您仍需使用NAT带宽包为该NAT网关提供公网IP。若要绑定EIP，请提交工单。

## EIP支持按流量和按带宽互相切换吗？ {#section_s5w_mrf_qgb .section}

支持。

但计费类型的切换需要在操作后的第二天零点生效，在生效期间不支持变配带宽峰值。如果必须要变配带宽峰值，可取消计费类型变更，将待生效的订单取消后再做变配带宽峰值操作。操作说明，请参见[取消未生效订单](../../../../../cn.zh-CN/用户指南/取消未生效订单.md#)。

## 已经删除了EIP，为什么还会产生费用？ {#section_wsh_44g_qgb .section}

对于后付费的EIP，账单是在下一个小时或下一天产生。您会在删除EIP后收到账单，但其实已经停止了计费。例如：

-   一个按流量计费的EIP实例，如果您在10：30删除EIP实例，那么您会在删除后会收到10点到11点的流量费的账单。
-   对于按带宽计费的EIP实例，如果您在2019-01-01删除EIP实例，那么您在删除后会收到2019-01-01到2019-01-02的的账单。

## EIP实例占用费的收费策略是什么？ {#section_v1d_jpg_qgb .section}

实例占用费与EIP绑定的资源和配额有关：

-   对于默认20个配额以内的EIP实例，如果EIP绑定ECS实例，则不收取实例占用费。
-   对于绑定非ECS的其他类型的云产品，包括但不限于NAT网关、SLB负载均衡和弹性网卡都会收实例占用费。
-   不管是按带宽计费还是按流量计费，单个EIP的实例费都是0.02元/小时。
-   EIP实例占用费和EIP是否加入共享带宽无关。

## 按流量计费的EIP设置了带宽峰值有什么用？ {#section_xry_qqg_qgb .section}

对于按流量计费的EIP，可以通过设置带宽峰值避免产生过多的出方向流量以达到控制成本的目的。

按流量计费的EIP实例的带宽峰值不提供任何服务质量承诺。例如一个按流量计费的EIP的带宽峰值设置为200Mbps，不承诺带宽峰值一定可以达到200Mbps。如果希望使用有服务质量承诺的带宽峰值，需要购买按带宽计费的EIP或共享带宽。

## EIP支持从后付费类型转换为预付费吗？ {#section_uwq_1rg_qgb .section}

支持。

在[EIP列表页面](https://vpc.console.aliyun.com/eip/cn-hangzhou/eips)，找到目标EIP，然后单击**更多** \> **转换为预付费模式**。

## EIP的API调用次数有限制吗？ {#section_h4q_1sg_qgb .section}

有限制，如果对EIP的API调用次数过于频繁会触发API调用次数限速。每用户每天调用API的次数如果大于500就会触发API限速。

## 预付费类型的EIP支持批量续费吗？ {#section_jz4_btg_qgb .section}

支持。您可以在批量续费中心批量续费：[https://renew.console.aliyun.com/center](https://renew.console.aliyun.com/center?spm=5176.2020520128.103.14.5JP3tJ#/renew/eip_pre?_k=03gpfx)

## 新申请的EIP的分配策略是什么样的？ {#section_xkm_2tg_qgb .section}

默认是随机分配，但对于频繁申请释放的用户，会优先从之前分配过的IP中再次分配。

