# Set the cut-through mode {#task_ajy_m5p_yfb .task}

This topic describes how to set the cut-through mode. When you associate an Elastic IP Address \(EIP\) with a secondary Elastic Network Interface \(ENI\), you can select the **Cut-Through Mode**. In this mode, the EIP replaces the private IP address of the ENI and the ENI becomes a pure Internet network interface. You can see the EIP in the network interface information of the operating system.

-   A secondary ENI is created. For more information, see [Create an ENI](../../../../reseller.en-US/Network/Elastic Network Interfaces/Create an ENI.md#).
-   The secondary ENI is not associated with any ECS instance.

    If the secondary ENI is already associated with an ECS instance, disassociate the ENI from the ECS instance first. For more information, see [Detach an ENI from an instance](../../../../reseller.en-US/Network/Elastic Network Interfaces/Detach an ENI from an instance.md#).


EIPs are a type of NAT IP address. Because the public IP address in the NAT mode exists in the NAT Gateway and is not on the network interface of the ECS instance, you cannot see the public IP address in the operating system and can only see the private IP address. This complicates the operation and maintenance, and the relationship between network interfaces/servers and public IP addresses must be maintained manually. Additionally, when the EIP is deployed as a NAT ALG \(NAT application layer gateway\), protocols such as H.323, SIP, DNS, and RTSP are not supported.

The **Cut-Through Mode** makes the EIP visible on the network interface and solves the preceding problems. In the cut-through mode:

-   The EIP replaces the private IP address of the ENI. The ENI becomes a pure Internet network interface and its intranet functions are not available any more.
-   You can see the EIP in the ENI of the operating system, and directly obtain the public IP address on the ENI by running the ifconfig or ipconfig command.
-   The EIP supports all IP protocols such as FTP, H.323, SIP, DNS, RTSP, and TFTP.

1.  Log on to the [VPC console](https://partners-intl.aliyun.com/login-required#/vpc).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  On the Elastic IP Addresses page, select the region of the target EIP. 

    **Note:** Currently, the cut-through mode is supported only in the China \(Zhangjiakou\), China \(Shenzhen\), China \(Hohhot\), Germany \(Frankfurt\), and US \(Virginia\) regions.

4.  Find the target EIP and click **Bind** in the **Actions** column. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155955353233373_en-US.png)

5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Required?|Description|
    |-------------|---------|-----------|
    |**Instance Type**|Yes|Select **Secondary ENI**.|
    |**Resource Group**|No|Select the resource group to which the EIP belongs.|
    |**Mode**|No|Select **Cut-Through Mode**.|
    |**Secondary ENI**|Yes|Select the secondary ENI to be associated with the EIP.|

    **Note:** Make sure that the ENI is not associated with any ECS instance.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155955353233380_en-US.png)

6.  Return to the EIP list page and click the ID of the associated ENI. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155955353233382_en-US.png)

7.  On the network interface list page, find the target ENI and click **Bind to Instance** to associate the ENI with an ECS instance. 

    **Note:** After you set the cut-through mode, you must enable the DHCP function of the ECS instance with which the ENI is associated to make the cut-through mode take effect.

8.  Log on to the ECS instance by using the associated EIP and check the network configurations of the ECS instance. 

    **Note:** Make sure that the security group rules of the ECS instance allow remote access.

    You can see that the local IP address of the ECS instance has changed to the associated EIP.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155955353233443_en-US.png)


