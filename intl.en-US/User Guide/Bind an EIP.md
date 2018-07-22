# Bind an EIP {#task_bh5_dll_vdb .task}

You can bind an Elastic IP Address \(EIP\) to an ECS instance, SLB instance or a NAT Gateway to enable Internet communication.

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com). 
2.  In the left-side navigation pane, click **Elastic IP Addresses**. 
3.  Select the region of the EIP and find the target EIP. 
4.  Click **Bind** in the **Actions** column of the target EIP. 
5.  On the Bind Elastic IP Address page, complete the following configurations, and then click **OK**. 

    |Configuration|Description|
    |:------------|:----------|
    |**Instance Type**| Select the type of instance to bind:

     -   **ECS Instance**: After binding an EIP, the ECS instance can communicate with the Internet.

The ECS instance must meet the following requirements:

        -   The network type of the ECS instance must be VPC.
        -   The ECS instance and the EIP must be in the same region.
        -   The ECS instance must be in the running or stopped status.
        -   The ECS instance does not have a public IP, nor is it bound to any EIP.
        -   One ECS instance can only be bound to one EIP.
    -   **NAT Gateway**: After binding an EIP, you can use the EIP to configure DNAT and SNAT entries.

The NAT Gateway must meet the following requirements:

        -   No bandwidth package was purchased before January 26, 2018 under the account that the NAT Gateway belongs to.
        -   The NAT Gateway and the EIP must be in the same region.
        -   Up to 10 EIPs can be bound to a NAT Gateway.
    -   **SLB Instance**: After an EIP is bound to an SLB instance, the SLB instance can forward requests from the Internet.

The SLB instance must meet the following requirements:

        -   The network type of the SLB instance must be VPC.
        -   The SLB instance and the EIP must be in the same region.
        -   Each SLB instance can have only one EIP bound to it at a time.
 |
    |**Instance**|Select the instance to bind.|


