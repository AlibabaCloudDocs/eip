# Associate an EIP with an ECS instance

This topic describes how to associate an elastic IP address \(EIP\) with an Elastic Compute Service \(ECS\) instance that is deployed in a Virtual Private Cloud \(VPC\) network. An ECS instance that is associated with an EIP can communicate with the Internet.

An ECS instance is created. For more information, see [Create an instance by using the provided wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the provided wizard.md).

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where your EIP is created.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters, and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **ECS Instance**.|
    |**Binding Mode**|Select the mode in which you want to associate the EIP.Only Normal mode is supported. In Normal mode:

    -   Both the private and public IP addresses of the ECS instance are available for use.
    -   The EIP is not displayed in the operating system. You must call the DescribeInstances operation to query the public IP address with which the ECS instance is associated. For more information, see [DescribeInstances](/intl.en-US/API Reference/Instances/DescribeInstances.md).
    -   EIPs in normal mode do not support NAT application layer gateway \(ALG\) protocols such as H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), Real Time Streaming Protocol \(RTSP\), and Trivial File Transfer Protocol \(TFTP\). |
    |**Select an instance to bind**|Select the ECS instance to be associated with the EIP.The ECS instance that you select must meet the following requirements:

    -   The ECS instance is deployed in a VPC network.
    -   The ECS instance is in the Running or Stopped state.
    -   Each ECS instance can be associated with only one EIP.
    -   The ECS instance and the EIP are created in the same region.
    -   The ECS instance is not associated with a public IP address or another EIP. |


**Related topics**  


[AssociateEipAddress](/intl.en-US/API reference/EIP/AssociateEipAddress.md)

