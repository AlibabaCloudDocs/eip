# Add EIPs to an Internet Shared Bandwidth instance {#task_bh5_dll_vdb .task}

Internet Shared Bandwidth provides region-level bandwidth sharing. After you purchase an Internet Shared Bandwidth instance, the ECS instances, NAT Gateways, and VPC SLB instances that are associated with the EIPs added to the instance can share the bandwidth.

Make sure the following conditions are met before you add an EIP to an Internet Shared Bandwidth instance:

-   The EIP adopts the Pay-As-You-Go billing method.
-   The EIP and the Internet Shared Bandwidth instance must belong to the same region.
-   Up to 100 EIPs can be added to an Internet Shared Bandwidth instance. If you need to add more EIPs, open a ticket.
-   An Internet Shared Bandwidth instance is created. For more information, see [Create an Internet Shared Bandwidth instance](../../../../reseller.en-US/User Guide/Create an Internet Shared Bandwidth instance.md#).

After you add EIPs to an Internet Shared Bandwidth instance:

-   The ECS instances, SLB instances, and NAT Gateways that are associated with the EIPs share the bandwidth.
-   The peak bandwidth of each added EIP becomes invalid and is replaced by the peak bandwidth of the Internet Shared Bandwidth.
-   The billing method of each added EIP becomes invalid and no additional traffic or bandwidth fee is incurred. Only EIP retention fee is charged on EIPs associated with NAT Gateways or SLB instances, and no additional fee is charged on EIPs associated with ECS instances.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP, and choose **More** \> **Add to Shared Bandwidth Package** in the **Actions** column.
5.  In the displayed dialog box, select the target Internet Shared Bandwidth instance, and click **OK**.

