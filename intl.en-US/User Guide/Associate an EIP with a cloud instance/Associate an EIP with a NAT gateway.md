# Associate an EIP with a NAT gateway

This topic describes how to associate an elastic IP address \(EIP\) with a NAT gateway. After you associate an EIP with a NAT gateway, you can create DNAT and SNAT entries that use the EIP.

A NAT gateway is created. For more information, see [Create a NAT gateway](/intl.en-US/NAT Gateway Instance/Create a NAT Gateway.md).

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where your EIP is created.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters, and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **NAT Gateway**.|
    |**Select an instance to bind**|Select the NAT gateway to be associated with the EIP.Make sure that the NAT gateway meets the following requirements:

    -   You did not purchase a NAT service plan before January 26, 2018 under the account to which the NAT gateway belongs. If you did, associate the NAT service plan with the NAT gateway.
    -   The NAT gateway and the EIP must be deployed in the same region.
    -   Each NAT gateway can be associated with a maximum of 20 EIPs. If you want to associate more EIPs, submit a ticket to request a quota increase. For more information, see [Quota management](/intl.en-US/User Guide/Quota management.md). |


**Related topics**  


[AssociateEipAddress](/intl.en-US/API reference/EIP/AssociateEipAddress.md)

