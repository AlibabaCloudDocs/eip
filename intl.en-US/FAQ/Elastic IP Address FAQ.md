# Elastic IP Address FAQ {#concept_o35_55m_vdb .concept}

This topic lists frequently asked questions about Elastic IP Address \(EIP\) and corresponding solutions.

-   [What differences are there between the public IP address and the EIP of an ECS instance?](#section_dfd_cvm_vdb)
-   [Why is an error of eip frequent purchase reported when I create an EIP?](#section_ti3_ufu_85t)
-   [Why is the EIP not displayed on the NIC of my ECS instance?](#section_rd3_w5m_vdb)
-   [How many EIPs can I create under one account?](#section_sd3_w5m_vdb)
-   [What resources can I associate an EIP with?](#section_td3_w5m_vdb)
-   [Why am I unable to access a created EIP?](#section_wd3_w5m_vdb)
-   [Why am I unable to associate an EIP with an ECS instance?](#section_gk4_fvm_vdb)
-   [Why am I unable to associate an EIP with a NAT Gateway?](#section_a23_w5m_vdb)
-   [Can I change the billing method of an EIP from traffic-based billing to bandwidth-based billing \(or perform the converse operation\)?](#section_s5w_mrf_qgb)
-   [Why are fees still incurred after I have deleted the EIP?](#section_wsh_44g_qgb)
-   [How is the EIP instance occupation fee billed?](#section_v1d_jpg_qgb)
-   [Are there benefits to set a peak bandwidth for an EIP that is billed based on traffic?](#section_xry_qqg_qgb)
-   [How many EIP API calls can I make in one day?](#section_h4q_1sg_qgb)
-   [How are newly created EIPs allocated?](#section_xkm_2tg_qgb)

## What differences are there between the public IP address and the EIP of an ECS instance? {#section_dfd_cvm_vdb .section}

-   The public IP address of an ECS instance can be found on the NIC of the ECS instance, whereas an EIP is a NAT IP address that is mapped to the intranet NIC of the ECS instance. Therefore, the EIP cannot be found on the NIC of the ECS instance.

-   You cannot disassociate a public IP address from an ECS instance, but you can associate and disassociate an EIP to and from an ECS instance at any time.


## Why is an error of eip frequent purchase reported when I create an EIP? {#section_ti3_ufu_85t .section}

Cause: Alibaba Cloud finds that you have been frequently creating and changing EIPs recently and therefore triggered security alerts to temporarily restrict your purchase of EIPs.

Solution: Make sure that you do not create EIPs more than the quota specified for your account in the next seven days. The restrictions will be automatically removed after seven days. For more information about how to view the quota of your account, see [Manage quotas](../../../../reseller.en-US/User Guide/Manage quotas.md#).

## Why is the EIP not displayed on the NIC of my ECS instance? {#section_rd3_w5m_vdb .section}

An EIP is configured on the Internet gateway and mapped to the NIC of the ECS instance through NAT. Therefore, you cannot see the EIP of the ECS instance on the NIC.

However, if you associate an EIP with a secondary Elastic Network Interface \(ENI\), you can select the Cut-Through Mode, which replaces the private IP address of the ENI with the EIP \(the ENI then becomes a pure Internet network interface\). You can then see the EIP in the network interface information of the operating system. For more information, see [Set the cut-through mode](../../../../reseller.en-US/User Guide/Associate an EIP with a cloud instance/Associate an EIP with a secondary ENI/Set the cut-through mode.md#).

## How many EIPs can I create under one account? {#section_sd3_w5m_vdb .section}

You can create up to 20 EIPs under one account. If you require an increase to your quota, you can open a ticket for this request.

## What resources can I associate an EIP with? {#section_td3_w5m_vdb .section}

Currently, you can associate an EIP with an ECS or SLB instance of the VPC network, or a NAT Gateway.

## Why am I unable to access a created EIP? {#section_wd3_w5m_vdb .section}

Possible causes are as follows:

-   The EIP is not associated with any cloud resources.
-   If the EIP is associated with an ECS instance, check the security policies of the ECS instance. For example, if the ECS instance is added to a security group that denies the access from port 80, then you cannot access the EIP over port 80.
-   The bill for the EIP is overdue.

## Why am I unable to associate an EIP with an ECS instance? {#section_gk4_fvm_vdb .section}

Possible causes are as follows:

-   The target ECS instance to which you want to associate the EIP is not of the VPC network.
-   The regions of the EIP and the ECS instance are not the same.
-   The state of the ECS instance does not support the association action. You can associate an EIP only with an ECS instance that is in the running or stopped state.
-   The ECS instance is already associated with an EIP.
-   The ECS instance has a public IP address that is system allocated.

## Why am I unable to associate an EIP with a NAT Gateway? {#section_a23_w5m_vdb .section}

## Can I change the billing method of an EIP from traffic-based billing to bandwidth-based billing \(or perform the converse operation\)? {#section_s5w_mrf_qgb .section}

Yes.

Note that changes to the billing method take effect at 00:00 of the next day. During this period of time, you cannot change the peak bandwidth. If you need to change the peak bandwidth, you can cancel the order of the billing method change. After the order is cancelled, you can change the peak bandwidth.

## Why are fees still incurred after I have deleted the EIP? {#section_wsh_44g_qgb .section}

If the deleted EIP was a Pay-As-You-Go-billed EIP, one final bill is generated in the next hour or the next day \(depending on if the billing method is traffic-based or bandwidth-based\) that corresponds to the usage of the EIP until the time at which it is deleted. For example,

-   If you delete an EIP that is billed according to traffic usage at 10:30, you will be charged for its use between the hour of 10:00 to 11:00.
-   If you delete an EIP that is billed according to bandwidth on January 1, 2019, you will receive a bill for the time from January 1, 2019 to January 2, 2019 after the EIP is deleted.

## How is the EIP instance occupation fee billed? {#section_v1d_jpg_qgb .section}

Depending on the cloud resources and quotas associated with the EIPs, an instance occupation fee may be charged to your account as follows:

-   If the EIP is associated with an ECS instance and you have not exceeded the default quota of 20 EIPs, no instance occupation fee is charged.
-   If the EIP is associated with other types of cloud resources except ECS instances, including but not limited to NAT Gateways, SLB instances, and ENIs, an instance occupation fee is charged.
-   An instance occupation fee for an EIP is charged at USD 0.003/hour regardless of whether the billing of the EIP is bandwidth-based or traffic-based.
-   An EIP instance occupation fee can be charged regardless of whether the EIP is added to an Internet Shared Bandwidth instance.

## Are there benefits to set a peak bandwidth for an EIP that is billed based on traffic? {#section_xry_qqg_qgb .section}

For an EIP that is billed based on traffic, we recommend that you set a peak bandwidth value to avoid incurring excessive charges related to outbound traffic.

Note that service quality is not guaranteed for an EIP that is billed based on traffic and for which you set a peak bandwidth value. If you need the peak bandwidth value to be guaranteed, you need to purchase an EIP that is billed based on bandwidth or purchase an Internet Shared Bandwidth instance.

## How many EIP API calls can I make in one day? {#section_h4q_1sg_qgb .section}

500. In each day, you can make up to 500 EIP API calls.

## How are newly created EIPs allocated? {#section_xkm_2tg_qgb .section}

By default, newly created EIPs are allocated at random. However, if you release EIPs too frequently, the released addresses are likely to be re-allocated to your EIP quota rather than new EIPs.

