# Elastic IP Address FAQ {#concept_o35_55m_vdb .concept}

This topic lists frequently asked questions about Elastic IP Addresses \(EIPs\) and corresponding solutions.

-   General questions
    -   [What is an EIP?](#section_qzu_vp2_jki)
    -   [What are the advantages of EIPs?](#section_mgn_p84_nly)
    -   [What are the differences between the public IP address and the EIP of an ECS instance?](#section_dfd_cvm_vdb)
    -   [Why is an error of "eip frequent purchase" reported when I create an EIP?](#section_n0q_mn4_66y)
    -   [Why am I unable to access a created EIP?](#section_v69_jpi_fxd)
    -   [How are newly created EIPs allocated?](#section_7qp_8nq_isj)
-   FAQ about Pay-As-You-Go EIPs
    -   [Why are fees still incurred after I have deleted the EIP?](#section_1nh_ax9_e2l)
    -   [Are there benefits to set a peak bandwidth for a Pay-As-You-Go EIP that is billed based on traffic?](#section_am7_sfw_w5y)
-   FAQ about EIP restrictions
    -   [How many EIPs can I create under one account?](#section_hrm_9q9_8fg)
    -   [Can I associate an EIP with multiple cloud resources at the same time?](#section_12o_yti_nld)
    -   [How many EIP API calls can I make in one day?](#section_r68_ghp_dft)
-   FAQ about associating EIPs with cloud resources
    -   [What resources can I associate an EIP with?](#section_274_5mv_ycx)
    -   [Why am I unable to associate an EIP with a NAT Gateway?](#section_6st_c7i_glg)
    -   [Why am I unable to associate an EIP with an ECS instance?](#section_49i_4mq_g42)
    -   [Why is the EIP not displayed on the NIC of my ECS instance?](#section_rd3_w5m_vdb)
    -   [How do I use multiple EIPs for an ECS instance if each ECS instance can only be associated with one EIP?](#section_naa_kwx_eks)

## What is an EIP? {#section_qzu_vp2_jki .section}

An EIP is a public IP address resource that you can purchase and use independently. Currently, you can associate EIPs with ECS instances, intranet Server Load Balancer \(SLB\) instances, secondary Elastic Network Interfaces \(ENIs\), NAT Gateways, and High-Availability Virtual IP Addresses \(HaVips\). The ECS instances, intranet SLB instances, and secondary ENIs must belong to VPC networks.

An EIP is also a type of NAT IP address that is located in the public network gateway of Alibaba Cloud, and is mapped to the associated cloud instance through NAT. After a cloud instance is associated with an EIP, the cloud instance can communicate with the Internet through the EIP.

## What are the advantages of EIPs? {#section_mgn_p84_nly .section}

EIPs have the following advantages:

-   Purchase and use independently

    You can purchase an EIP as an independent resource instead of purchasing it together with other computing or storage resources.

-   Flexible association

    When you need a cloud instance to access the Internet, you can associate an EIP with the instance. You can also disassociate and release the EIP at any time.

-   Configurable network capabilities

    You can adjust the bandwidth value of an EIP at any time. The bandwidth change takes effect immediately.


## What are the differences between the public IP address and the EIP of an ECS instance? {#section_dfd_cvm_vdb .section}

The following table lists the differences between an EIP and an ECS public IP address.

|Item|EIP|ECS public IP address|
|:---|:--|:--------------------|
|Supported networks|VPC|VPC and classic network|
|Can the IP address be independently used?|Yes|No|
|Can the IP address be associated with and disassociated from the ECS instance at any time?|Yes|No|
|Can the IP address be read on the NIC of the ECS instance?|The IP address can be read on the NIC in the **Cut-Through Mode** or **Multi-EIP to ENI Mode**.| Classic network: Yes

 VPC: No

 |

## Why is an error of "eip frequent purchase" reported when I create an EIP? {#section_n0q_mn4_66y .section}

Cause: Alibaba Cloud finds that you have been frequently creating and changing EIPs recently and therefore triggered security alerts to temporarily restrict your purchase of EIPs.

Solution: Make sure that you do not create EIPs more than the quota specified for your account in the next seven days. The restrictions will be automatically removed after seven days. For more information about how to view the quota of your account, see [Manage quotas](../../../../intl.en-US/User Guide/Manage quotas.md#).

## Why am I unable to access a created EIP? {#section_v69_jpi_fxd .section}

Possible causes are as follows:

-   The EIP is not associated with any cloud resources.
-   If the EIP is associated with an ECS instance, check the security policies of the ECS instance. For example, if the ECS instance is added to a security group that denies the access from port 80, then you cannot access the EIP over port 80.
-   The bill for the EIP is overdue.

## How are newly created EIPs allocated? {#section_7qp_8nq_isj .section}

By default, newly created EIPs are allocated at random. However, if you release EIPs too frequently, the released addresses are likely to be re-allocated to your EIP quota rather than new EIPs.

## Why are fees still incurred after I have deleted the EIP? {#section_1nh_ax9_e2l .section}

If the deleted EIP is a Pay-As-You-Go EIP, one final bill is generated in the next hour that corresponds to the usage of the EIP until the time at which it is deleted. For example:

If you delete an EIP that is billed according to traffic usage at 10:30, you will receive a bill for the time between the hour of 10:00 to 11:00.

## Are there benefits to set a peak bandwidth for a Pay-As-You-Go EIP that is billed based on traffic? {#section_am7_sfw_w5y .section}

For a Pay-As-You-Go EIP that is billed based on traffic, we recommend that you set a peak bandwidth value to avoid incurring excessive charges related to outbound traffic.

Note that service quality is not guaranteed for an EIP that is billed based on traffic and for which you set a peak bandwidth value. If you need the peak bandwidth value to be guaranteed, you need to purchase an EIP that is billed based on bandwidth or purchase an Internet Shared Bandwidth instance.

## How many EIPs can I create under one account? {#section_hrm_9q9_8fg .section}

You can create up to 20 EIPs under one account. If you require an increase to your quota, you can open a ticket for this request.

## Can I associate an EIP with multiple cloud resources at the same time? {#section_12o_yti_nld .section}

No. You can only associate an EIP with one cloud resource.

## How many EIP API calls can I make in one day? {#section_r68_ghp_dft .section}

500. In each day, you can make up to 500 EIP API calls.

## What resources can I associate an EIP with? {#section_274_5mv_ycx .section}

Currently, you can associate an EIP with an ECS instance of the VPC network, an intranet SLB instance of the VPC network, an ENI of the VPC network, a NAT Gateway, or an HaVip.

## Why am I unable to associate an EIP with a NAT Gateway? {#section_6st_c7i_glg .section}

If you purchased a NAT bandwidth package before January 26, 2018, you need to use the NAT bandwidth package to provide public IP addresses for the NAT Gateway. If you must associate an EIP with the NAT Gateway, open a ticket.

## Why am I unable to associate an EIP with an ECS instance? {#section_49i_4mq_g42 .section}

Possible causes are as follows:

-   The target ECS instance to which you want to associate the EIP is not of the VPC network.
-   The regions of the EIP and the ECS instance are not the same.
-   The status of the ECS instance does not support the association action. You can associate an EIP only with an ECS instance that is in the running or stopped state.
-   The ECS instance is already associated with an EIP.

## Why is the EIP not displayed on the NIC of my ECS instance? {#section_rd3_w5m_vdb .section}

An EIP is configured on the Internet gateway and mapped to the NIC of the ECS instance through NAT. Therefore, you cannot see the EIP of the ECS instance on the NIC.

However, if you associate an EIP with a secondary ENI, you can select the cut-through mode or multi-EIP to ENI mode, which allows you to see the EIP in the network interface information of the operating system.

-   Cut-through mode

    In the cut-through mode, the EIP replaces the private IP address of the ENI. The ENI becomes a pure Internet network interface and its intranet function is not available any more. You can see the EIP in the ENI of the operating system, and directly obtain the public IP address on the ENI by running the ifconfig or ipconfig command. For more information, see [Set the cut-through mode](../../../../intl.en-US/User Guide/Associate an EIP with a cloud instance/Associate an EIP with a secondary ENI/Set the cut-through mode.md#).

-   Multi-EIP to ENI mode

    In the multi-EIP to ENI mode, the intranet function of the secondary ENI is still available. The EIPs are visible to the ENI. After the operating system is configured with a static IP address, you can run the ifconfig or ipconfig command to obtain the public IP address of the ENI. For more information, see [Set the Multi-EIP to ENI mode](../../../../intl.en-US/User Guide/Associate an EIP with a cloud instance/Associate an EIP with a secondary ENI/Set the Multi-EIP to ENI mode.md#).


## How do I use multiple EIPs for an ECS instance if each ECS instance can only be associated with one EIP? {#section_naa_kwx_eks .section}

You can use multiple EIPs for an ECS instance in the following way:

-   Associate an EIP with a secondary ENI and associate the ENI with the ECS instance. The number of ENIs that can be associated with an ECS instance varies according to the specification of the ECS instance. For more information, see [Instance type families](../../../../intl.en-US/Instances/Instance type families.md#).
-   If you associate the EIP with the secondary ENI in the **NAT Mode**, you can associate multiple EIPs with the ENI by associating one EIP with one secondary private IP address of the ENI. Then, you can associate the ENI with the ECS instance and in this way the ECS instance can use multiple EIPs. For more information, see [Associate multiple EIPs with an ENI in the NAT mode](../../../../intl.en-US/Best practices/Associate multiple EIPs with an ENI in the NAT mode.md#).
-   If you associate the EIP with the secondary ENI in the **Multi-EIP to ENI Mode**, you can directly associate multiple EIPs with the ENI. Then, you can associate the ENI with the ECS instance and in this way the ECS instance can use multiple EIPs. For more information, see [Set the Multi-EIP to ENI mode](../../../../intl.en-US/User Guide/Associate an EIP with a cloud instance/Associate an EIP with a secondary ENI/Set the Multi-EIP to ENI mode.md#).

