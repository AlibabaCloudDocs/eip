# Convert an automatically assigned public IP address to an EIP for a VPC-connected ECS instance

This topic describes how to convert an automatically assigned public IP address to an elastic IP address \(EIP\) for an Elastic Compute Service \(ECS\) instance that is deployed in a Virtual Private Cloud \(VPC\) network. After the conversion, you can disassociate the EIP from the ECS instance, and you can associate the EIP with the ECS instance again at any time. This allows you to manage public IP addresses in a flexible way.

A ECS instance is created and assigned a public IP address. For more information, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).

## Overview of public IP addresses

If an ECS instance requires access to the Internet, you must configure a public IP address and Internet bandwidth for the ECS instance. Alibaba Cloud provides the following types of public IP addresses:

-   Automatically assigned public IP addresses

    When you create a VPC-connected ECS instance, you can choose to use the public IP address that is automatically assigned by the system. You cannot disassociate this public IP address from the ECS instance.

-   EIP

    An EIP is a public IP address that can be purchased and owned independently. You can associate an EIP with a VPC-connected ECS instance, VPC-connected private Server Load Balancer \(SLB\), VPC-connected secondary elastic network interface \(ENI\), Network Address Translation \(NAT\) gateway, or high-availability virtual IP address \(HAVIP\). You can also use EIP bandwidth plans and data transfer plans to reduce data transfer costs.


Both public IP addresses and EIPs apply multi-line BGP network which Alibaba uses to provide quality Internet services. The biggest difference between a public IP address and an EIP is whether it can be disassociated from an ECS instance. You can disassociate an EIP from an ECS instance at any time and re-associate it. However, you cannot disassociate a public IP address from an ECS instance.

## Limits

To convert the public IP address of an ECS instance to an EIP, note the following limits:

-   If the billing method of the ECS instance is pay-as-you-go, your account must not have overdue payments.
-   If the billing method of the ECS instance is subscription, you cannot convert the public IP address within 24 hours before the expiration date.
-   If the billing method of the ECS instance is subscription, the Internet bandwidth must be billed on a **pay-by-data-transfer** basis. If the Internet bandwidth is billed on a **pay-by-bandwidth** basis, you can log on to the console and choose upgrade or downgrade to change the billing method of the Internet bandwidth to pay-by-traffic, and then convert the public IP address to an EIP. For more information, see [Overview of instance upgrade and downgrade](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).
-   Only VPC-connected ECS instances that are in the Stopped or Running state are supported. The VPC-connected ECS instances in other states cannot be converted.
-   You can convert only the automatically assigned public IP address of an ECS instance to an EIP.
-   You cannot convert the public IP address of an ECS instance to an EIP if the instance has a pending upgrade or downgrade task in the queue.

## Considerations

Before you convert an automatically assigned public IP address of an ECS instance to an EIP, note that:

-   For a VPC-connected ECS instance, the conversion process does not cause transient connection errors.
-   During the conversion process, the public IP address can be retained for the ECS instance.
-   The conversion does not change the billing method of the Internet bandwidth.
-   After the public IP address is converted to an EIP for a VPC-connected ECS instance, the EIP cannot be converted back to the public IP address.
-   After the conversion, the EIP is billed independently, and a separate bill is generated. For more information about EIP billing, see [Overview](/intl.en-US/Pricing/Overview.md). In **User Center**, select [Usage Record](https://billing.console.aliyun.com/#/usage/record), and select to export the bill statements of the **Elastic IP**.

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

3.  In the top navigation bar, select the region where the ECS instance is deployed.

4.  On the **Instances** page, find the ECS instance that you want to manage, choose **More** \> **Network and Security Group** \> **Convert to EIP** in the **Actions** column.

    ![Convert an automatically assigned public IP address to an EIP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8815679161/p88779.png)

5.  In message that appears, click **OK**.

6.  Refresh the instance list.

    After the conversion, the original public IP address is labeled as **EIP**.

    ![The automatically assigned public IP address is successfully converted to an EIP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2905958951/p88777.png)


**Related topics**  


[ConvertNatPublicIpToEip](/intl.en-US/API Reference/Networks/ConvertNatPublicIpToEip.md)

