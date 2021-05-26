---
keyword: [classic network, public IP addresses, convert public IP addresses, network migration, EIP]
---

# Convert the static public IP address of an ECS instance in a classic network to an EIP

When you manually release an ECS instance, you can convert the static public IP address of the Elastic Compute Service \(ECS\) instance to an elastic IP address \(EIP\). You can associate an EIP with an ECS instance that is deployed in a virtual private cloud \(VPC\). EIPs provide the following features to meet your business requirements in different scenarios: EIPs allow you to migrate resources between different networks. You can associate EIPs with resources at any time and modify the bandwidth limits of EIPs on demand. You can convert the static public IP address of an ECS instance that is deployed in a classic network to an EIP only when you manually release the ECS instance.

Before you convert the static public IP address of an ECS instance that is deployed in a classic network to an EIP, make sure that the following requirements are met:

-   The ECS instance is assigned a static public IP address.
-   The ECS instance is not deployed in Hangzhou Zone C.
-   If the ECS instance is billed on a pay-as-you-go basis, it is in the **Stopped** state and your account does not have overdue payments.
-   If the ECS instance is billed on a subscription basis, it is in the **Expired** or **Expired and Being Recycled** state.
-   If the instance is a subscription instance, the instance uses **Pay-By-Traffic** billing method for Internet usage. You can change the billing method for Internet usage from **Pay-By-Bandwidth** to Pay-By-Traffic by upgrading or downgrading instance configurations. For more information, see [Overview of instance upgrade and downgrade](/intl.en-US/Instance/Change configurations/Overview of instance upgrade and downgrade.md).
-   If you have performed an operation to modify the specification of the ECS instance, make sure that the modification takes effect before you convert the static public IP address.
-   Snapshots are created for the ECS instance to avoid data loss caused by human errors. For more information, see [Create a snapshot](/intl.en-US/Snapshots/Use snapshots/Create a normal snapshot.md).

After the static public IP address is converted to an EIP:

-   The EIP is billed on a pay-by-data-transfer basis.
-   The bandwidth limit of the EIP that is used for communication over the Internet is the same as the bandwidth limit of the ECS instance. You can modify the bandwidth limit of the EIP in the VPC console based on your business requirements. However, if the bandwidth limit of the ECS instance is 0 Mbit/s, the bandwidth limit of the EIP is 1 Mbit/s.
-   You cannot associate the EIP with an ECS instance that is deployed in a classic network.
-   Compared to ECS instances in a VPC, ECS instances in a classic network are attached with public network interface controllers \(NICs\). After the static public IP address is converted to an EIP, the public NIC is removed from the ECS instance and the MAC address of the NIC is not preserved.

1.  Log on to the [ECS console](https://ecs.console.aliyun.com).

2.  In the left-side navigation pane, choose **Instances & Images** \> **Instances**.

3.  In the top navigation bar, select a region.

4.  Find the ECS instance that you want to manage and release the ECS instance by performing the following operations:

    -   To release a subscription ECS instance, click **Release** in the **Actions** column.
    -   To release a pay-as-you-go ECS instance, choose **More** \> **Instance Status** \> **Release** in the **Actions** column.
5.  Select **Release Now**, select **Convert the public IP address of the ECS instance in a classic network to an EIP address. \(The EIP addresses that are not bound to ECS instances will be billed.\)**, and then click **Next**.

    ![Convert the public IP address of the ECS instance in a classic network to an EIP address. (The EIP addresses that are not bound to ECS instances will be billed.)](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6257298951/p51065.png)

6.  Click **OK**.


After the static public IP address of an ECS instance in a classic network is converted to an EIP, the ECS instance is released. You can view the EIP in the VPC console.

![View the EIP](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6257298951/p51066.png)

Then, you can associate the EIP with the ECS instance again or with another ECS instance. For more information, see [Associate an EIP with an ECS instance](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Associate an EIP with an ECS instance.md).

