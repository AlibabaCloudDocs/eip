# Limits {#concept_zrj_b23_vdb .concept}

Get yourself familiarize with the following limitations before using Elastic IP Address \(EIP\).

## Generic limitations {#section_kqn_p23_vdb .section}

-   Up to 20 Elastic IP Addresses can be created per account. Open a ticket to apply for more.
-   You can bind an EIP to a resource only when the status of the EIP is available.
-   The binding of an EIP takes effect immediately.
-   An EIP can be bound to only one resource at a time.
-   An EIP address that is locked because of security reasons cannot be bound or unbound.

## Limitations on binding ECS instances {#section_act_r23_vdb .section}

-   The ECS instance must be in a VPC network.
-   The ECS instance and the EIP must be in the same region.
-   The ECS instance must be running or stopped.
-   The ECS instance does not have a public IP, nor is it bound to any EIP.
-   An ECS instance can only be bound to one EIP.

## Limitations on binding NAT Gateway {#section_oy3_v23_vdb .section}

-   No bandwidth package was purchased before January 26, 2018 under the account that the NAT Gateway belongs to.
-   The NAT Gateway and the EIP must be in the same region.
-   Up to 10 Elastic IP Addresses can be bound to a NAT Gateway.

## Limitations on binding SLB {#section_nrq_x23_vdb .section}

-   The SLB instance must be in a VPC network.
-   The SLB instance and the EIP must be in the same region.
-   An SLB instance can be bound to one EIP at a time.

