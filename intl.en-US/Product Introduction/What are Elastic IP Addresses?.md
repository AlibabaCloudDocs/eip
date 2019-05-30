# What are Elastic IP Addresses? {#concept_zmv_hd3_vdb .concept}

An Elastic IP Address \(EIP\) is a public IP address resource that you can purchase and use independently. You can associate an EIP with an ECS instance of the VPC network, a private SLB instance of the VPC network, an ENI of the VPC network, and a NAT Gateway, or a HAVIP.

An EIP is also a type of NAT IP address that is located in the public network gateway of Alibaba Cloud, and is mapped to the associated cloud instance through NAT. After a cloud instance is associated with an EIP, the cloud instance can communicate over the Internet through the EIP.

## The differences between an EIP and an ECS public IP address {#section_vke_czq_hoy .section}

The following table lists the differences between an EIP and an ECS public IP address.

|Item|EIP|ECS public IP address|
|:---|:--|:--------------------|
|Supported networks|VPC|VPC and classic network|
|Can the IP address be independently used?|Yes|No|
|Can the IP address be associated with and disassociated from an ECS instance at any time?|Yes|No|
|Can the IP address be read on the NIC of an ECS instance?|The IP address can be read on the NIC in the **Cut-Through Mode** or **Multi-EIP to ENI Mode**.| Classic Network: Yes

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


