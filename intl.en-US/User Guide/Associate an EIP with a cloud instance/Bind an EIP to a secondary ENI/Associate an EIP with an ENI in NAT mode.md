# Associate an EIP with an ENI in NAT mode

This topic describes how to associate an elastic IP address \(EIP\) with a secondary elastic network interface \(ENI\) in NAT mode. This allows you to use the public and private IP addresses of the ENI at the same time. In this case, the EIP is not displayed on the secondary ENI.

Before you associate an EIP with a secondary ENI in NAT mode, make sure that the following requirements are met:

-   A VPC-connected secondary ENI is created. The secondary ENI and the EIP to be associated are deployed in the same region. For more information, see [Create an ENI](/intl.en-US/Network/Elastic Network Interfaces/Create an ENI.md).
-   The secondary ENI with which you want to associate an EIP is not associated with any Elastic Compute Service \(ECS\) instance.

    If the secondary ENI is associated with an ECS instance, you must disassociate it from the ECS instance before you can associate the secondary EN with an EIP. For more information, see the [Detach an ENI from an instance](/intl.en-US/Network/Elastic Network Interfaces/Detach an ENI from an instance.md).


1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where the EIP is created.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to associate, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **Secondary ENI**.|
    |**Resource Group**|Select the resource group to which the secondary ENI belongs.|
    |**Binding Mode**|Select **NAT Mode**.In NAT Mode:

    -   The number of EIPs that can be associated with a secondary ENI depends on the number of the private IP addresses of the secondary ENI.
    -   After you associate a secondary ENI with an EIP, you can use the public and private IP addresses of the secondary ENI at the same time.
    -   The EIP that is associated with a secondary ENI in NAT mode is not displayed in the operating system. To query the EIP, call the DescribeEipAddresses operation. For more information, see [DescribeEipAddresses](/intl.en-US/API reference/EIP/DescribeEipAddresses.md).
    -   An EIP that is associated with a secondary ENI in NAT mode does not support NAT ALG protocols, such as H.323, SIP, DNS, RTSP, and TFTP. |
    |**Select an instance to bind**|Select the secondary ENI to be associated with the EIP.Make sure that the following requirements are met:

    -   The secondary ENI is deployed in a Virtual Private Cloud \(VPC\) network.
    -   The secondary ENI and the EIP are created in the same region. |


