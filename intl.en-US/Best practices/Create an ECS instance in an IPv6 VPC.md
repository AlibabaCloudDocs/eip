# Create an ECS instance in an IPv6 VPC

This topic describes how to create a virtual private cloud \(VPC\) with an IPv6 CIDR block and create an Elastic Compute Service \(ECS\) instance assigned with an IPv6 address in the VPC.

**Note:** VPCs that simultaneously support IPv4 and IPv6 CIDR blocks are in public preview and available only in the following regions: China \(Hangzhou\), China \(Shanghai\), China \(Shenzhen\), China \(Beijing\), China \(Hohhot\), China \(Chengdu\), China \(Hong Kong\), and Singapore \(Singapore\).. To use VPCs of the preceding types, [submit a ticket](https://page.aliyun.com/form/act608662110/index.htm?spm=5176.11182174.0.0.5a1c4882UFiAde).

## Prerequisites

To deploy cloud resources in a VPC, you must have network subnetting prepared first. For more information, see [Plan and design a VPC](/intl.en-US/Quick Start/Plan and design a VPC.md).

## Step 1: Create a VPC and VSwitch

A VPC is a private network deployed in the cloud. You have full control over your VPC. For example, you can specify CIDR blocks, and configure route tables and gateways for your VPC.

To create a VPC and VSwitch, perform the following steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).

2.  In the top menu bar, select the region where you want to deploy the VPC.

    The VPC and the cloud resources that you want to deploy must be in the same region. In this topic, **China \(Hohhot\)** is selected.

    **Note:** The following regions support IPv6 gateways: China \(Hangzhou\), China \(Shanghai\), China \(Shenzhen\), China \(Beijing\), China \(Hohhot\), China \(Chengdu\), China \(Hong Kong\), and Singapore \(Singapore\)..

3.  On the VPCs page, click **Create VPC**.

4.  In the Create VPC dialog box, set the following parameters and click **OK**.

    **Note:** Allocate is selected in the IPv6 CIDR Block section in this example. After you create the VPC, the system automatically assigns an IPv6 CIDR block whose mask length is /56 to the VPC and creates an IPv6 gateway free of charge. You can use the IPv6 gateway to control IPv6 traffic.

    |Parameter|Description|
    |:--------|:----------|
    |**VPC**|
    |**Region**|Displays the region where you want to deploy the VPC.|
    |**Name**|Enter a name for the VPC that you want to create. The name must be 2 to 128 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
    |**IPv4 CIDR Block**|Enter an IPv4 CIDR block for the VPC. We recommend that you enter 192.168.0.0/16, 172.16.0.0/12, 10.0.0.0/8, or a subset of these CIDR blocks as the primary IPv4 CIDR block of the VPC. The subnet mask must be 8 to 24 bits in length. 192.168.0.0/24 is used in this example. To use a public CIDR block as the primary CIDR block of the VPC,[submit a ticket](https://workorder-intl.console.aliyun.com/console.htm#/ticket/add?productId=1218).

**Note:** After you create a VPC, you cannot change its primary IPv4 CIDR block. However, you can add a secondary IPv4 CIDR block to the VPC. For more information, see [Add a secondary IPv4 CIDR block](/intl.en-US/VPCs and vSwitchs/Work with VPCs.md). |
    |**IPv6 CIDR Block**|Specify whether to assign an IPv6 CIDR block to the VPC. By default, no IPv6 CIDR block is allocated. If you set this parameter to Assign, the system automatically creates a free IPv6 gateway for this VPC, and assigns an IPv6 CIDR block with the subnet mask /56, such as 2xx1:db8::/56. By default, IPv6 addresses can be used to communicate within only private networks. If you want to allow an instance assigned with an IPv6 address to access the Internet or be accessed by IPv6 clients over the Internet, you must purchase an Internet bandwidth plan for the IPv6 address. For more information, see [Enable Internet connectivity for an IPv6 address](/intl.en-US/User Guide/Manage IPv6 Internet bandwidth/Enable Internet connectivity for an IPv6 address.md).

**Note:**

    -   The following regions support IPv6 CIDR blocks: China \(Hangzhou\), China \(Shanghai\), China \(Shenzhen\), China \(Beijing\), China \(Hohhot\), China \(Chengdu\), China \(Hong Kong\), and Singapore \(Singapore\)..
    -   After you create a VPC, you cannot change its IPv6 CIDR block. |
    |**Description**|Enter a description for the VPC. The description must be 2 to 256 characters in length and cannot start with `http://` or `https://`. |
    |**Resource Group**|Select the resource set to which the VPC belongs.|
    |**vSwitch**|
    |**Name**|Enter a name for the vSwitch. The name must be 2 to 128 characters in length, and can contain digits, underscores \(\_\), and hyphens \(-\). It must start with a letter. |
    |**Zone**|Select a zone for the vSwitch. In the same VPC, vSwitches in different zones can communicate with each other.|
    |**Zone Resource**|Displays the cloud resources that can be created in the specified zone. The supported cloud resources vary based on the zone and the time when you create cloud resources. The instances provided in this topic are for reference only. The actual instances on the buy page shall prevail. Only ECS, ApsaraDB RDS, and SLB instances can be queried on the buy page. |
    |**IPv4 CIDR Block**|Specify an IPv4 CIDR block for the vSwitch. When you specify an IPv4 CIDR block for the vSwitch, take note of the following limits:

    -   The CIDR block of a vSwitch must be a subset of the CIDR block of the VPC to which the vSwitch belongs.

For example, if the CIDR block of a VPC is 192.168.0.0/16, the CIDR block of a vSwitch in the VPC must be a subset of 192.168.0.0/16. In this example, the CIDR block of the vSwitch can range from 192.168.0.0/17 to 192.168.0.0/29.

    -   The first IP address and last three IP addresses of a vSwitch CIDR block are reserved.

For example, if a vSwitch CIDR block is 192.168.1.0/24, the IP addresses 192.168.1.0, 192.168.1.253, 192.168.1.254, and 192.168.1.255 are reserved.

    -   If the vSwitch is required to communicate with vSwitches in other VPCs or with data centers, make sure that the CIDR block of the vSwitch does not overlap with the destination CIDR blocks.
**Note:** After you create a vSwitch, you cannot modify its CIDR block. |
    |**Number of Available Private IPs**|Displays the number of available IP addresses.|
    |**IPv6 CIDR Block**|Specify an IPv6 CIDR block for the vSwitch. By default, the subnet mask for the IPv6 CIDR block of a vSwitch is /64. You can enter a number from 0 to 255 to define the last 8 bits of the IPv6 CIDR block.

For example, if the IPv6 CIDR block of the VPC is 2xx8:4004:c0:b900::/56, you can specify 255 to define the last 8 bits of the IPv6 CIDR block. In this case, the IPv6 CIDR block of the vSwitch is 2xx8:4004:c0:b9ff::/64. ff is the hexadecimal value of 255. |
    |**Description**|Enter a description for the vSwitch. The description must be 2 to 256 characters in length and cannot start with `http://` or `https://`. |


## Step 2: Create and configure an ECS instance

After you create an IPv6 VPC and VSwitch, you must create an ECS instance and assign an IPv6 address to the ECS instance. Then, you must assign the specified IPv6 address to the network interface controller \(NIC\) of the ECS instance.

To create and configure the ECS instance, perform the following steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).

2.  In the left-side navigation pane, click **VSwitches**.

3.  On the top of the page, select the region where you want to create the VSwitch. **China \(Hohhot\)** is selected in this example.

4.  On the VSwitches page, find the VSwitch and choose **Create** \> **ECS Instance** in the **Actions** column.

5.  On the Custom Launch page, configure the ECS instance.

    The ECS instance is configured as shown in the following description:

    -   To log on to the ECS instance, you must configure the elastic network interface \(ENI\) of the ECS instance. Select **Assign Public IP Address** and set the bandwidth to 1 Mbit/s. You can use an elastic IP address \(EIP\) instead of a public IP address.
    -   Select **Assign IPv6 Address Free of Charge**.
    For more information about other parameters, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).

6.  Return to the Instances page, and click the instance ID to view the assigned IPv6 address.

7.  Configure a static IPv6 address.


## Step 3: Purchase an IPv6 Internet bandwidth plan

By default, IPv6 addresses can be used for communication only over private networks. If you want to use the IPv6 address to access the Internet or to be accessed by IPv6 clients over the Internet, you must purchase an Internet bandwidth plan for the IPv6 address.

To purchase an IPv6 Internet bandwidth plan, perform the following steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).

2.  In the left-side navigation pane, click **IPv6 Gateway**.

3.  In the top navigation bar, select the region of the IPv6 gateway. In this example, **China \(Hohhot\)** is selected.

4.  On the IPv6 Gateway page, find the IPv6 gateway and click **Manage** in the **Actions** column.

5.  In the left-side navigation pane, click **IPv6 Internet Bandwidth**.

6.  On the IPv6 Internet Bandwidth page, find the IPv6 address and click **Enable IPv6 Internet Bandwidth** in the **Actions** column.

    ![Purchase an Internet bandwidth plan](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8310509951/p33776.png)

7.  Specify the billing method and maximum bandwidth, click **Buy Now**, and then complete the payment.


## Step 4: Configure the security group rules

IPv4 addresses cannot communicate with IPv6 addresses. If the current security group rules cannot meet the requirements of your IPv6 workloads, you can configure IPv6 security group rules for the ECS instance.

For more information, see [Add security group rules](/intl.en-US/Security/Security groups/Add security group rules.md).

## Step 5: Test the connectivity

Log on to the ECS instance and ping an IPv6 service to test whether the communication is working as expected.

![Test the connectivity](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2310509951/p54447.png)

