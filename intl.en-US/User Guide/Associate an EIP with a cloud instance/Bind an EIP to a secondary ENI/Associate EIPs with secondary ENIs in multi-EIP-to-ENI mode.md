# Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode

This topic describes how to associate multiple elastic IP addresses \(EIPs\) with a secondary elastic network interface \(ENI\) in multi-EIP-to-ENI mode. This mode allows you to use private and public IP addresses at the same time. You can view the status of the EIPs in the network interface controller \(NIC\) of the operating system.

Before you start, make sure that the following requirements are met:

-   Currently, multi-EIP-to-ENI mode is not open for all users, but only for who has already registered in public review.
-   A secondary ENI is created and deployed in a virtual private cloud \(VPC\). The secondary ENI and EIP are deployed in the same region. For more information, see [Create an ENI](/intl.en-US/Network/Elastic Network Interfaces/Create an ENI.md).
-   The secondary ENI is not associated with an ECS instance.

    If the secondary ENI is associated with an ECS instance, you must disassociate it from the ECS instance before you can associate an EIP with a secondary ENI in multi-EIP-to-ENI mode. For more information, see [Unbind an ENI](/intl.en-US/Network/Elastic Network Interfaces/Unbind an ENI.md).


EIPs serve as Network Address Translation \(NAT\) IP addresses. In NAT mode, the public IP address is assigned to the gateway device instead of the NIC of the ECS instance. In the operating system, only the private IP address of the NIC of the ECS instance is displayed. The public IP address is not displayed. In this case, administrators must manually maintain the mapping between the NIC or server and the public IP address. EIPs that are associated with resources in NAT mode do not support the H.323, SIP, DNS, and RTSP protocols.

In **multi-EIP-to-ENI mode**, EIPs are displayed on the NIC. In multi-EIP-to-ENI mode:

-   The secondary ENI supports both private and public IP addresses.
-   EIPs are displayed on the NIC. After you configure a static IP address in the operating system, you can run the ifconfig or ipconfig command to query the public address of the ENI.
-   EIPs that are associated with a secondary ENI in multi-EIP-to-ENI mode support all Internet protocols, such as H.323, SIP, DNS, RTSP, FTP, and TFTP.
-   Each secondary ENI can be associated with at most 10 EIPs.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

    **Note:** The multi-EIP-to-ENI mode is supported in the following regions: China \(Shenzhen\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou\), China \(Chengdu\), Singapore \(Singapore\), Germany \(Frankfurt\), India \(Mumbai\), US \(Virginia\), and UK \(London\).

3.  On the **Elastic IP Addresses** page, find the EIP that you want to associate, and click **Bind Resources** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters, and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|The type of the instance. Select **Secondary ENI**.|
    |**Mode**|Select **Multi-EIP to ENI Mode**.|
    |**Select an instance to bind**|Select the secondary ENI to be associated with the EIP.|

5.  To associate more EIPs with the secondary ENI, repeat the preceding steps.

6.  Return to the Elastic IP Addresses page and click the ID of the associated ENI.

    ![View the associated ENI](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9059039951/p33382.png)

7.  On the Network Interfaces page, click **Bind to Instance** to associate the ENI with an ECS instance.

    **Note:**

    -   In the multi-EIP-to-ENI mode, you can associate an EIP with the secondary ENI, and then associate the secondary ENI with an ECS instance. Supported ECS instance families are: ecs.c5-618, ecs.d1ne, ecs.db11-se1ne, ecs.ebma1, ecs.ebmc4, ecs.ebmg4, ecs.ebmg5, ecs.ebmg5ne, ecs.ebmgn5i, ecs.ebmgn5t, ecs.ebmhfg4, ecs.ebmhfg5, ecs.ebmi2, ecs.ebmi3, ecs.ebmr4, ecs.ebmr5, ecs.elmd1ne, ecs.elmdb, ecs.f1, ecs.f2, ecs.g5-618, ecs.gn3, ecs.gn5d, ecs.gn5i, ecs.gn5t, ecs.gn6p, ecs.gn6v, ecs.i2, ecs.r1, ecs.re4, ecs.re4e, ecs.sccg5, ecs.sccgn6, ecs.scch5, ecs.x1.i2, ecs.x1.i5, ecs.x1.i6, ecs.x1.i8, ecs.g5, ecs.c5, ecs.r5, ecs.t5, ecs.sn2ne, ecs.se1ne, and ecs.sn1ne. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).
    -   After you associate EIPs with the secondary ENI in the multi-EIP-to-ENI mode, you must enable DHCP for the ECS instance that is associated with the secondary ENI. Otherwise, the multi-EIP-to-ENI mode does not take effect.
8.  You can call the DescribeEipGatewayInfo operation to query the gateway and subnet mask information about the EIP. For more information, see [DescribeEipGatewayInfo](/intl.en-US/API reference/EIP/DescribeEipGatewayInfo.md).

9.  Log on to the ECS instance and configure EIPs for the ECS instance. For more information, see [Assign a secondary private IP address to a Windows instance](/intl.en-US/Network/Elastic Network Interfaces/Assign secondary private IP addresses.md) and [Assign a secondary private IP address to a Linux instance](/intl.en-US/Network/Elastic Network Interfaces/Assign secondary private IP addresses.md).

    **Note:** When you configure EIPs for an ECS instance as described in the preceding topics, replace the secondary private IP address with an EIP, and replace the gateway and subnet mask of the secondary private IP address with those of the EIP.

    After you configure the EIP, you can run the ifconfig or ipconfig command to query the EIP.


