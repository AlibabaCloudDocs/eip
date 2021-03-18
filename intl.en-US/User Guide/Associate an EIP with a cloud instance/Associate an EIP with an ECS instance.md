# Associate an EIP with an ECS instance

This topic describes how to associate an elastic IP address \(EIP\) with an Elastic Compute Service \(ECS\) instance that is deployed in a virtual private cloud \(VPC\). ECS instances can communicate with the Internet after they are associated with EIPs.

An ECS instance is created. For more information, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage, and click **Bind Resource** in the **Actions** column.

4.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**Instance Type**|Select **ECS Instance**.|
    |**Binding mode**|Select the mode in which you want to associate the EIP.Only the NAT mode is supported. In NAT mode:

    -   The EIP is associated with the ECS instance in NAT mode. The private IP address and public IP address of the ECS instance are both available.
    -   The EIP is not displayed in the operating system. You must call the DescribeInstances operation to query the public IP address with which the ECS instance is associated. For more information, see [DescribeInstances](/intl.en-US/API Reference/Instances/DescribeInstances.md).
    -   The EIP does not support NAT application layer gateway \(ALG\) protocols such as H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), Real Time Streaming Protocol \(RTSP\), or Trivial File Transfer Protocol \(TFTP\). |
    |**Select an instance to bind**|Select the ECS instance to be associated with the EIP.The ECS instance that you select must meet the following requirements:

    -   The ECS instance is deployed in a VPC.
    -   The ECS instance is in the Running or Stopped state.
    -   Each ECS instance can be associated with only one EIP.
    -   The ECS instance and EIP belong to the same region.
    -   The ECS instance is not associated with a public IP address or another EIP. |


**Related topics**  


[AssociateEipAddress](/intl.en-US/API reference/EIP/AssociateEipAddress.md)

