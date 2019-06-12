# Associate an EIP with an ECS instance {#task_bh5_dll_vdb .task}

This topic describes how to associate an Elastic IP Address \(EIP\) with an ECS instance. After you associate an EIP with an ECS instance, the ECS instance can communicate with the Internet.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Bind** in the **Actions** column.
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**|Select **ECS Instance**. The ECS instance to be associated with the EIP must meet the following requirements:

    -   The network type of the ECS instance must be VPC.
    -   The ECS instance and the EIP must belong to the same region.
    -   The ECS instance must be in the Running or Stopped state.
    -   The ECS instance cannot have a public IP address or be associated with any EIP.
    -   One ECS instance can be associated with only one EIP.
 |
    |**ECS Instance**|Select the ECS instance to be associated with the EIP.|


