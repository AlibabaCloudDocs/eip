# Associate an EIP with an SLB instance

This topic describes how to associate an elastic IP address \(EIP\) with a Server Load Balancer \(SLB\) instance. After you associate an EIP with an SLB instance, the SLB instance can distribute requests from the Internet.

A SLB instance is created. For more information, see [Create an SLB instance](/intl.en-US/Quick Start (New Console)/Create an SLB instance.md).

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where your EIP is created.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters, and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **SLB Instance**.|
    |**Select an instance to bind**|Select the SLB instance to be associated with the EIP.When you select an SLB instance, make sure that the following requirements are met:

    -   The SLB instance must be deployed in a Virtual Private Cloud \(VPC\) network.
    -   The SLB instance and the EIP must be deployed in the same region.
    -   Each SLB instance can be associated with only one EIP. |


**Related topics**  


[AssociateEipAddress](/intl.en-US/API reference/EIP/AssociateEipAddress.md)

