# Associate an EIP with a secondary ENI in NAT mode

This topic describes how to associate an elastic IP address \(EIP\) with a secondary elastic network interface \(ENI\) in NAT mode. After you associate an EIP with a secondary ENI, the private IP address and public IP address that are assigned to the secondary ENI are available. In this case, the EIP is not displayed on the secondary ENI.

Before you associate an EIP with a secondary ENI in NAT mode, make sure that the following requirements are met:

-   A secondary ENI that is deployed in a virtual private cloud \(VPC\) is created. The secondary ENI and the EIP belong to the same region. For more information, see [Create an ENI](/intl.en-US/Network/Elastic Network Interfaces/Create an ENI.md).
-   The secondary ENI is not associated with an Elastic Compute Service \(ECS\) instance. If the secondary ENI is associated with an ECS instance, disassociate the secondary ENI from the ECS instance first. Then, associate the EIP with the secondary ENI in NAT mode and associate the secondary ENI with the ECS instance. For more information, see the [Unbind an ENI](/intl.en-US/Network/Elastic Network Interfaces/Unbind an ENI.md).

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select the type of instance. In this example, **Secondary ENI** is selected.|
    |**Binding mode**|Select **Normal**. In NAT mode:

    -   The number of EIPs that can be associated with a secondary ENI is based on the number of private IP addresses that are assigned to the secondary ENI.
    -   When an EIP is associated with a secondary ENI in NAT mode, both the private IP address and public IP address that are assigned to the secondary ENI are available.
    -   The EIP is not displayed in the operating system. To query the EIP, call the DescribeEipAddresses operation. For more information, see [DescribeEipAddresses](/intl.en-US/API reference/EIP/DescribeEipAddresses.md).
    -   The EIP does not support NAT application layer gateway \(ALG\) protocols such as H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), Real Time Streaming Protocol \(RTSP\), or Trivial File Transfer Protocol \(TFTP\). |
    |**Select an instance to bind**|Select the secondary ENI with which you want to associate the EIP. Make sure that the following requirements are met:

    -   The secondary ENI is deployed in a VPC.
    -   The secondary ENI and the EIP belong to the same region. |


