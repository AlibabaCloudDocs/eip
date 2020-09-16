# Switch the billing method of an EIP to pay-by-bandwidth

This topic describes how to switch the billing method of an elastic IP address \(EIP\) from pay-by-data-transfer to pay-by-bandwidth.

Note the following rules before you switch the billing method:

-   The new billing method takes effect at 00:00 the next day.
-   Before the new billing method takes effect, you cannot modify the maximum bandwidth of the EIP.

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where your EIP is created.

3.  On the Elastic IP Addresses page, find the EIP that you want to manage, and click **![More](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1382169951/p143776.png)** \> **Modify Configuration** in the **Actions** column.

4.  In the Configuration Upgrade section, set the following parameters, and click **Activate**.

    |Parameter|Description|
    |---------|-----------|
    |**Network Type**|The network type of the EIP.|
    |**Max Bandwidth**|The maximum bandwidth of the EIP. You can increase or decrease the maximum bandwidth. |
    |**Network Traffic**|Select **By bandwidth**. The EIP is billed based on the maximum bandwidth that you have set on that day, not the actual data usage. |
    |**Billing Cycle**|The billing cycle of the EIP.|


