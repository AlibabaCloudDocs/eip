# Manage quotas

You can log on to the Virtual Private Cloud \(VPC\) console to query quota usage of elastic IP addresses \(EIPs\). If the quota of a resource does not meet your business requirements, you can request a quota increase. You can also increase API quotas in the VPC console. This allows you to call more EIP operations within a specific time period.

## Manage quotas

1.  Use one of the following methods to open the **Quota Management** page.

    -   Method 1
        1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com/vpc).
        2.  In the left-side navigation pane, click **Quota Management**.
    -   Method 2
        1.  Log on to the [EIP page](https://vpc.console.aliyun.com/eip).
        2.  At the bottom of the **Elastic IP Addresses** page, choose **Increase EIP Quota** \> **Quantity Quota**.
2.  On the Quota Management page, click the **Elastic IP Address \(EIP\)** tab to view the quota usage of EIPs.

3.  To increase quotas, click **Submit Application** in the **Actions** column.

4.  In the **Apply** dialog box, set the following parameters and submit the application.

    -   **Requested Value**: Enter the requested value.
    -   **Reason**: Enter detailed reasons for the application, including the scenarios and necessity.
    -   **Email**: Enter the email address of the applicant.
5.  Click **OK**.

    The system automatically reviews the application, and determines whether to approve the application. If your application is rejected, its state changes to **Rejected**. If your application is approved, its state changes to **Approved** and new quotas immediately take effect.


## Manage API quotas

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where you want to manage API quotas.

3.  At the bottom of the **Elastic IP Addresses** page, choose **Increase EIP Quota** \> **API Quota**.

4.  On the **API Rate Limits** page, find the name of the API that you want to manage and click **Apply** in the **Actions** column.

5.  In the **Apply for API Rate Limit** dialog box, set the following parameters.

    -   **Applied Quotas**: Enter the requested value. The value indicates the maximum times that you can call the API operation every 60 seconds.
    -   **Reason for Application**: Enter detailed reasons for the application, including the scenarios and necessity.
    -   **Notify Result**:
        -   **Yes**: After your application is processed, you are notified by SMS or email.
        -   **No**: You will not receive a notification.
6.  Click **OK**.

7.  Click **Application Records** in the **Actions** column to view the status of your application.


