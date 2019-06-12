# Add an EIP to a shared-bandwidth Global Acceleration instance {#task_593342 .task}

This topic describes how to add an Elastic IP Address \(EIP\) to a shared-bandwidth Global Acceleration instance. After you create a shared-bandwidth Global Acceleration instance, you can add all EIPs in the same region to the shared-bandwidth Global Acceleration instance. In this way, the EIPs can obtain the feature of Internet access acceleration and share the bandwidth of the Global Acceleration instance to save the Internet cost.

The EIP to be added to a shared-bandwidth Global Acceleration instance must meet the following requirements:

-   The EIP must adopt the Pay-As-You-Go billing method.
-   The EIP and the shared-bandwidth Global Acceleration instance must belong to the same region.
-   Up to 200 EIPs can be added to a shared-bandwidth Global Acceleration instance. If you need to add more EIPs, open a ticket.
-   A shared-bandwidth Global Acceleration instance is created. For more information, see [Create a shared-bandwidth Global Acceleration instance](../../../../reseller.en-US/Quick Start/Configure a shared-bandwidth Global Acceleration instance.md#section_scl_pxw_5db).

Shared-bandwidth global acceleration instances are billed by using the bandwidth-based Subscription method. For more information, see [Billing instructions](../../../../reseller.en-US/Pricing/Billing instructions.md#).

After an EIP is added to a shared-bandwidth Global Acceleration instance,

-   The original peak bandwidth of the EIP becomes invalid and all added EIPs share the bandwidth of the Global Acceleration instance.
-   The original billing method of the EIP becomes invalid. The EIP becomes a pure public IP address and no additional traffic or bandwidth fee is charged.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP, and choose **More** \> **Add to Global Acceleration** in the **Actions** column.
5.  In the displayed dialog box, select the target shared-bandwidth Global Acceleration instance, and then click **OK**.

