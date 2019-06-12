# Set the NAT mode {#task_268615 .task}

This topic describes how to set the NAT mode. When you associate an Elastic IP Address \(EIP\) with a secondary Elastic Network Interface \(ENI\), you can select the **NAT Mode**. In the NAT mode, the private and public IP addresses of the ENI are available at the same time, and the EIP is invisible to the ENI.

A secondary ENI is created. For more information, see [Create an ENI](../../../../reseller.en-US/Network/Elastic Network Interfaces/Create an ENI.md#).

In the NAT mode:

-   The EIP is associated with the ENI in the NAT mode. The private and public IP addresses of the ENI are available at the same time.
-   The EIP is invisible to the operating system. If you need to know the public IP address associated with the ENI, you must call the DescribeEipAddresses API. For more information, see [../../../../dita-oss-bucket/SP\_22/DNVPC11886329/EN-US\_TP\_2492.md\#](../../../../reseller.en-US/API reference/EIP/DescribeEipAddresses.md#).
-   Protocols that require NAT ALG are not supported, such as H.323, SIP, DNS, RTSP, and TFTP.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Required?|Description|
    |:------------|:--------|:----------|
    |Instance Type|Yes|Select **Secondary ENI**.|
    |Resource Group|No|Select the resource group to which the EIP belongs.|
    |Mode|No|Select **NAT Mode**.|
    |Secondary ENI|Yes|Select the secondary ENI to be associated with the EIP.|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221988/156030756547638_en-US.png)


