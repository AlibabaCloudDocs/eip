# Limits {#concept_zrj_b23_vdb .concept}

Get yourself familiarize with the following limits before using Elastic IP Address \(EIP\).

## General limits {#section_kqn_p23_vdb .section}

-   Up to 20 Elastic IP Addresses can be created per account. Open a ticket to apply for more.
-   You can bind an EIP to a resource only when the status of the EIP is available.
-   The binding of an EIP takes effect immediately.
-   An EIP can be bound to only one resource at a time.
-   An EIP address that is locked because of security reasons cannot be bound or unbound.

## Limits on binding ECS instances {#section_act_r23_vdb .section}

-   The ECS instance must be in a VPC network.
-   The ECS instance and the EIP must be in the same region.
-   The ECS instance must be in the running or stopped status.
-   The ECS instance does not have a public IP, nor is it bound to any EIP.
-   Each ECS instance can have only one EIP bound to it at a time.

## Limits on binding NAT Gateway {#section_oy3_v23_vdb .section}

-   The NAT Gateway and the EIP must be in the same region.
-   Up to 10 EIPs can be bound to a NAT Gateway.

## Limits on binding SLB {#section_nrq_x23_vdb .section}

-   The SLB instance must be in a VPC network.
-   The SLB instance and the EIP must be in the same region.
-   Each SLB instance can have only one EIP bound to it at a time.

