# Associate an EIP with a secondary ENI in cut-through mode

This topic describes how to associate an elastic IP address \(EIP\) with a secondary elastic network interface \(ENI\) in cut-through mode. After the association, the EIP replaces the private IP address of the secondary ENI, which changes the secondary ENI to a network interface controller \(NIC\). In this case, the EIP is displayed in the operating system.

Before you associate an EIP with a secondary ENI in cut-through mode, make sure that the following requirements are met:

-   A secondary ENI that is connected to a VPC network is created. The VPC-connected secondary ENI and the EIP to be associated are deployed in the same region. For more information, see [Create an ENI](/intl.en-US/Network/Elastic Network Interfaces/Create an ENI.md).
-   The secondary ENI is not associated with any ECS instances.

    If the secondary ENI is associated with an ECS instance, you must disassociate it from the ECS instance before you can associate an EIP with the secondary ENI in cut-through mode. For more information, see the [Detach an ENI from an instance](/intl.en-US/Network/Elastic Network Interfaces/Detach an ENI from an instance.md).


EIPs function as Network Address Translation \(NAT\) gateway IP addresses. In NAT mode, the public IP address is assigned to the gateway device instead of the NIC of the ECS instance. In the operating system, only the private IP address of the NIC of the ECS instance is displayed. The public IP address is not displayed. Administrators must manually maintain the mapping between the NIC or server and the public IP address. EIPs that are associated with resources in NAT mode do not support the H.323, SIP, DNS, or RTSP protocol.

To use an EIP that supports these protocols, you can associate the EIP with a secondary ENI in **cut-through mode**. In cut-through mode:

-   The EIP that is associated with a secondary ENI replaces the private IP address of the secondary ENI. The secondary ENI becomes an NIC. The private network features of the secondary ENI are not available.
-   The EIP is displayed on the ENI in the operating system. You can run the ifconfig or ipconfig command to query the public IP address of the secondary ENI.
-   EIPs in cut-through mode support all IP protocols, such as FTP, H.323, SIP, DNS, RTSP, and TFTP.
-   Each secondary ENI can be associated with only one EIP.

**Note:** If you associate a subscription EIP with a secondary ENI in cut-through mode, and the secondary ENI is associated with an ECS instance, the private network features are no longer available after the EIP is released. To restore the private network features of the secondary ENI, you must disassociate it from the ECS instance, and associate an EIP with the secondary ENI in cut-through mode.

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where your EIP is created.

    **Note:** The cut-through mode is supported in the following regions: China \(Hangzhou\), China \(Shanghai\), China Qingdao\), China \(Beijing\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Shenzhen\), China \(Chengdu\), Singapore \(Singapore\), Indonesia \(Jakarta\), Germany \(Frankfurt\), UK \(London\), and US \(Virginia\).

3.  On the **Elastic IP Addresses** page, find the EIP that you want to associate, and click **Bind Elastic IP Address to Resources** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters, and then click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **Secondary ENI**.|
    |**Binding Mode**|Select **Cut-Through Mode**.|
    |**Select an instance to bind**|Select the secondary ENI with which you want to associate the EIP.**Note:** Make sure that the selected secondary ENI is not associated with any ECS instance. |

5.  Return to the Elastic IP Addresses page and click the hyperlink of the associated ENI.

    ![Check the associated ENI.](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/9059039951/p33382.png)

6.  On the **Network Interfaces** page, click **Bind** in the **Actions** column to associate the ENI with an ECS instance.

    **Note:**

    -   The number of ENIs that can be associated with an ECS instance varies based on the type of the EIP. For more information, see the [Instance families](/intl.en-US/Instance/Instance families.md).
    -   After you associate the secondary ENI with an ECS instance, you must enable Dynamic Host Configuration Protocol \(DHCP\) and then restart the ENI for the cut-through mode to take effect.
    -   After the cut-through mode is set, the ECS instance automatically generates a route entry that uses the secondary ENI as the outbound interface. The priority of this route entry is lower than that of the route of the primary ENI. You can adjust the priorities of these route entries to meet your business requirements.
7.  Log on to the ECS instance by using the associated EIP and run the `ipconfig` command to view the network configuration of the ECS isntance.

    **Note:** Make sure that the security group rules of the ECS instance allow remote access.

    As shown in the following figure, the IPv4 address of the ECS instance is replaced by the associated EIP.

    ![Check the EIP that is associated with the ECS instance](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/7367409951/p33443.png)


