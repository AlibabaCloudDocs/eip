# Elastic IP Address FAQ {#concept_o35_55m_vdb .concept}

The following are common questions and corresponding solutions about Elastic IP Address \(EIP\).

-   [1. What is the difference between an EIP and a public IP address of an ECS instance?](#section_dfd_cvm_vdb)
-   [Why can't I see the EIP on the NIC of my ECS instance?](#section_rd3_w5m_vdb)
-   [3. How many EIPs can an account create?](#section_sd3_w5m_vdb)
-   [4. What resources can I associate an EIP with?](#section_td3_w5m_vdb)
-   [6. Why can't I access the EIP that I have created?](#section_wd3_w5m_vdb)
-   [7. Why can't I associate an EIP with an ECS instance?](#section_gk4_fvm_vdb)
-   [8. Why can't I associate an EIP with a NAT Gateway?](#section_a23_w5m_vdb)
-   [Can I change the billing method of an EIP from traffic-based billing to bandwidth-based billing or from bandwidth-based billing to traffic-based billing?](#section_s5w_mrf_qgb)
-   [Why are fees still incurred after I have deleted the EIP?](#section_wsh_44g_qgb)
-   [How is EIP instance occupation fee billed?](#section_v1d_jpg_qgb)
-   [What is the purpose of setting a peak bandwidth for an EIP that is billed based on traffic?](#section_xry_qqg_qgb)
-   [Is there a limit on the number of EIP API calls that I can make during one day?](#section_h4q_1sg_qgb)
-   [How are newly applied EIPs allocated?](#section_xkm_2tg_qgb)

## 1. What is the difference between an EIP and a public IP address of an ECS instance? {#section_dfd_cvm_vdb .section}

-   A public IP address can be found on the NIC of the ECS instance, whereas an EIP is a NAT IP address that is mapped to the intranet NIC of the ECS instance. Therefore, the EIP cannot be found on the NIC of the ECS instance.

-   You cannot disassociate a public IP address from an ECS instance but you can associate and disassociate an EIP with an ECS instance at any time.


## Why can't I see the EIP on the NIC of my ECS instance? {#section_rd3_w5m_vdb .section}

An EIP is configured on the Internet gateway and mapped to the NIC of the ECS instance through NAT. Therefore, you cannot see the EIP on the NIC of the ECS instance.

When you associate an EIP with a secondary Elastic Network Interface \(ENI\), you can select the Cut-Through Mode. In this mode, the EIP replaces the private IP address of the ENI and the ENI becomes a pure Internet network interface. You can see the EIP in the network interface information of the operating system. For more information, see [Configure the cut-through mode](../../../../reseller.en-US/User Guide/Configure the cut-through mode.md#).

## 3. How many EIPs can an account create? {#section_sd3_w5m_vdb .section}

An account can create 20 EIPs at most. Open a ticket if you need more EIPs.

## 4. What resources can I associate an EIP with? {#section_td3_w5m_vdb .section}

Currently, you can associate an EIP with an ECS or SLB instance of the VPC network, or a NAT Gateway.

## 6. Why can't I access the EIP that I have created? {#section_wd3_w5m_vdb .section}

Possible causes are as follows:

-   The EIP is not associated with any resources.
-   If the EIP is associated with an ECS instance, check the security policies of the ECS instance. For example, if the ECS instance is added to a security group that denies the access from port 80, then you cannot access the EIP over port 80.
-   The bill for the EIP is overdue.

## 7. Why can't I associate an EIP with an ECS instance? {#section_gk4_fvm_vdb .section}

Possible causes are as follows:

-   The ECS instance with which you associate the EIP is not of VPC network. An EIP can only be associated with an ECS instance of the VPC network.
-   The regions of the EIP and the ECS instance are not the same.
-   The status of the ECS instance is invalid. You can associate an EIP only with an ECS instance that is in the running or stopped state.
-   The ECS instance is associated with other EIPs.
-   The ECS instance has a public IP address that is system allocated.

## 8. Why can't I associate an EIP with a NAT Gateway? {#section_a23_w5m_vdb .section}

## Can I change the billing method of an EIP from traffic-based billing to bandwidth-based billing or from bandwidth-based billing to traffic-based billing? {#section_s5w_mrf_qgb .section}

Yes.

The billing method change takes effect at 00:00 of the next day after the change. During this period of time, you cannot change the peak bandwidth. If you need to change the peak bandwidth, you can cancel the order of billing method change. After the order is cancelled, you can change the peak bandwidth.

## Why are fees still incurred after I have deleted the EIP? {#section_wsh_44g_qgb .section}

For an EIP that is billed with the Pay-As-You-Go method, the bill is generated in the next hour or the next day. You will receive the bill after deleting the EIP, but the billing has actually stopped. For example,

-   if you delete an EIP that is billed based on traffic at 10:30, you receive a bill for a traffic fee from 10:00 to 11:00 after the EIP is deleted.
-   If you delete an EIP that is billed based on bandwidth on January 1, 2019, you receive a bill for the time from January 1, 2019 to January 2, 2019 after the EIP is deleted.

## How is EIP instance occupation fee billed? {#section_v1d_jpg_qgb .section}

The instance occupation fee is related to the resources and quotas associated with the EIP.

-   For an EIP instance with a default quota of less than 20, if the EIP is associated with an ECS instance, no instance occupation fee is charged.
-   If the EIP is associated with other types of cloud products except ECS instances, including but not limited to NAT Gateways, SLB instances, and ENIs, the instance occupation fee is charged.
-   Whether bandwidth-based or traffic-based billing is used, the instance fee for an EIP is 0.02 RMB/hour.
-   The EIP instance occupation fee is irrelevant to whether the EIP is added to an Internet Shared Bandwidth instance.

## What is the purpose of setting a peak bandwidth for an EIP that is billed based on traffic? {#section_xry_qqg_qgb .section}

For an EIP that is billed based on traffic, you can set a peak bandwidth to avoid excessive outbound traffic to control costs.

The service quality is not guaranteed for an EIP that is billed based on traffic and for which you set a peak bandwidth. For example, if the peak bandwidth of an EIP that is billed based on traffic is set to 200 Mbit/s, the peak bandwidth cannot necessarily reach 200 Mbit/s. If you need a guaranteed peak bandwidth, you need to purchase an EIP that is billed based on bandwidth or an Internet Shared Bandwidth instance.

## Is there a limit on the number of EIP API calls that I can make during one day? {#section_h4q_1sg_qgb .section}

Yes. If you call EIP APIs too frequently during one day, the number of API calls will be limited. Specifically, you cannot call APIs any more after the number of API calls reach 500 in a day.

## How are newly applied EIPs allocated? {#section_xkm_2tg_qgb .section}

Newly applied addresses are allocated randomly by default. However, if you release EIPs too frequently, the released addresses will be re-allocated for your newly applied EIPs.

