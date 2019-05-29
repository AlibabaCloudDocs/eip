# Associate an EIP with a cloud instance {#task_bh5_dll_vdb .task}

You can associate an Elastic IP Address \(EIP\) with an ECS instance, an Elastic Network Interface \(ENI\), a Server Load Balancer \(SLB\) instance or a NAT Gateway to enable Internet communication.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  On the Elastic IP Addresses page, select the region of the target EIP.
4.  Find the target EIP, and click **Bind** in the **Actions** column. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12805/155909964535585_en-US.png)

5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**| Select the type of the cloud instance to be associated with the EIP:

     -   **NAT Gateway Instance**: After you associate an EIP with a NAT Gateway, you can use the EIP to configure DNAT and SNAT entries.

The NAT Gateway must meet the following requirements:

        -   The NAT Gateway and the EIP must belong to the same region.
        -   Up to 10 EIPs can be associated with a NAT Gateway.
    -   **ECS Instance**: After you associate an EIP with an ECS instance, the ECS instance can access the Internet through the EIP.

The ECS instance must meet the following requirements:

        -   The network type of the ECS instance must be VPC.
        -   The ECS instance and the EIP must belong to the same region.
        -   The ECS instance must be in the Running or Stopped state.
        -   The ECS instance cannot have a public IP address or be associated with any EIP.
        -   One ECS instance can be associated with only one EIP.
    -   **HaVip Address**: After you associate an EIP with a High-Availability Virtual IP Address \(HaVip\), the HaVip can access the Internet.

The HaVip must meet the following requirements:

        -   The HaVip and the EIP must belong to the same region.
        -   The HaVip must be in the Available or Allocated state.
        -   An HaVip can be associated with only one EIP.
    -   **SLB Instance**: After you associate an EIP with a Server Load Balancer \(SLB\) instance, the SLB instance can forward requests from the Internet.

The SLB instance must meet the following requirements:

        -   The network type of the SLB instance must be VPC.
        -   The SLB instance and the EIP must belong to the same region.
        -   Each SLB instance can be associated with only one EIP at a time.
    -   **Secondary ENI**: After you associate an EIP with an ENI, the ECS instance attached to the ENI can access the Internet or provide external services by using the EIP.

The secondary ENI must meet the following requirements:

        -   The network type of the secondary ENI must be VPC.
        -   The secondary ENI and the EIP must belong to the same region.
        -   You can associate an EIP with an ENI in three modes: NAT mode, cut-through mode, and multi-EIP to ENI mode.
            -   In the NAT mode, the number of EIPs with which a secondary ENI can be associated depends on the number of private IP addresses of the secondary ENI.
            -   In the cut-through mode, a secondary ENI can only be associated with one EIP.
            -   In the multi-EIP to ENI mode, a secondary ENI can be associated with 10 EIPs. If you need to associate more EIPs, you can open a ticket to increase the quota.
 |
    |**NAT Gateway Instance/ECS Instance/HaVip Address/SLB Instance/Secondary ENI**|Select the instance to be associated with the EIP.|


