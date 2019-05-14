# What are Elastic IP Addresses? {#concept_zmv_hd3_vdb .concept}

An Elastic IP Address \(EIP\) is a public IP address resource that you can purchase and use independently. You can associate an EIP with an ECS or Server Load Balancer \(SLB\) instance of the VPC network, or a NAT Gateway.

An EIP is also a type of NAT IP address that is located in the public network gateway of Alibaba Cloud, and is mapped to the associated cloud instance through NAT. After a cloud instance is associated with an EIP, the cloud instance can communicate over the Internet through the EIP.

The following table lists the differences between an EIP and an ECS public IP address.

|Item|EIP|ECS public IP address|
|:---|:--|:--------------------|
|Supported networks|VPC|VPC and classic network|
|Can the IP address be independently used?|Yes|No|
|Can the IP address be associated with and disassociated from an ECS instance at any time?|Yes|No|
|Can the IP address be read on the NIC of an ECS instance?|The IP address can be read in the **Cut-Through Mode**.| Classic Network: Yes

 VPC: No

 |

## Benefits {#section_wqw_5d3_vdb .section}

EIP has the following advantages:

-   Purchase and use independently

    You can purchase an EIP as an independent resource instead of purchasing it together with other computing or storage resources.

-   Flexible association

    When you need an instance to access the Internet, you can associate an EIP with the instance as needed. You can also disassociate and release the EIP at any time.

-   Configurable network capabilities

    You can adjust the bandwidth value of an EIP as needed. The bandwidth change takes effect immediately.


## Limits {#section_xc5_fc4_4gb .section}

Before you use an EIP, note the following limits:

-   Up to 20 EIPs can be created under one account. If you need more EIPs, open a ticket.
-   You can associate an EIP with a cloud instance only when the EIP is available.
-   The association of an EIP takes effect immediately.
-   An EIP can be associated with only one instance at a time.
-   An EIP that is locked because of security reasons cannot be associated with or disassociated from any cloud instance.
-   Note the following limits when you associate an EIP with an ECS instance:
    -   The ECS instance must be in a VPC network.
    -   The ECS instance and the EIP must belong to the same region.
    -   The ECS instance must be in the Running or Stopped status.
    -   The target ECS instance cannot have a public IP address or be associated with any EIP.
    -   Each ECS instance can be associated with only one EIP at a time.
-   Note the following limits when you associate an EIP with an NAT Gateway instance:
    -   The NAT Gateway and the EIP must belong to the same region.
    -   Up to 10 EIPs can be associated with a NAT Gateway.
-   Note the following limits when you associate an EIP with an intranet SLB instance:
    -   The SLB instance must be in a VPC network.
    -   The SLB instance and the EIP must belong to the same region.
    -   Each SLB instance can be associated with only one EIP at a time.

