# Limits {#concept_zrj_b23_vdb .concept}

Before you use Elastic IP Address \(EIP\), note the following limits.

## General limits {#section_kqn_p23_vdb .section}

-   Up to 20 EIPs can be created under one account. If you need more EIPs, open a ticket.
-   You can associate an EIP with a cloud resource only when the EIP is available.
-   The association of an EIP takes effect immediately.
-   An EIP can be associated with only one resource at a time.
-   An EIP that is locked because of security reasons cannot be associated with or disassociated from any cloud resource.

## Limits on associating ECS instances {#section_act_r23_vdb .section}

-   The ECS instance must be in a VPC network.
-   The ECS instance and the EIP must belong to the same region.
-   The ECS instance must be in the Running or Stopped status.
-   The ECS instance cannot have a public IP address or be associated with any EIP.
-   Each ECS instance can be associated with only one EIP at a time.

## Limits on associating NAT Gateways {#section_oy3_v23_vdb .section}

-   The NAT Gateway and the EIP must belong to the same region.
-   Up to 20 EIPs can be associated with a NAT Gateway. If you need to associate more EIPs, open a ticket.

## Limits on associating SLB instances {#section_nrq_x23_vdb .section}

-   The Server Load Balancer \(SLB\) instance must be in a VPC network.
-   The SLB instance and the EIP must belong to the same region.
-   Each SLB instance can be associated with only one EIP at a time.

## Limits on associating HaVips {#section_40a_nqo_3yv .section}

-   The High-Availablility Virtual IP Address \(HaVip\) and the EIP must belong to the same region.
-   The HaVip must be in the Available or Allocated status.
-   An HaVip can be associated with only one EIP.

## Limits on associating secondary ENIs {#section_rui_807_1f5 .section}

-   The network type of the secondary Elastic Network Interface \(ENI\) must be VPC.
-   The secondary ENI and the EIP must belong to the same region.
-   Three modes are available when you associate an EIP with a secondary ENI: NAT mode, cut-through mode, and multi-EIP to ENI mode.
    -   In the NAT mode, the number of EIPs that a secondary ENI can be associated with depends on the number of private IP addresses of the secondary ENI.
    -   In the cut-through mode, a secondary ENI can only be associated with one EIP.
    -   In the multi-EIP to ENI mode, a secondary ENI can be associated with 10 EIPs. If you need to associate more EIPs, open a ticket.

