# Use BGP \(Multi-ISP\) Pro EIPs to access web services with low latency

Compared with BGP \(Multi-ISP\), when BGP \(Multi-ISP\) Pro provides services to clients in mainland China \(excluding data centers\), cross-border connections are established to mainland China without using international Internet service provider \(ISP\) services. This reduces network latency. You can associate a \(Multi-ISP\) Pro elastic IP address \(EIP\) with an Elastic Compute Service \(ECS\) instance. Then, users in mainland China can access web services deployed in the China \(Hong Kong\) region with low latency.

Before you start, make sure the following requirements are met:

-   An Alibaba Cloud account is created. If you do not have an Alibaba Cloud account,[create an Alibaba Cloud account](https://account.alibabacloud.com/register/intl_register.htm).
-   A web service is deployed on an ECS instance in the China \(Hong Kong\) region. For more information, see [Create an instance by using the wizard](/intl.en-US/Instance/Create an instance/Create an instance by using the wizard.md).

The following scenario is used as an example in this topic. A web service is deployed on an ECS instance in the China \(Hong Kong\) region. The ECS instance is associated with a BGP \(Multi-ISP\) EIP. Network latency is high when users in mainland China access the web service deployed in the China \(Hong Kong\) region.

You can associate a BGP \(Multi-ISP\) Pro EIP with the ECS instance. Then, users in mainland China can access the web service deployed in the China \(Hong Kong\) region without using international ISP services. This reduces network latency.

![Scenario](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8059039951/p120847.png)

## Procedure

![Procedure](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8059039951/p120912.png)

## Step 1: Purchase a BGP \(Multi-ISP\) Pro EIP

The following example describes how to purchase a BGP \(Multi-ISP\) Pro EIP that is billed on a subscription basis.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  On the **Elastic IP Addresses** page, click **Create EIP**.

3.  On the buy page, select **Subscription**, and set the following parameters.

    -   **Region**: Select a region where you want to create the EIP. In this example, **China \(Hong Kong\)** is selected.
    -   **Connection Type**: Select the line type.

        **BGP \(Multi-ISP\) Pro** is selected in this example.

    -   **Network Type**: Select a network type. **Public** is selected in this example.
    -   **Bandwidth Value**: Select the maximum bandwidth value as needed. **10 Mbit/s** is selected in this example.
    -   **Name**: Enter a name for the EIP.

        The name must be 2 to 128 characters in length, and can contain letters, digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter.

    -   **Resource Group**: Select the resource group to which the EIP belongs.
    -   **Quantity**: Select the number of EIPs that you want to buy.
    -   **Service Time**: Select a subscription duration.
4.  Click **Buy Now** and complete the payment.

5.  Click **Console** and return to the **Elastic IP Addresses** page.


After you return to the **Elastic IP Addresses** page, you can view that the **Connection Type** of the EIP displays **BGP \(Multi-ISP\) Pro**.

![BGP (Multi-ISP) Pro](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8059039951/p120871.png)

## Step 2: Associate the EIP with an ECS instance

You can associate the EIP with an ECS instance that is deployed in a virtual private cloud \(VPC\). ECS instances can communicate with the Internet after they are associated with EIPs.

Perform the following steps to associate the EIP with an ECS instance:

1.  On the **Elastic IP Addresses** page, find the EIP created in [Step](#section_92f_mgi_0kw)[1](#section_92f_mgi_0kw), and click **Bind Resource** in the **Actions** column.

2.  In the **Bind Elastic IP Address to Resources** dialog box, set the following parameters.

    -   **Instance Type**: Select the type of the instance that you want to associate with the EIP. **ECS Instance** is selected in this example.
    -   **Binding Mode**: Select a binding mode.

        You can select only Normal. In Normal mode:

        -   Both the private and public IP addresses of the ECS instance are available.
        -   The EIP is not displayed in the operating system. You must call the DescribeInstances operation to query the public IP address of the ECS instance. For more information, see [DescribeInstances](/intl.en-US/API Reference/Instances/DescribeInstances.md).
        -   The EIP does not support NAT application layer gateway \(ALG\) protocols such as H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), Real Time Streaming Protocol \(RTSP\), or Trivial File Transfer Protocol \(TFTP\).
    -   **Select an Instance to Bind**: Select an ECS instance to be associated with the EIP.
3.  Click **OK**.


## Step 3: Test the network latency

After you associate the EIP with the ECS instance, you can test the network latency between a client in mainland China and the ECS instance that is deployed in the China \(Hong Kong\) region.

1.  Open the command-line interface on an on-premises machine that is deployed in mainland China.

2.  Run the `ping` command to `ping` the EIP that is associated with the ECS instance.

    The test result shows that the network latency is reduced when users in mainland China use the BGP \(Multi-ISP\) Pro EIP to access the ECS instance.

    ![Network latency between the BGP (Multi-ISP) Pro EIP and the ECS instance](../images/p120906.png "Network latency between the BGP (Multi-ISP) Pro EIP and the ECS instance")

    ![Access services deployed in the China (Hong Kong) region](../images/p120908.png "Network latency between the BGP (Multi-ISP) EIP and the ECS instance")

    **Note:** The preceding test result is for reference only. The actual network latency varies based on the network quality of the ISP.


