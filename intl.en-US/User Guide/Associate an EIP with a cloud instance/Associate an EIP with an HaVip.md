# Associate an EIP with an HaVip {#task_593058 .task}

This topic describes how to associate an Elastic IP Address \(EIP\) with a High-Availability Virtual IP Address \(HaVip\). After you associate an EIP with an HaVip, the HaVip can access the Internet.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**|Select **HaVip Address** The HaVip to be associated with the EIP must meet the following requirements:

    -   The HaVip and the EIP must belong to the same region.
    -   The HaVip must be in the Available or Allocated state.
    -   An HaVip can be associated with only one EIP.
 |
    |**HaVip Address**|Select the HaVip address to be associated with the EIP.|


