# Associate EIPs with secondary ENIs in multi-EIP to ENI mode \(new applications are not accepted\)

If you have already obtained the permissions to use the multi-EIP to ENI mode, you can associate elastic IP addresses \(EIPs\) with a secondary elastic network interface \(ENI\) in multi-EIP to ENI mode. After EIPs are associated with a secondary ENI in multi-EIP to ENI mode, the private IP address of the ENI and the EIPs are both available. You can view the EIPs in the ENI information of the operating system.

**Note:** Alibaba Cloud no longer accepts new applications for using the multi-EIP to ENI mode. If you have already been authorized to use this feature, you can associate EIPs with a secondary ENI in multi-EIP to ENI mode.

## Prerequisites

-   A secondary ENI is created and deployed in a virtual private cloud \(VPC\). The secondary ENI and the EIPs that you want to associate are deployed in the same region. For more information, see [t9734.md\#](/intl.en-US/Network/Elastic Network Interfaces/Create an ENI.md).
-   The secondary ENI is not associated with an Elastic Compute Service \(ECS\) instance.

    If the secondary ENI is associated with an ECS instance, you must disassociate the secondary ENI from the ECS instance before you can associate EIPs with the secondary ENI in multi-EIP to ENI mode. For more information, see [Unbind an ENI](/intl.en-US/Network/Elastic Network Interfaces/Unbind an ENI.md).


## Background information

EIPs function as Network Address Translation \(NAT\) IP addresses. In NAT mode, public IP addresses are assigned to gateways instead of the network interface controllers \(NICs\) of ECS instances. In the operating system, only private IP addresses of NICs are displayed. Public IP addresses are not displayed. Administrators must manually maintain the mapping between NICs or servers and public IP addresses. In addition, EIPs that are associated with resources in NAT mode do not support the H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), or Real Time Streaming Protocol \(RTSP\) protocol.

To resolve this issue, you can associate EIPs with a secondary ENI in **multi-EIP to ENI mode**. This way, the EIPs are displayed in the ENI information of the operating system. After you associate EIPs with a secondary ENI in multi-EIP to ENI mode:

-   The private network features of the secondary ENI are still available.
-   The EIPs are displayed in the ENI information of the operating system. After you configure static IP addresses in the operating system, you can run the ifconfig or ipconfig command to query the public IP addresses of the ENI.
-   EIPs support all IP protocols, including FTP, H.323, SIP, DNS, RTSP, and TFTP.
-   A secondary ENI can be associated with at most 10 EIPs.

## Procedure

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

    **Note:** The multi-EIP to ENI mode is supported in the following regions: China \(Shenzhen\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou\), China \(Chengdu\), Singapore \(Singapore\), Germany \(Frankfurt\), India \(Mumbai\), US \(Virginia\), and UK \(London\).

3.  On the **Elastic IP Addresses** page, find the EIP that you want to associate and click **Bind Resources** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **Secondary ENI**.|
    |**Mode**|Select **Multi-EIP to ENI Mode**.|
    |**Select an instance to bind**|Select the secondary ENI to be associated with the EIP.|

5.  To associate more EIPs with the secondary ENI, repeat the preceding steps.

6.  Return to the Elastic IP Addresses page and click the ID of the associated ENI.

    ![View the associated ENI](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9059039951/p33382.png)

7.  On the Network Interfaces page, click **Bind to Instance** to associate the ENI with an ECS instance.

    **Note:**

    -   After you associate EIPs with a secondary ENI in multi-EIP to ENI mode, you can associate the secondary ENI with an ECS instance. Make sure that the ECS instance belongs to one of the following instance families: ecs.c5-618, ecs.d1ne, ecs.db11-se1ne, ecs.ebma1, ecs.ebmc4, ecs.ebmg4, ecs.ebmg5, ecs.ebmg5ne, ecs.ebmgn5i, ecs.ebmgn5t, ecs.ebmhfg4, ecs.ebmhfg5, ecs.ebmi2, ecs.ebmi3, ecs.ebmr4, ecs.ebmr5, ecs.elmd1ne, ecs.elmdb, ecs.f1, ecs.f2, ecs.g5-618, ecs.gn3, ecs.gn5d, ecs.gn5i, ecs.gn5t, ecs.gn6p, ecs.gn6v, ecs.i2, ecs.r1, ecs.re4, ecs.re4e, ecs.sccg5, ecs.sccgn6, ecs.scch5, ecs.x1.i2, ecs.x1.i5, ecs.x1.i6, ecs.x1.i8, ecs.g5, ecs.c5, ecs.r5, ecs.t5, ecs.sn2ne, ecs.se1ne, and ecs.sn1ne. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).
    -   After you associate EIPs with the secondary ENI in the multi-EIP to ENI mode, you must enable Dynamic Host Configuration Protocol \(DHCP\) for the ECS instance. Otherwise, the multi-EIP to ENI mode does not take effect.
8.  You can call the DescribeEipGatewayInfo operation to query the gateway and subnet mask of an EIP. For more information, see [DescribeEipGatewayInfo](/intl.en-US/API reference/EIP/DescribeEipGatewayInfo.md).

9.  Log on to the ECS instance and configure the EIPs for the ECS instance. For more information, see [Configure EIPs for an ECS instance that runs Windows](/intl.en-US/Network/Elastic Network Interfaces/Assign secondary private IP addresses.md) and [Configure EIPs for an ECS instance that runs Linux](/intl.en-US/Network/Elastic Network Interfaces/Assign secondary private IP addresses.md).

    **Note:** The preceding topics describe how to configure secondary private IP addresses for ECS instances. You can follow the same procedure to configure EIPs for ECS instances. However, you must specify the gateways and subnet masks of EIPs instead of the gateways and subnet masks of secondary private IP addresses.

    After you configure EIPs for the ECS instances, you can run the ifconfig or ipconfig command to query the EIPs.


