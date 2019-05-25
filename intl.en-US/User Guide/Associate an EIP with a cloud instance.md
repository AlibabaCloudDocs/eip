# Associate an EIP with a cloud instance {#task_bh5_dll_vdb .task}

You can associate an Elastic IP Address \(EIP\) with an ECS instance, an Elastic Network Interface \(ENI\), a Server Load Balancer \(SLB\) instance or a NAT Gateway to enable Internet communication.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  Select the target region and find the target EIP.
4.  Click **Bind** in the **Actions** column of the target EIP. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12805/155874855235585_en-US.png)

5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**| Select the type of the instance to be associated with the EIP.

     -   **ECS Instance**: After you associate an EIP with an ECS instance, the ECS instance can access the Internet through the EIP.

The ECS instance must meet the following requirements:

        -   The network type of the ECS instance must be VPC.
        -   The ECS instance and the EIP must belong to the same region.
        -   The ECS instance must be in the running or stopped state.
        -   The ECS instance cannot have a public IP address or be associated with any EIP.
        -   One ECS instance can be associated with only one EIP.
    -   **NAT Gateway Instance**: After you associate an EIP with a NAT Gateway, you can use the EIP to configure DNAT and SNAT entries.

The NAT Gateway must meet the following requirements:

        -   The NAT Gateway and the EIP must belong to the same region.
        -   Up to 10 EIPs can be associated with a NAT Gateway.
    -   **SLB Instance**: After you associate an EIP with an SLB instance, the SLB instance can forward requests from the Internet.

The SLB instance must meet the following requirements:

        -   The network type of the SLB instance must be VPC.
        -   The SLB instance and the EIP must belong to the same region.
        -   Each SLB instance can be associated with only one EIP at a time.
    -   **Secondary ENI**: After you associate an EIP with an ENI, the ECS instance attached to the ENI can access the Internet or provide external services by using the EIP.

For more information, see [Associate an EIP with an ENI](reseller.en-US//Associate an EIP with an ENI.md#).

 |
    |**NAT Gateway Instance/ECS Instance/SLB Instance**|Select the instance to be associated with the EIP.|


