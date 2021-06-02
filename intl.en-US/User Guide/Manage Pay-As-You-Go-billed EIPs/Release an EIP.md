# Release an EIP

This topic describes how to release an elastic IP address \(EIP\) that you no longer need. After you release an EIP, you are no longer charged for the EIP.

Take note of the following limits before you release an EIP:

-   You can release only pay-as-you-go EIPs. You cannot release subscription EIPs.
-   You cannot release EIPs that are locked due to security issues.

After you release an EIP, you are no longer charged for the EIP. However, you may still receive bills.

-   Bills for pay-by-data-transfer EIPs are generated on an hourly basis. The bill for data transfer within the current hour is generated the next hour.

    For example, if you release an EIP at 10:30, you will receive a bill at 11:00. The bill contains fees that are charged from 10:00 to 11:00.

-   Bills for pay-by-bandwidth EIPs are generated on a daily basis. Bills are generated at 00:00 every day and contain fees that are charged during the last day.

    For example, if you release an EIP on January 1, 2019, you will receive a bill at 00:00 \(UTC+8\), January 2, 2019. The bill contains fees that are charged during January 1, 2019.


## Prerequisites

Before you release an EIP, make sure that the following requirements are met:

-   The EIP is not associated with an EIP bandwidth plan. For more information, see [Disassociate an EIP from an EIP bandwidth plan](/intl.en-US/User Guide/Manage Pay-As-You-Go-billed EIPs/Disassociate an EIP from an EIP bandwidth plan.md).
-   The EIP is not associated with a cloud resource. For more information, see [Disassociate an EIP from a cloud resource](/intl.en-US/User Guide/Disassociate an EIP from a cloud resource.md).

## Release an EIP

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage and choose **![More](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1576420061/p140904.png)** \> **Release** in the **Actions** column.

4.  In the **Release Elastic IP** dialog box, click **OK**.

    If you release a continuous EIP, all continuous EIPs in the continuous EIP group are released. Select **I have read and understood the preceding information, and want to release the continuous EIP group and all EIPs in it** and click **OK**.


## Enable deletion protection

You can enable deletion protection to prevent EIPs from being released due to human errors.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  Use one of the following methods to enable deletion protection:

    After you enable deletion protection for an EIP, you cannot release the EIP.

    -   Method 1
        1.  On the **Elastic IP Addresses** page, find the EIP that you want to manage and click its ID.
        2.  On the Instance Information tab, click **Enable Deletion Protection**.
    -   Method 2

        On the **Elastic IP Addresses** page, select one or more EIPs and choose **More** \> **Enable Deletion Protection**.


## Disable deletion protection

If the EIP that you want to release has deletion protection enabled, you must disable deletion protection before you can release the EIP.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  Use one of the following methods to disable deletion protection:

    -   Method 1
        1.  On the **Elastic IP Addresses** page, find the EIP that you want to manage and click its ID.
        2.  On the Instance Information tab, click **Disable Deletion Protection**.
    -   Method 2

        On the **Elastic IP Addresses** page, find the EIP that you want to manage, move the pointer over ![Deletion protection](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0881349161/p208122.png), and then click **Disable Deletion Protection** in the tooltip that appears.

    -   Method 3

        On the **Elastic IP Addresses** page, select one or more EIPs and choose **More** \> **Disable Deletion Protection**.


**Related topics**  


[ReleaseEipAddress](/intl.en-US/API reference/EIP/ReleaseEipAddress.md)

[ReleaseEipSegmentAddress](/intl.en-US/API reference/EIP/ReleaseEipSegmentAddress.md)

