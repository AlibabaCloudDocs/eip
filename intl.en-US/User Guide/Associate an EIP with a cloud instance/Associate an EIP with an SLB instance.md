# Associate an EIP with an SLB instance {#task_593067 .task}

This topic describes how to associate an Elastic IP Address \(EIP\) with a Server Load Balancer \(SLB\) instance. After you associate an EIP with an SLB instance, the SLB instance can forward requests from the Internet.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**|Select **SLB Instance**. The SLB instance to be associated with the EIP must meet the following requirements:

    -   The network type of the SLB instance must be VPC.
    -   The SLB instance and the EIP must belong to the same region.
    -   Each SLB instance can be associated with only one EIP at a time.
 |
    |**SLB Instance**|Select the SLB instance to be associated with the EIP.|


