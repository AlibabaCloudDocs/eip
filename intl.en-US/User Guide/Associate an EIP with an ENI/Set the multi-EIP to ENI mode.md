# Set the multi-EIP to ENI mode {#task_268616 .task}

This topic describes how to set the multi-EIP to ENI mode. When you associate an Elastic IP Address \(EIP\) with a secondary Elastic Network Interface \(ENI\), you can select the **Multi-EIP to ENI Mode**. In this mode, the private and public IP addresses of the ENI are available at the same time, and the EIP is invisible to the ENI.

-   A secondary ENI is created. For more information, see [Create an ENI](../../../../reseller.en-US/Network/Elastic Network Interfaces/Create an ENI.md#).
-   The secondary ENI is not associated with any EIP in the NAT or cut-through mode.

    If the secondary ENI is already associated with an EIP, disassociate the EIP first.

-   Currently, the multi-EIP to ENI mode is supported only in the China \(Beijing\), China \(Zhangjiakou\), Singapore, Germany \(Frankfurt\), and India \(Mumbai\) regions.

EIPs are a type of NAT IP addresses. Because the public IP address in the NAT mode exists in the NAT Gateway and is not on the network interface of the ECS instance, you cannot see the public IP address in the operating system and can only see the private IP address. This complicates the operation and maintenance, and the relationship between network interfaces or servers and public IP addresses must be maintained manually. Additionally, when the EIP is deployed as a NAT ALG \(NAT application layer gateway\), protocols such as H.323, SIP, DNS, and RTSP are not supported.

The **Multi-EIP to ENI Mode** makes the EIP visible on the network interface and solves the preceding problems. In the multi-EIP to ENI mode:

-   The intranet function of the secondary ENI is still available.
-   The EIP is visible to the ENI. After the operating system is configured with a static IP address, you can run the ifconfig or ipconfig command to obtain the public IP address of the ENI.
-   The EIP supports all IP protocols such as FTP, H.323, SIP, DNS, RTSP, and TFTP.

1.  Log on to the [VPC console](https://partners-intl.aliyun.com/login-required#/vpc).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  On the Elastic IP Addresses page, select the region of the target EIP.
4.  Locate the target EIP and click **Bind** in the **Actions** column. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155928209533373_en-US.png)

5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Required?|Description|
    |-------------|---------|-----------|
    |**Instance Type**|Yes|Select **Secondary ENI**.|
    |**Mode**|No|Select **Multi-EIP to ENI Mode**.|
    |**Secondary ENI**|Yes|Select the secondary ENI to be associated with the EIP.|

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/221990/155928209547675_en-US.png)

6.  Repeat the preceding steps to associate multiple EIPs to the secondary ENI.
7.  Return to the EIP list page and click the ID of the associated ENI. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155928209533382_en-US.png)

8.  On the Network Interfaces page, locate the target ENI and click **Bind to Instance** to associate the ENI to an ECS instance. 

    **Note:** After you set the multi-EIP to ENI mode, you must enable the DHCP function of the ECS instance with which the ENI is associated to make the multi-EIP to ENI mode take effect.

9.  Log on to the ECS instance and configure multiple EIPs for the ECS instance. For more information, see [Configure an EIP for a Windows instance](../../../../reseller.en-US/Network/Elastic Network Interfaces/Assign multiple secondary private IP addresses.md#section_y4b_krk_ggb) and [Configure an EIP for a Linux instance](../../../../reseller.en-US/Network/Elastic Network Interfaces/Assign multiple secondary private IP addresses.md#section_b2x_hlb_3gb). 

    **Note:** To configure an EIP for an ECS instance, you must open a ticket to obtain the EIP gateway and subnet mask.

    After configuring EIPs, you can run the ifconfig or ipconfig command to view the configured EIPs.


