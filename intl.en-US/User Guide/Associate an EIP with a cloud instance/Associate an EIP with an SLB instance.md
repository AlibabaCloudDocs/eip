# Associate an EIP with an SLB instance

This topic describes how to associate an elastic IP address \(EIP\) with a Server Load Balancer \(SLB\) instance. After you associate an EIP with an SLB instance, the SLB instance can forward requests from the Internet.

An SLB instance is created. For more information, see [Create an SLB instance](/intl.en-US/Classic Load Balancer/Quick Start (New Console)/Create an SLB instance.md).

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **SLB Instance**.|
    |**Select an instance to bind**|Select the SLB instance to be associated with the EIP.Make sure that the following requirements are met:

    -   The SLB instance is deployed in a virtual private cloud \(VPC\).
    -   The SLB instance and EIP belong to the same region.
    -   Each SLB instance can be associated with only one EIP.
**Note:** If you associate the EIP with an internal-facing SLB instance and the SLB instance has traffic of private network workloads, transient connections may occur. We recommend that you perform the association during off-peak hours or switch the workloads to another SLB instance. |


**Related topics**  


[AssociateEipAddress](/intl.en-US/API reference/EIP/AssociateEipAddress.md)

