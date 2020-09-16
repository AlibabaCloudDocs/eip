# Apply fornew EIPs

This topic describes how to apply fornew elastic IP addresses \(EIPs\). An EIP is a public IP address that you can purchase and hold as an independent resource.

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  On the **Elastic IP Addresses** page, click **Create EIP**.

3.  On the Elastic IP page, set the following parameters, click **Buy Now** and complete the payment.

    |Parameter|Description|
    |:--------|:----------|
    |**Billing Method**|Select a billing method for the EIP.

The subscription and pay-as-you-go billing methods are supported.

    -   **Subscription**: A one-time fee is charged based on the specified maximum bandwidth of the EIP. For more information, see [Subscription](/intl.en-US/Pricing/Subscription.md).
    -   **Pay-as-you-go**: You are charged for the resources that you use. Pay-as-you-go EIPs are charged by data transfer or bandwidth. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md). |
    |**Subscription**|
    |**Region**|Select the region where you want to create the EIP. You can associate the EIP with an Elastic Compute Service \(ECS\) instance, NAT gateway, Server Load Balancer \(SLB\) instance, high-availability virtual IP address \(HAVIP\), or secondary elastic network interface \(ENI\). Make sure that the EIP and the cloud resources to be associated with are in the same region. |
    |**Internet Connection Type**|Select a line type for the EIP.     -   **BGP \(Multi-ISP\)**: Up to 89 high-quality BGP lines are available worldwide. Direct connections can be established across all regions of mainland China through lines of the following Internet Service Providers \(ISPs\): China Telecom, China Unicom, China Mobile, China Mobile Tietong, China Netcom, China Education and Research Network \(CERNET\), National Radio and Television Administration, Dr. Peng Telecom & Media Group, and Founder Broadband Network.
    -   **BGP \(Multi-ISP\) Pro**: BGP \(Multi-ISP\) Pro optimizes cross-border data transmission to improve the connection quality for international services. Compared with BGP \(Multi-ISP\), BGP \(Multi-ISP\) Pro can be used to establish direct cross-border connections without using international ISP services. This helps reduce network latency.

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region. |
    |**Network Mode**|Select a line type for the EIP. Only public network is supported. |
    |**Bandwidth value**|Specify a bandwidth value for the EIP.|
    |**Name**|Enter a name for the EIP. The name must be 2 to 128 characters in length, and start with a letter or Chinese character. It can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). |
    |**Quantity**|Specify the number of EIPs that you want to purchase.|
    |**Service Time**|Specify the subscription duration of the EIP.|
    |**Pay-as-you-go**|
    |**Region**|Select a region where you want to create the EIP. You can associate an EIP with a cloud resource, such as an ECS instance, NAT gateway, SLB instance, HAVIP, or secondary ENI. Make sure that the EIP and the cloud resource are deployed in the same region. |
    |**Internet Connection Type**|Select a line type for the EIP.     -   **BGP \(Multi-ISP\)**: Up to 89 high-quality BGP lines are available worldwide. Direct connections can be established across all regions of mainland China through lines of the following Internet Service Providers \(ISPs\): China Telecom, China Unicom, China Mobile, China Mobile Tietong, China Netcom, China Education and Research Network \(CERNET\), National Radio and Television Administration, Dr. Peng Telecom & Media Group, and Founder Broadband Network.
    -   **BGP \(Multi-ISP\) Pro**: BGP \(Multi-ISP\) Pro optimizes cross-border data transmission to improve the connection quality for international services. Compared with BGP \(Multi-ISP\), BGP \(Multi-ISP\) Pro can be used to establish direct cross-border connections without using international ISP services. This helps reduce network latency.

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region. |
    |**Network Mode**|Select a network type for the EIP. Only public network is supported. |
    |**Network Traffic**|Select a metering method for the EIP.     -   **By traffic**: Bills are generated hourly based on the amount of data transferred.
    -   **By bandwidth**: Bills are generated daily based on the specified maximum bandwidth of the EIP. |
    |**Max Bandwidth**|Specify the maximum bandwidth of the EIP.|
    |**Name**|Enter a name for the EIP. The name must be 2 to 128 characters in length, and start with a letter or Chinese character. It can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). |
    |**Billing Cycle**|Specify a billing cycle for the EIP. Pay-by-data-transfer EIPs are billed on an hourly basis and pay-by-bandwidth EIPs are billed on a daily basis. |
    |**Quantity**|Specify the number of EIPs that you want to purchase.|


**Related topics**  


[AllocateEipAddress](/intl.en-US/API reference/EIP/AllocateEipAddress.md)

