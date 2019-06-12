# Set the Multi-EIP to ENI mode {#task_268616 .task}

This topic describes how to set the Multi-EIP to ENI mode. When you associate an Elastic IP Address \(EIP\) with a secondary Elastic Network Interface \(ENI\), you can select the **Multi-EIP to ENI Mode**. In this mode, the private and public IP addresses of the ENI are available at the same time. You can see the EIP in the network interface information of the operating system.

-   A secondary ENI is created. For more information, see [Create an ENI](../../../../reseller.en-US/Network/Elastic Network Interfaces/Create an ENI.md#).
-   The secondary ENI is not associated with any EIP in the NAT or cut-through mode.

    If the secondary ENI is already associated with an EIP, disassociate the EIP first. For more information, see [Disassociate an EIP](reseller.en-US/User Guide/Disassociate an EIP from a cloud instance.md#).


EIPs are a type of NAT IP address. Because the public IP address in the NAT mode exists in the NAT Gateway and is not on the network interface of the ECS instance, you cannot see the public IP address in the operating system and can only see the private IP address. This complicates the operation and maintenance, and the relationship between network interfaces/servers and public IP addresses must be maintained manually. Additionally, when the EIP is deployed as a NAT ALG \(NAT application layer gateway\), protocols such as H.323, SIP, DNS, and RTSP are not supported.

The **Multi-EIP to ENI Mode** makes the EIP visible on the network interface and solves the preceding problems. In the Multi-EIP to ENI mode:

-   The intranet function of the secondary ENI is still available.
-   The EIP is visible to the ENI. After the operating system is configured with a static IP address, you can run the ifconfig or ipconfig command to obtain the public IP address of the ENI.
-   The EIP supports all IP protocols such as FTP, H.323, SIP, DNS, RTSP, and TFTP.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP. 

    **Note:** Currently, the Multi-EIP to ENI mode is supported only in the China \(Zhangjiakou\), Singapore, Germany \(Frankfurt\), India \(Mumbai\), and UK \(London\) regions.

4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Required?|Description|
    |-------------|---------|-----------|
    |**Instance Type**|Yes|Select **Secondary ENI**.|
    |**Mode**|No|Select **Multi-EIP to ENI Mode**.|
    |**Secondary ENI**|Yes|Select the secondary ENI to be associated with the EIP.|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221990/156032338547675_en-US.png)

6.  Repeat the preceding steps to associate multiple EIPs with the secondary ENI.
7.  Return to the EIP list page and click the ID of the associated ENI. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/156032338533382_en-US.png)

8.  On the Network Interfaces page, locate the target ENI and click **Bind to Instance** to associate the ENI with an ECS instance. 

    **Note:** After you set the Multi-EIP to ENI mode, you must enable the DHCP function of the ECS instance with which the ENI is associated to make the Multi-EIP to ENI mode take effect.

9.  Log on to the ECS instance and configure multiple EIPs for the ECS instance. For more information, see [Configure an EIP for a Windows instance](../../../../reseller.en-US/Network/Elastic Network Interfaces/Assign a secondary private IP address.md#section_y4b_krk_ggb) and [Configure an EIP for a Linux instance](../../../../reseller.en-US/Network/Elastic Network Interfaces/Assign a secondary private IP address.md#section_b2x_hlb_3gb). 

    **Note:** To configure an EIP for an ECS instance, you must open a ticket to obtain the EIP gateway and subnet mask.

    After configuring EIPs, you can run the ifconfig or ipconfig command to view the configured EIPs.


