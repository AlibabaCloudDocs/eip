# Convert an ECS public IP address to an EIP {#concept_jgg_1rm_vdb .concept}

This topic describes how to convert the assigned public IP address of an ECS instance to an Elastic IP address \(EIP\).

**Note:** After the ECS public IP address is converted, you cannot convert it back.

## Public IP addresses {#section_vrf_5rm_vdb .section}

A public IP address and Internet bandwidth are required for an ECS instance if you want users to access the application deployed on the ECS instance over the Internet.

Alibaba Cloud provides the following two types of public IP addresses:

-   ECS public IP address

    If you choose to use a public IP address allocated by the system when you create an ECS instance of the VPC network, the public IP address is permanently associated with the corresponding ECS instance \(that is, it cannot be disassociated from the ECS instance\).

-   EIP

    An EIP is a public IP address resource that can be purchased and held independently. Currently, you can associate an EIP with an ECS instance of the VPC network, an intranet Server Load Balancer \(SLB\) instance of the VPC network, or a NAT Gateway.


Both ECS public IP addresses and EIPs use the high-quality multi-line BGP network of Alibaba Cloud to help your application provide external services over the Internet. You can disassociate an EIP from an ECS instance, and re-associate it with the ECS instance when required. However, you cannot disassociate an ECS public IP address from an ECS instance.

## Benefits of EIPs {#section_abd_gsm_vdb .section}

ECS public IP addresses will be gradually replaced by EIPs. EIPs have the following benefits:

-   Flexibly defend against DDoS attacks

    If your server is under DDoS attacks, you can disassociate the EIP from the attacked ECS instance and re-associate a new EIP with the ECS instance. You can additionally combine this measure with Anti-DDoS Pro to defend DDoS attacks.

-   Simplify system and application extensions

    If you need to expand your application, you may need to deploy the application on multiple ECS instances and use SLB to distribute traffic to these ECS instances. For this scenario, you can disassociate the EIP from the ECS instances and associate it with the SLB instance of the VPC network. This architecture change has no impact to user experience.

-   Reduce costs

    If you add EIPs to an Internet Shared Bandwidth instance, the Internet costs can be greatly reduced.

    For more information, see [How to save the Internet cost?](../../../../reseller.en-US/Best practices/How to save the Internet cost?.md#)

-   Simplify access control

    You can open a ticket to apply for continuous public IP addresses to simplify network access control.


## Limits {#section_abt_psm_vdb .section}

Before you convert an ECS public IP address to an EIP, make sure that the following requirements are met:

-   The target ECS instance must be of the VPC network type and have a public IP address.
-   The target ECS instance must be in the Stopped or Running state.
-   No pending specification adjustments for the target ECS instance exist in the Billing console.
-   The expiration time of the target ECS instance is more than 24 hours from the current time.
-   The billing method of the target ECS instance is Subscription and is billed by traffic.
-   The ECS public IP address can only be converted to an EIP.

## Note {#section_u93_s21_tkm .section}

Note the following before you convert an ECS public IP address to an EIP:

-   The Internet access of the ECS instance is not affected and no network disconnections will occur when the IP address is in a state of conversion.
-   You can retain the original IP address with only the type of the IP address changed.
-   The billing method of the Internet bandwidth remains unchanged.
-   After the IP address is converted to an EIP, the EIP is charged and billed separately. For more information about the billing method of EIPs, see [Billing method](../../../../reseller.en-US/Pricing/Billing method.md#). You can view the bill of the EIP in the [User Center](https://usercenter2.aliyun.com/home) by choosing **Purchases record** \> **Usage record** and then exporting the bill of **EIP**.

## Procedure {#section_ghs_tsm_vdb .section}

To convert an ECS public IP address to an EIP, follow these steps:

1.  Log on to the ECS console.
2.  In the left-side navigation pane, click **Instances**.
3.  Select a region and find the target ECS instance.
4.  Choose **More** \> **Network and Security Group** \> **Convert to EIP**.
5.  In the displayed dialog box, click **OK**.
6.  Refresh the list of ECS instances.

    After the the public IP address is converted to an EIP, the original public IP address is labelled as **EIP**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12809/15587484312253_en-US.png)


