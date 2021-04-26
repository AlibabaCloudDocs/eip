# Release an EIP

This topic describes how to release an elastic IP address \(EIP\) that you no longer need. After you release an EIP, you are no longer charged for it.

Take note of the following limits before you release an EIP:

-   You can only release pay-as-you-go EIPs. You cannot release subscription EIPs.
-   You cannot release EIPs that are locked due to security issues.

After you release an EIP, you are no longer charged for the EIP. However, you may still receive bills.

-   Bills for pay-by-data-transfer EIPs are generated on an hourly basis. The bill for data transfer within the current hour is generated at the next hour.

    For example, if you release an EIP at 10:30, you will receive a bill at 11:00. The bill covers fees that are charged from 10:00 to 11:00.

-   Bills for pay-by-bandwidth EIPs are generated on a daily basis. A bill is generated at 00:00 every day and contains fees that are charged during the last day.

    For example, if you release an EIP on January 1, 2019, you will receive a bill at 00:00, January 2, 2019. The bill covers fees that were charged during January 1, 2019.


## Prerequisites

Before you release an EIP, make sure that the following requirements are met:

-   The EIP is not associated with an EIP bandwidth plan. For more information, see [Disassociate an EIP from an EIP bandwidth plan](/intl.en-US/User Guide/Manage Pay-As-You-Go-billed EIPs/Disassociate an EIP from an EIP bandwidth plan.md).
-   The EIP is not associated with a cloud resource. For more information, see [Disassociate an EIP from a cloud resource](/intl.en-US/User Guide/Disassociate an EIP from a cloud resource.md).

## Release an EIP

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP and choose **![More](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1576420061/p140904.png)** \> **Release** in the **Actions** column.

4.  In the **Release Elastic IP** dialog box, click **OK**.

    If you release an EIP that belongs to a contiguous EIP group, all EIPs in the group are released. Select **I have read and understood the preceding information, and want to release the continuous EIP group and all EIPs in it** and then click **OK**.


## Enable deletion protection

You can enable deletion protection to prevent releasing an EIP by mistake.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  Select one of the following methods to enable deletion protection.

    After you enable deletion protection for an EIP, you cannot release the EIP.

    -   Method 1
        1.  On the **Elastic IP Addresses** page, find the EIP and click its ID.
        2.  On the Instance Information tab, click **Enable Deletion Protection**.
    -   Method 2

        On the **Elastic IP Addresses** page, select one or more EIPs, and choose **More** \> **Enable Deletion Protection**.


## Disable deletion protection

You can disable deletion protection when you want to release an EIP.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  Select one of the following methods to disable deletion protection.

    -   Method 1
        1.  On the **Elastic IP Addresses** page, find the EIP and click its ID.
        2.  On the Instance Information tab, click **Disable Deletion Protection**.
    -   Method 2:

        On the **Elastic IP Addresses** page, find the EIP, move the pointer over ![Deletion protection](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0881349161/p208122.png), and then click **Disable Deletion Protection** in the pop-up box.

    -   Method 3

        On the **Elastic IP Addresses** page, select one or more EIPs, and choose **More** \> **Disable Deletion Protection**.


**Related topics**  


[ReleaseEipAddress](/intl.en-US/API reference/EIP/ReleaseEipAddress.md)

[ReleaseEipSegmentAddress](/intl.en-US/API reference/EIP/ReleaseEipSegmentAddress.md)

