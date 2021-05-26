# Convert the static public IP address of an ECS instance in a VPC to an EIP

This topic describes how to convert the static public IP address of an Elastic Compute Service \(ECS\) instance in a virtual private cloud \(VPC\) to an elastic IP address \(EIP\). After the conversion, you can disassociate the EIP from the ECS instance. Then, you can associate the EIP with the ECS instance again or another ECS instance. EIPs allow you to manage public IP addresses in a flexible way.

An ECS instance is created and assigned a static public IP address. For more information, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).

## Overview of public IP addresses

If an ECS instance requires access to the Internet, you must allocate a public IP address and Internet bandwidth for the ECS instance. Alibaba Cloud provides the following types of public IP addresses:

-   Static public IP addresses

    When you create an ECS instance in a VPC, you can specify Assign Public IPv4 Address for the ECS instance. After the ECS instance is created, the system automatically assigns a static public IP address to the ECS instance. You cannot disassociate this public IP address from the ECS instance.

-   EIPs

    An EIP is a public IP address that you can purchase and use as an independent resource. You can associate EIPs with ECS instances, internal-facing Server Load Balancer \(SLB\) instances, secondary elastic network interfaces \(ENIs\), NAT gateways, and high-availability virtual IP addresses \(HAVIPs\). The ECS instances, internal-facing SLB instances, and secondary ENIs must be deployed in VPCs. In addition, you can use EIP bandwidth plans and data transfer plans to reduce costs of Internet data transfer.


Both static public IP addresses and EIPs apply multi-line BGP network that Alibaba Cloud uses to provide high-quality Internet services. The main difference between a static public IP address and an EIP is whether the IP address can be disassociated from an ECS instance. You can disassociate an EIP from an ECS instance at any time. Then, you can associate the EIP with the ECS instance again based on your business requirements. However, you cannot disassociate a static public IP address from an ECS instance.

## Limits

Before you convert the static public IP address of an ECS instance to an EIP, take note of the following limits:

-   If the ECS instance is billed on a pay-as-you-go basis, make sure that your account does not have overdue payments.
-   If the ECS instance is billed on a subscription basis, you cannot convert the static public IP address within 24 hours before the ECS instance expires.
-   If the ECS instance is billed on a subscription basis, make sure that the Internet bandwidth is billed on a **pay-by-data-transfer** basis. If the Internet bandwidth is billed on a **pay-by-bandwidth** basis, you must modify the billing method of the Internet bandwidth before you can convert the static public IP address. For more information, see [Overview of instance upgrade and downgrade](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).
-   You can convert only the static public IP address of an ECS instance that is deployed in a VPC. In addition, the ECS instance must be in the Stopped or Running state. ECS instances in other states do not support the operation.
-   You can convert the static public IP address of an ECS instance only to an EIP.
-   You cannot convert the static public IP address of an ECS instance to an EIP if the ECS instance has a pending upgrade or downgrade task in the queue.

## Considerations

Before you convert the static public IP address of an ECS instance to an EIP, take note of the following items:

-   When you convert the static public IP address of an ECS instance in a VPC to an EIP, connections to the ECS instance from the Internet are not interrupted.
-   After the static public IP address is converted to an EIP, the EIP cannot be converted back to the static public IP address.
-   During the conversion, the public IP address is preserved. After the conversion, the public IP address becomes the IP address of the EIP.
-   After the conversion, the billing method of the Internet bandwidth that the ECS instance uses is not changed. You are charged on a pay-bay-data-transfer basis.
-   After the conversion, the unit price of Internet data transfer is not changed. The EIP is automatically associated with the ECS instance. You are not charged a configuration fee for the EIP. The billing of the EIP and the ECS instance are independent of each other. The system generates separate bills for the EIP and the ECS instance. For more information about EIP billing, see[Overview](/intl.en-US/Pricing/Overview.md). Go to **Billing Management**, click [Usage Records](https://billing.console.aliyun.com/#/usage/record), and export the bills of the **EIP**.

## Procedure

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

3.  In the top navigation bar, select the region where the ECS instance is deployed.

4.  On the **Instances** page, find the ECS instance that you want to manage and choose **More** \> **Network and Security Group** \> **Convert to EIP** in the **Actions** column.

    ![Convert the static public IP address to an EIP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8815679161/p88779.png)

5.  In the message that appears, click **OK**.

6.  Refresh the ECS instance list.

    After the conversion, the IP address is labeled as **EIP**.

    ![The static public IP address is converted to an EIP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2905958951/p88777.png)


**Related topics**  


[ConvertNatPublicIpToEip](/intl.en-US/API Reference/Networks/ConvertNatPublicIpToEip.md)

