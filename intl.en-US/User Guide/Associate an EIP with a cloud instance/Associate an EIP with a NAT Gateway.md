# Associate an EIP with a NAT Gateway {#task_593039 .task}

This topic describes how to associate an Elastic IP Address \(EIP\) with a NAT Gateway. After you associate an EIP with a NAT Gateway, you can use the EIP to configure DNAT and SNAT entries.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**|Select **NAT Gateway Instance**. The NAT Gateway to be associated with the EIP must meet the following requirements:

    -   The NAT Gateway and the EIP must belong to the same region.
    -   Up to 20 EIPs can be associated with a NAT Gateway. To associate more EIPs, open a ticket.
 |
    |**NAT Gateway Instance**|Select the NAT Gateway to be associated with the EIP.|


