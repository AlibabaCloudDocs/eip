# Configure the cut-through mode {#task_ajy_m5p_yfb .task}

When you bind an Elastic IP Address \(EIP\) to a secondary Elastic Network Interface \(ENI\), you can select the **Cut-Through Mode**. In this mode, the EIP replaces the private IP address of the ENI, and the ENI becomes a pure Internet network interface. You can view the EIP in the network interface information of the operating system.

-   A secondary ENI is created. For more information, see [Create an ENI](../../../../reseller.en-US/Network/Elastic Network Interfaces/Create an ENI.md#).
-   The secondary ENI is not bound to any ECS instance.

    If the secondary ENI is bound to an ECS instance, unbind the ENI from the instance first. For more information, see [Detach an ENI from an instance](../../../../reseller.en-US/Network/Elastic Network Interfaces/Detach an ENI from an instance.md#).

-   The EIP that you create is a Pay-As-You-Go-billed instance. The cut-through mode is not supported by Subscription-billed EIPs.

An EIP is a NAT IP address by nature. The public IP address of the NAT mode exists in the NAT Gateway and is not on the network interface of the ECS instance. Therefore, you cannot see the public IP address in the operating system and can only see the private IP address of the network interface. This complicates O&M operations by requiring you to manually maintain the relationship between the network interface or server and public IP addresses. Furthermore, when the EIP is deployed as NAT ALG \(NAT application layer gateway\), protocols such as H.323, SIP, DNS, and RTSP are not supported.

The **Cut-Through Mode** makes the EIP visible on the network interface and solves the preceding problems.

-   The EIP replaces the private IP address of the ENI. The ENI becomes a pure Internet network interface, and its intranet functions are not available any more.
-   You can see the EIP in the ENI of the operating system, and directly obtain the public IP address on the ENI by using ifconfig/ipconfig.
-   EIP supports all major IP protocols such as FTP, H.323, SIP, DNS, RTSP, and TFTP.

1.  Log on to the [VPC console](https://partners-intl.aliyun.com/login-required#/vpc).
2.  In the left-side navigation pane, click **Elastic IP Addresses** and select the region of the EIP.
3.  Locate the target EIP, and then click **Bind**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155660916733373_en-US.png)

4.  On the displayed page, complete the following steps: 
    1.  **Instance Type**: Select **Secondary ENI**.
    2.  **Resource Group**: Select the resource group that the EIP belongs to.
    3.  **Mode**: Select **Cut-Through Mode**.
    4.  **Secondary ENI**: Select the ENI to bind. 

        **Note:** Make sure that the ENI is not bound to any ECS instance.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155660916733380_en-US.png)

5.  Then click the link of the bound ENI. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155660916733382_en-US.png)

6.  On the page of network interfaces, click **Bind to Instance** to bind the ENI to the ECS instance. 

    **Note:** To make the cut-through mode take effect, you must enable the DHCP function for the ECS instance to which the secondary ENI is bound.

7.  Use the bound EIP to log on to the ECS instance to view the network configurations of the instance. 

    **Note:** Make sure the security group rules of the ECS instance allow remote access.

    You can see that the local IP address of the instance has changed to the EIP address.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155660916733443_en-US.png)


