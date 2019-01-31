# What is Elastic IP Address? {#concept_zmv_hd3_vdb .concept}

 An Elastic IP Address \(EIP\) is a public IP address resource that you can purchase and possess independently. You can bind an EIP to an ECS or SLB instance of the VPC network, or a NAT Gateway.

An EIP is a type of NAT IP address. It is located in the public network gateway of Alibaba Cloud, and is mapped to the private network interface card \(NIC\) of the bound ECS instance using the NAT method. Therefore, an ECS instance bound with an EIP can communicate with the Internet without disclosing the EIP on the NIC.

## Differences between an EIP and an ECS public IP {#section_ygb_ld3_vdb .section}

The following table lists the differences between an EIP and an ECS public IP.

|Item|EIP|ECS public IP|
|:---|:--|:------------|
|Supported networks|VPC|VPC and classic network|
|Independently possessed| Yes| No|
|Elastically bound to and  from an ECS instance|Yes|No|
|Disclosed on the NIC of the ECS instance|No| Classic Network: Yes 

 VPC: No

 |

## Benefits {#section_wqw_5d3_vdb .section}

-   Independently purchased and possessed

    You can purchase an EIP as an independent resource instead of purchasing it together with other computing or storage resources.

-   Flexible binding

    You can bind an EIP to an instance as needed to make the instance accessible to the Internet. You can release the EIP whenever Internet communication is not needed for the instance.

-   Configurable network capabilities

    You can adjust the bandwidth of an EIP as needed. The bandwidth change takes effect immediately.


