# Associate an EIP with a NAT gateway

This topic describes how to associate an elastic IP address \(EIP\) with a NAT gateway. After you associate an EIP with a NAT gateway, you can create DNAT and SNAT entries for the EIP.

A NAT gateway is created. For more information, see [Create NAT gateways](/intl.en-US/User Guide/Create NAT gateways.md)**Create a NAT gateway** in **Quick Start** of the

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **NAT Gateway**.|
    |**Select an instance to bind**|Select the NAT gateway to be associated with the EIP.Make sure that the following requirements are met:

    -   You had not purchased a NAT bandwidth plan before January 26, 2018 with the Alibaba Cloud account to which the NAT gateway belongs. If you did, associate the NAT bandwidth plan with the NAT gateway.
    -   The NAT gateway and EIP must be deployed in the same region.
    -   You can associate a NAT gateway with at most 20 EIPs, among which at most 10 pay-by-data-transfer EIPs can be associated. If you want to associate more EIPs, submit a ticket to request a quota increase. For more information, see [Quota management](/intl.en-US/User Guide/Quota management.md). |


**Related topics**  


[AssociateEipAddress](/intl.en-US/API reference/EIP/AssociateEipAddress.md)

