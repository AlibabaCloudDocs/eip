# Associate multiple EIPs with a secondary ENI in NAT mode

This topic describes how to associate multiple elastic IP addresses \(EIPs\) with a secondary Elastic Network Interface \(ENI\) in NAT mode to make full use of Elastic Compute Services \(ECS\) instances.

ECS instances can communicate with the Internet only after they are associated with static public IP addresses or EIPs. Each ECS instance can be associated with only one static public IP address or EIP.

## Scenario

This topic takes the following scenario as an example. A company creates an ECS instance on Alibaba Cloud and associates the ECS instance with an EIP. To meet business requirements, the company needs to associate the ECS instance with three EIPs to make full use of the ECS instance.

If you want to associate multiple EIPs with an ECS instance in NAT mode, you must assign the same number of secondary private IP addresses to the secondary ENI of the ECS instance. Then, map the EIPs to the secondary private IP addresses, respectively. This way, you can make full use of the ECS instance.

![Scenario](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5059039951/p146503.png)

## Prerequisites

-   An ECS instance is created. For more information, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).
-   A secondary ENI is created and meets the following requirements:

    -   The secondary ENI and the ECS instance to be associated with the secondary ENI are deployed in the same Virtual Private Cloud \(VPC\) network.
    -   The VSwitch of the secondary ENI and the VSwitch of the ECS instance to be associated with the secondary ENI are deployed in the same region.
    For more information, see [t9734.md\#](/intl.en-US/Network/Elastic Network Interfaces/Create an ENI.md).

-   Three EIPs are created in the same region as the ENI. For more information, see [Apply for new EIPs](/intl.en-US/User Guide/Create an EIP/Apply for new EIPs.md).

## Procedure

![Procedure](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5059039951/p144059.png)

## Step 1: Assign multiple secondary private IP addresses

You can assign multiple secondary private IP addresses to each secondary ENI. This helps make full use of the ECS instance and mask the failure of the ECS instance by rapidly remapping the EIP.

Take the following steps to assign multiple secondary private IP addresses to a secondary ENI.

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).

2.  In the left-side navigation pane, choose **Network & Security** \> **ENIs**.

3.  In the upper-left corner, select the region where the secondary ENI is deployed.

4.  On the **Network Interfaces** page, find the target ENI, and click **Manage Secondary Private IP Address** in the **Actions** column.

5.  In the **Manage Secondary Private IP Address** dialog box, click **Assign New IP** one or more times. Then, one or more secondary private IP addresses are automatically assigned to the secondary ENI.

    Click **Assign New IP** two times in this example. Then, two secondary private IP addresses are automatically assigned to the secondary ENI.

    **Note:** You can manually enter a secondary private IP address. The private IP addresses must be within the range of **IPv4 private CIDR blocks**. If you do not manually enter a secondary private IP address, the system assigns an idle IP address from the **IPv4 private CIDR blocks**.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6059039951/p47047.png)

6.  Click **OK**.

7.  On the **Network Interfaces** page, find the target secondary ENI, and click **Manage Secondary Private IP Address** in the **Actions** column to view the assigned secondary private IP addresses.

    ![View the assigned secondary private IP addresses](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6059039951/p143959.png)


## Step 2: Map EIPs to the secondary private IP addresses

Take the following steps to map an EIP to a secondary private IP address of the secondary ENI.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the target EIP and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    -   **Instance Type**: Select **Secondary ENI**.
    -   **Mode**: Select **NAT Mode**.

        In NAT mode:

        -   The number of EIPs that can be associated with a secondary ENI depends on the number of private IP addresses assigned to this secondary ENI.
        -   The secondary private addresses and public IP addresses of the secondary ENI are available at the same time.
        -   In the operating system of the ECS instance, the EIP is not displayed. You must call the DescribeInstances operation to display the EIP that is associated with the ECS instance. For more information, see [DescribeEipAddresses](/intl.en-US/API reference/EIP/DescribeEipAddresses.md).
        -   EIPs do not support NAT application layer gateway \(ALG\), protocols such as H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), Real Time Streaming Protocol \(RTSP\), and Trivial File Transfer Protocol \(TFTP\).
    -   **Secondary ENI**: Select the target secondary private IP address that you want to map to the EIP. You can also map the EIP to the primary private IP address of the secondary ENI.

        In this example, the primary private IP address of the secondary ENI is selected.

5.  Repeat the preceding steps to map the remaining EIPs to the secondary private IP addresses of the secondary ENI. Make sure that each EIP is mapped to a separate secondary private IP address.


## Step 3: Associate the secondary ENI with an ECS instance

Take the following steps to associate the secondary ENI with an ECS instance

1.  Log on to the [ECS console](https://ecs.console.aliyun.com/#/home).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

3.  In the top navigation bar, select the region where the target ECS instance is deployed.

4.  On the **Instances** page, find the target ECS instance, and choose **More** \> **Network and Security Group** \> **Bind Secondary ENI** in the **Actions** column.

5.  In the **Bind Secondary ENI** dialog box, select the secondary ENI to be associated and click **OK**.


## Step 4: Configure the secondary private IP addresses

After you associate the secondary ENI with the ECS instance, you must configure the secondary private IP addresses for the ECS instance.

An ECS instance that runs CentOS 7 is used in the following example to describe how to configure the secondary private IP addresses for the ECS instance. For more information about how to configure ECS instances that run other operating systems, see [Configure secondary private IP addresses in a Windows instance](/intl.en-US/Network/Elastic Network Interfaces/Assign secondary private IP addresses.md) and [Configure secondary private IP addresses in a Linux instance](/intl.en-US/Network/Elastic Network Interfaces/Assign secondary private IP addresses.md).

1.  Log on to the ECS instance.

2.  Run the following command to query the MAC address of the secondary ENI:

    `ip address`

    ![Query the MAC address](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6059039951/p144007.png)

3.  Configure the secondary private IP addresses for the secondary ENI.

    1.  Run the following command to open the configuration file of the secondary ENI:

        `vi /etc/sysconfig/network-scripts/ifcfg-eth1`

    2.  Run the following command to enter the Edit mode:

        `i`

    3.  Run the following command to copy configurations to the configuration file of the secondary ENI:

        ```
        DEVICE=eth1  # This indicates the newly configured ENI.
        BOOTPROTO=no
        ONBOOT=yes
        TYPE=Ethernet
        USERCTL=yes
        PEERDNS=no
        IPV6INIT=no
        PERSISTENT_DHCLIENT=yes
        HWADDR=00:16:**:**:cc:8d  # Configure the MAC address of the secondary ENI.
        IPADDR0=172.xx.xx.163     # Configure the primary private IP address of the secondary ENI.
        IPADDR1=172.xx.xx.164     # Configure the secondary private IP address 1 of the secondary ENI.
        IPADDR2=172.xx.xx.165     # Configure the secondary private IP address 2 of the secondary ENI.
        DEFROUTE=no  # This indicates that the ENI is not the default route. To avoid changing the active default route of the ECS instance while bring up the secondary ENI of the ECS instance, do not specify the eth1 as the default route.
        ```

4.  Run the following command to restart the network connection service:

    `service network restart`


After you configure the secondary private IP addresses, you can run the ip address command to view the configured secondary private IP addresses.

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6059039951/p47722.png)

## Step 5: Test the network connectivity

An ECS instance that runs Linux is used in the following example to describe how to test the network connectivity.

1.  Log on to the ECS instance.

2.  Run the following command to configure a static route in which the source IP address is set to one of the secondary private IP addresses:

    `ip route add <destination network>/<prefix length of the subnet> via <NAT gateway of the secondary private IP addresses> src <secondary private IP address>`

3.  Run the following command to verify the connectivity between the secondary private IP addresses and the destination network:

    `ping <destination network> -I <secondary private IP addresses>`

    The test result shows that packets sent from the secondary private IP addresses can reach the destination network. This means that the association between the secondary private IP addresses and EIP takes effect.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6059039951/p49832.png)


