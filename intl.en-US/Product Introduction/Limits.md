# Limits {#concept_zrj_b23_vdb .concept}

Before you use Elastic IP Addresses \(EIPs\), note the following limits.

## General limits {#section_kqn_p23_vdb .section}

The general limits of EIPs are as follows:

-   Up to 20 EIPs can be created under one account. If you need more EIPs, open a ticket.
-   You can associate an EIP with a cloud resource only when the EIP is available.
-   The association of an EIP takes effect immediately.
-   An EIP can be associated with only one resource at a time.
-   An EIP that is locked because of security reasons cannot be associated with or disassociated from any cloud resource.
-   The maximum peak bandwidth available for Pay-As-You-Go EIPs that are billed based on traffic is 200 Mbit/s. If you need a larger peak bandwidth, you can use either of the following two ways.
    -   \(Recommended\) Add the EIP to an Internet Shared Bandwidth instance. For more information, see [Add EIPs to an Internet Shared Bandwidth instance](../../../../reseller.en-US/User Guide/Manage Pay-As-You-Go-billed EIPs/Add EIPs to an Internet Shared Bandwidth instance.md#).
    -   Open a ticket.

## Limits on associating ECS instances {#section_act_r23_vdb .section}

Note the following limits before you associate an EIP with an ECS instance:

-   The network type of the ECS instance must be VPC.
-   The ECS instance and the EIP must belong to the same region.
-   The ECS instance must be in the Running or Stopped state.
-   The ECS instance cannot have a public IP address or be associated with any EIP.
-   One ECS instance can be associated with only one EIP.

## Limits on associating NAT Gateways {#section_oy3_v23_vdb .section}

Note the following limits before you associate an EIP with a NAT Gateway:

-   The NAT Gateway and the EIP must belong to the same region.
-   Up to 20 EIPs can be associated with a NAT Gateway. To increase the quota, open a ticket.

## Limits on associating SLB instances {#section_nrq_x23_vdb .section}

Note the following limits before you associate an EIP with a Server Load Balancer \(SLB\) instance:

-   The network type of the SLB instance must be VPC.
-   The SLB instance and the EIP must belong to the same region.
-   Each SLB instance can be associated with only one EIP at a time.

## Limits on associating HaVips {#section_40a_nqo_3yv .section}

Note the following limits before you associate an EIP with a High-Availability Virtual IP Address \(HaVip\):

-   The HaVip and the EIP must belong to the same region.
-   The HaVip must be in the Available or Allocated state.
-   An HaVip can be associated with only one EIP.

## Limits on associating secondary ENIs {#section_rui_807_1f5 .section}

Note the following limits before you associate an EIP with a secondary Elastic Network Interface \(ENI\):

-   The network type of the secondary ENI must be VPC.
-   The secondary ENI and the EIP must belong to the same region.
-   You can associate an EIP with an ENI in three modes: NAT mode, cut-through mode, and multi-EIP to ENI mode.
    -   In the NAT mode, the number of EIPs with which a secondary ENI can be associated depends on the number of private IP addresses of the secondary ENI.
    -   In the cut-through mode, a secondary ENI can only be associated with one EIP.
    -   In the multi-EIP to ENI mode, a secondary ENI can be associated with ten EIPs. To increase the quota, open a ticket.

