# FAQ

This topic provides answers to some frequently asked questions about Elastic IP Address \(EIP\).

-   General questions
    -   [What is an EIP?](#section_qzu_vp2_jki)
    -   [What are the benefits of EIPs?](#section_mgn_p84_nly)
    -   [What are the differences between an EIP and a public IP address of an ECS instance?](#section_dfd_cvm_vdb)
    -   [Why does the system prompt "eip frequent purchase" when I request an EIP?](#section_n0q_mn4_66y)
    -   [Why am I unable to access an EIP?](#section_v69_jpi_fxd)
    -   [How are newly created EIPs assigned?](#section_7qp_8nq_isj)
-   FAQ about pay-as-you-go EIPs
    -   [Why am I still charged after I release a pay-as-you-go EIP?](#section_1nh_ax9_e2l)
    -   [Why do I need to set a maximum bandwidth value for a pay-by-data-transfer EIP?](#section_am7_sfw_w5y)
-   FAQ about limits on EIP
    -   [How many EIPs can I create for one Alibaba Cloud account?](#section_hrm_9q9_8fg)
    -   [Can I associate an EIP with multiple cloud resources?](#section_12o_yti_nld)
    -   [Is the number of EIP operations that I can call limited?](#section_r68_ghp_dft)
    -   [If an ECS instance is associated with an EIP, can I use the DNAT feature of NAT gateways to provide service to the Internet?](#section_wnr_50v_1qi)
-   FAQ about associating EIPs with cloud resources
    -   [What are the cloud resources with which I can associate EIPs?](#section_274_5mv_ycx)
    -   [Why am I unable to associate an EIP with a NAT gateway?](#section_6st_c7i_glg)
    -   [Why am I unable to associate an EIP with an ECS instance?](#section_49i_4mq_g42)
    -   [Why am I unable to view the EIP on the ENI of an ECS instance after I associate the EIP with the ECS instance?](#section_rd3_w5m_vdb)
    -   [How can I associate multiple EIPs with one ECS instance?](#section_naa_kwx_eks)

## What is an EIP?

An EIP is a public IP address that you can purchase and own as an independent resource. You can associate EIPs with Elastic Compute Service \(ECS\) instances, internal-facing Server Load Balancer \(SLB\) instances, secondary elastic network interfaces \(ENIs\), NAT gateways, and high-availability virtual IP addresses \(HAVIPs\). The ECS instances, internal-facing SLB instances, and secondary ENIs must be deployed in virtual private clouds \(VPCs\).

An EIP is also a type of Network Address Translation \(NAT\) IP address that is deployed at the Internet-facing gateway of Alibaba Cloud, and is mapped to the associated cloud resource through NAT. After an EIP is associated with a cloud resource, the cloud resource can access the Internet through the EIP.

## What are the benefits of EIPs?

EIPs have the following benefits:

-   Independently purchased and owned

    You can purchase and own an EIP as an independent resource. You do not need to purchase it along with other computing or storage resources.

-   Flexible association

    You can associate an EIP with or disassociate the EIP from a cloud resource as needed.

-   Adjustable bandwidth

    You can adjust the bandwidth of an EIP as needed. The new bandwidth immediately takes effect.


## What are the differences between an EIP and a public IP address of an ECS instance?

The following table lists the differences between an EIP and a public IP address of an ECS instance.

|Item|EIP|ECS public IP address|
|:---|:--|:--------------------|
|Supported networks|VPCs|VPCs and classic networks|
|Whether you can independently own the IP address|Yes|No|
|Whether the IP address can be associated with and disassociated from an ECS instance as needed|Yes|No|
|Whether you can view the IP address on the ENI of the ECS instance|You can view the IP address on the ENI in **Cut-Through Mode** or **Multi-EIP to ENI Mode**|Classic networks: Yes

VPCs: No |

## Why does the system prompt "eip frequent purchase" when I request an EIP?

Cause: Alibaba Cloud has noticed that you have been frequently requesting and changing EIPs, which triggers security alerts. Therefore, the system temporarily restricts your purchase of EIPs.

Solution: Make sure that the number of EIPs that you request in the next 7 days does not exceed the quota. This way, the restriction is automatically removed after 7 days. For more information about how to view the quotas of your Alibaba Cloud account, see [Quota management](/intl.en-US/User Guide/Quota management.md).

## Why am I unable to access an EIP?

Possible causes:

-   The EIP is not associated with a cloud resource.
-   A security policy is configured for the Elastic Compute Service \(ECS\) instance. For example, if the ECS instance is added to a security group that denies access to port 80, you cannot access port 80 of the EIP.
-   The EIP has an overdue payment.

## How are newly created EIPs assigned?

By default, newly created EIPs are assigned at random. However, if you request and release EIPs frequently, you may be assigned with the released EIPs instead of new ones.

## Why am I still charged after I release a pay-as-you-go EIP?

For a pay-as-you-go EIP, the bill of an hour is generated in the next hour. You may receive the bill after the EIP is released. However, the system stops calculating the fee upon its release. For example:

After you release a pay-by-data-transfer EIP instance at 10:30, you receive the bill for the data usage from 10:00 to 11:00.

## Why do I need to set a maximum bandwidth value for a pay-by-data-transfer EIP?

For a pay-by-data-transfer EIP, we recommend that you set a maximum bandwidth value to avoid unnecessary fees due to excessive outbound traffic.

The maximum bandwidth value is not guaranteed for a pay-by-data-transfer EIP. For example, if the maximum bandwidth value of a pay-by-data-transfer EIP is set to 200 Mbit/s, the peak bandwidth may not reach 200 Mbit/s. If you want to use an EIP with a guaranteed peak bandwidth, you must purchase a pay-by-bandwidth EIP or an EIP bandwidth plan.

## How many EIPs can I create for one Alibaba Cloud account?

You can create at most 20 EIPs for one Alibaba Cloud account. To create more EIPs, apply for a quota increase. For more information, see [Quota management](/intl.en-US/User Guide/Quota management.md).

## Can I associate an EIP with multiple cloud resources?

No. You can associate an EIP with only one cloud resource.

## Is the number of EIP operations that I can call limited?

Yes. If you call EIP operations more than 500 times within one day, the system responds to your requests at a lower speed.

## If an ECS instance is associated with an EIP, can I use the DNAT feature of NAT gateways to provide service to the Internet?

No. Limits:

-   If an ECS instance is associated with an EIP, you cannot use the Destination Network Address Translation \(DNAT\) feature of NAT gateways to provide service to the Internet.

    Before you can use the DNAT feature, you must disassociate the EIP from the ECS instance. After you disassociate the EIP, you can add DNAT entries to the ECS instance. For more information, see [Disassociate an EIP from a cloud resource](/intl.en-US/User Guide/Disassociate an EIP from a cloud resource.md) and [Create a DNAT entry to provide Internet-facing services](/intl.en-US/User Guide/Create a DNAT entry to provide Internet-facing services.md).

-   If you have already added DNAT entries to an ECS instance, you cannot associate an EIP with the ECS instance.

    Before you can associate an EIP with the ECS instance, you must delete the DNAT entries. After you delete the DNAT entries, you can associate an EIP with the ECS instance. For more information, see [Delete a DNAT entry]() and [Associate an EIP with a NAT gateway](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Associate an EIP with a NAT gateway.md).


**Note:** If DNAT entries are added to an ECS instance that is associated with an EIP, the ECS instance preferably uses the EIP to communicate with the Internet.

## What are the cloud resources with which I can associate EIPs?

You can associate EIPs with ECS instances, internal-facing SLB instances, secondary ENIs, NAT gateways, and HAVIPs. The ECS instances, internal-facing SLB instances, and secondary ENIs must be deployed in VPCs.

## Why am I unable to associate an EIP with a NAT gateway?

If you purchased a NAT bandwidth plan before January 26, 2018, you must use the NAT bandwidth plan to provide public IP addresses to the NAT gateway. To associate an EIP with a NAT gateway, submit a ticket.

## Why am I unable to associate an EIP with an ECS instance?

Possible reasons:

-   You can associate an EIP with only an ECS instance that is deployed in a VPC. If the ECS instance is not deployed in a VPC, you cannot associate an EIP with the ECS instance.
-   The EIP and ECS instance are deployed in different regions.
-   The state of the ECS instance does not support the association action. You can associate an EIP only with an ECS instance that is in the Running or Stopped state.
-   The ECS instance is already assigned a public IP address or associated with another EIP.

## Why am I unable to view the EIP on the ENI of an ECS instance after I associate the EIP with the ECS instance?

An EIP is configured on the Internet-facing gateway and mapped to the private ENI of the ECS instance through NAT. Therefore, you cannot view the EIP on the private ENI of the ECS instance.

When you associate an EIP with a secondary ENI, you can select the cut-through mode or multi-EIP to ENI mode.

-   Cut-through mode

    In this mode, the EIP replaces the private IP address of the secondary ENI. The secondary ENI becomes a pure Internet network interface controller \(NIC\) and its private network feature is no longer available. You can view the EIP in the ENI of the operating system and run the ifconfig or ipconfig command to obtain the public IP address of the ENI. For more information, see [Associate an EIP with a secondary ENI in cut-through mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate an EIP with a secondary ENI in cut-through mode.md).

-   Multi-EIP to ENI mode

    In this mode, the private network feature of the secondary ENI is available. You can view the EIP on the ENI. After the operating system is configured with a static IP address, you can run the ifconfig or ipconfig command to obtain the public IP address of the ENI. For more information, see [Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode.md).


## How can I associate multiple EIPs with one ECS instance?

You can associate multiple EIPs with one ECS instance in the following ways:

-   Associate an EIP with each secondary ENI for multiple times, and then associate the secondary ENIs with an ECS instance. The number of secondary ENIs that can be associated with an ECS instance varies based on the specification of the ECS instance. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).
-   If you associate an EIP with a secondary ENI in **NAT Mode**, you can associate multiple EIPs with the secondary private IP address of the secondary ENI. Then, you can associate the secondary ENI with an ECS instance. For more information, see [Associate multiple EIPs with a secondary ENI in NAT mode](/intl.en-US/Best practices/Associate multiple EIPs with a secondary ENI in NAT mode.md).
-   If you associate an EIP with a secondary ENI in **Multi-EIP to ENI Mode**, you can associate multiple EIPs with the secondary ENI. Then, you can associate the secondary ENI with an ECS instance. For more information, see [Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode.md).

