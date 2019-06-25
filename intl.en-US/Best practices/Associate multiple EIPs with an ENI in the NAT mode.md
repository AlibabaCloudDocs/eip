# Associate multiple EIPs with an ENI in the NAT mode {#concept_269613 .concept}

This topic describes how to associate multiple Elastic IP Addresses \(EIPs\) with a secondary Elastic Network Interface \(ENI\) in the NAT mode. By associating multiple EIPs with a secondary ENI, you can improve the availability of the associated ECS instance.

## Prerequisites {#section_c2k_9h5_mbp .section}

If you want to associate multiple EIPs with a secondary ENI in the NAT mode, the following requirements must be met:

-   You have obtained the permission to associate multiple EIPs with a secondary ENI in the NAT mode by opening a ticket.
-   An ECS instance is created. For more information, see [Create an instance by using the wizard](../../reseller.en-US/Instances/Create an instance/Create an instance by using the wizard.md#).
-   A secondary ENI is created. For more information, see [Create an ENI](../../reseller.en-US/Network/Elastic Network Interfaces/Create an ENI.md#).

## Limit {#section_n30_2j0_2cd .section}

Currently, multiple EIPs associated with one secondary ENI in the NAT mode are supported only in the China \(Beijing\), China \(Zhangjiakou\), Singapore, Germany \(Frankfurt\), and India \(Mumbai\) regions.

## Step 1 Assign multiple secondary private IP addresses to the ENI {#section_nbm_39r_jyz .section}

To assign multiple secondary private IP addresses to the ENI, follow these steps:

1.  Log on to the [ECS console](https://partners-intl.aliyun.com/login-required#/ecs).
2.  In the left-side navigation pane, choose **Network & Security** \> **ENI**.
3.  On the Network Interfaces page, select the region of the target ENI.
4.  Find the target ENI and click **Manage Secondary Private IP Address** in the **Actions** column.
5.  On the Manage Secondary Private IP Address page, click **Assign New IP** multiple times to assign multiple secondary private IP addresses to the ENI.

    **Note:** You can manually enter private IP addresses, which must fall into the **IPv4 Private CIDR**. If you do not enter any IP addresses, the system will automatically assign IP addresses from the **IPv4 Private CIDR**.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/83258/156142478447047_en-US.png)

6.  Click **Modify**.

## Step 2 Associate EIPs with the secondary private IP addresses {#section_nom_quj_d1f .section}

To associate EIPs with the secondary private IP addresses of the ENI, follow these steps:

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**.
    -   **Instance Type**: Select **Secondary ENI**.
    -   **Resource Group**: Select the resource group to which the EIP belongs.
    -   **Mode**: Select **NAT Mode**.
    -   **Secondary ENI**: Select the ENI to be associated with the EIP.
6.  Repeat the preceding steps to associate multiple EIPs with the secondary private IP addresses of the secondary ENI.

## Step 3 Associate the ENI with an ECS instance {#section_lgd_nts_85o .section}

After associating EIPs with the secondary private IP addresses of the ENI, you need to associate the ENI with an ECS instance. For more information, see [Attach an ENI to an existing ECS instance](../../reseller.en-US/Network/Elastic Network Interfaces/Attach an ENI.md#section_bwf_mqs_lgb).

## Step 4 Configure secondary private IP addresses {#section_h3w_i8m_svn .section}

After associating the ENI with an ECS instance, you need to configure secondary private IP addresses for the ECS instance. For more information, see [Assign a secondary private IP address to a Windows instance](../../reseller.en-US/Network/Elastic Network Interfaces/Assign a secondary private IP address.md#section_y4b_krk_ggb) and [Assign a secondary private IP address to a Linux instance](../../reseller.en-US/Network/Elastic Network Interfaces/Assign a secondary private IP address.md#section_b2x_hlb_3gb).

**Note:** To configure secondary private IP addresses for an ECS instance, you must first obtain the gateway and subnet mask. For more information, see [Retrieve instance metadata](../../reseller.en-US/Instances/Manage instances/User-defined data and metadata/Retrieve instance metadata.md#).

After configuring secondary private IP addresses, you can run the ip address command to view the configured secondary private IP addresses.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222560/156142478447722_en-US.png)

## Step 5 Test the network connectivity {#section_6l6_t3r_azk .section}

In this example, an ECS instance with the Linux operating system is created and static routing of the eth1 network interface is configured. To test the network connectivity of the ECS instance, follow these steps:

1.  Log on to the ECS instance.
2.  Run the following command to configure static routing for the eth1 network interface: `/sbin/iproute add <destination network>/<the number of network bits> via <gateway of the secondary private IP address> eth1 src <secondary private IP address>`.
3.  Run the following command to check the network connectivity between the secondary private IP address and the destination network: `ping <destination network> -I <secondary private IP address>`.

    If the ping test succeeds, it indicates that the EIPs have been associated with the secondary private IP addresses of the ENI.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/222560/156142478549832_en-US.png)


