# Change an ECS public IP address to an EIP {#concept_jgg_1rm_vdb .concept}

You can flexibly use a public IP address by changing an ECS public IP address to an EIP.

**Note:** After the public IP address of an ECS instance of the VPC network is converted to an EIP, it cannot be converted back to a public IP address.

## Introduction to public IP addresses {#section_vrf_5rm_vdb .section}

A public IP address and network bandwidth is required for an ECS instance if you want users to access the application deployed on the ECS instance.

Alibaba Cloud provides two types of public IP addresses:

-   ECS public IP address

    If you choose to use the public IP address allocated by the system when creating an ECS instance of the VPC network, a public IP address will be allocated to the ECS instance after the ECS instance is created and the public IP address cannot be detached from the ECS instance.

-   EIP

    An Elastic IP \(EIP\) address is a public IP address resource that you can purchase and possess independently. Currently, you can attach an EIP to an ECS instance of the VPC network, a private SLB instance of the VPC network, or a NAT Gateway. You can also add EIPs to an Internet Shared Bandwidth or a Data Transfer Plan to save the Internet cost.


Using the high-quality multi-line BGP network of Alibaba Cloud, a public IP address and an EIP have the same capacity in providing Internet services. The greatest difference between the two lies in whether it can be detached from an ECS instance. You can detach an EIP from an ECS instance anytime and attach it to the ECS instance again when necessary, while you cannot detach a public IP address from an ECS instance.

## Benefits in changing a public IP address to an EIP {#section_abd_gsm_vdb .section}

Public IP addresses will be gradually replaced by EIPs. EIP has the following benefits:

-   Flexibly  defend against DDoS attacks

    If your server is under DDoS attack, you can immediately detach the EIP from the attacked ECS instance. You can attach a new EIP to the ECS instance and use Anti-DDoS Pro to defend the DDoS attack.

-   Simplify system and application extension

    When you need to expend your application to provide external services, you may need to deploy the application on multiple ECS instances and use SLB to distribute traffic. You can unbind the EIP first and then attach it to an SLB instance of the VPC network to provide external services. Users are insensitive to the architecture change.

-   Save costs

    If you add EIPs to an Internet Shared Bandwidth, the Internet costs can be greatly reduced.

    For more information, see[How to save the Internet cost?](../../../../reseller.en-US/Best practices/How to save the Internet cost?.md#)

-   Simplify the management of network access

    You can submit a ticket to apply for continuous public IP addresses to simplify network access management.


## Limitation {#section_abt_psm_vdb .section}

To change a public IP to an EIP, the following requirements must be met:

-   You can only change the public IP of an ECS instance of the VPC network to an EIP. 
-   You can only change the public IP of an ECS instance in stopped or running.
-   If the configuration of the ECS instance is being changed, the conversion cannot be performed.
-   The conversion cannot be performed within 24 hours before a Subscription instance expires.
-   For subscription ECS instances that are billed by bandwidth, change them to ECS instances billed by traffic first.

## Procedure {#section_ghs_tsm_vdb .section}

Complete these steps to change a public IP address of an ECS instance of the VPC network to an EIP:

1.  Log on to the ECS console.
2.  In the left-side navigation pane, click **Instances**.
3.  Select a region and find the target ECS instance.
4.  Click **More** \> **Network and Security Group** \> **Convert to EIP**.
5.  In the displayed dialog box, click **OK**.
6.  Refresh the list of instances.

    After the conversion, the original public IP address is labelled as **EIP**.

    ![](images/2253_en-US.png)


