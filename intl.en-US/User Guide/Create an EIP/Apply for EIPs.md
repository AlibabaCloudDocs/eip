# Apply for EIPs

An elastic IP address \(EIP\) is a public IP address that you can purchase and use as an independent resource. You can apply for new EIPs, released EIPs, or contiguous EIPs.

## Operations

-   [Apply for new EIPs](#section_f6y_iq4_xcz)
-   [Recover a released EIP](#section_umn_6gx_1x4)
-   [Apply for continuous EIPs](/intl.en-US/User Guide/Create an EIP/Apply for continuous EIPs.md)

## Apply fornew EIPs

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  On the **Elastic IP Addresses** page, click **Create EIP**.

3.  On the page that appears, set the following parameters, click **Buy Now**, and then complete the payment.

    |Parameter|Description|
    |:--------|:----------|
    |**Billing Method**|Select a billing method for the EIP.

The subscription and pay-as-you-go billing methods are supported.

    -   **Subscription**: A one-time fee is charged based on the specified maximum bandwidth value of the EIP. For more information, see [Subscription](/intl.en-US/Pricing/Subscription.md).
    -   **Pay-As-You-Go**: You are charged for the resources that you use. Pay-as-you-go EIPs are charged by data transfer or bandwidth. For more information, see [Pay-as-you-go](/intl.en-US/Pricing/Pay-as-you-go.md). |
    |**Subscription**|
    |**Region**|Select a region where you want to create the EIP. You can associate the EIP with an Elastic Compute Service \(ECS\) instance, NAT gateway, Server Load Balancer \(SLB\) instance, high-availability virtual IP address \(HAVIP\), or secondary elastic network interface \(ENI\). Make sure that the EIP and the cloud resource are deployed in the same region. |
    |**Connection Type**|Select a line type for the EIP.     -   **BGP \(Multi-ISP\)**: Up to 89 high-quality BGP lines are available worldwide. Direct connections can be established across all regions in mainland China through lines of the following Internet service providers \(ISPs\): China Telecom, China Unicom, China Mobile, China Mobile Tietong, China Netcom, China Education and Research Network \(CERNET\), National Radio and Television Administration, Dr. Peng Telecom & Media Group, and Founder Broadband Network.
    -   **BGP \(Multi-ISP\) Pro**: BGP \(Multi-ISP\) Pro is provided to improve the efficiency of data transmission from regions outside mainland China to mainland China. Compared with BGP \(Multi-ISP\), when BGP \(Multi-ISP\) Pro provides services to clients in mainland China \(excluding data centers\), cross-border connections are established without using international ISP services. This reduces network latency.

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region. |
    |**Network Mode**|Select a network type for the EIP. You can select only Public. |
    |**Bandwidth value**|Specify a maximum bandwidth value for the EIP.|
    |**Name**|Enter a name for the EIP. The name must be 2 to 128 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter. |
    |**Quantity**|Specify the number of EIPs that you want to purchase.|
    |**Service Time**|Specify the subscription duration of the EIP.|
    |**Pay-As-You-Go**|
    |**eip\_region\_no**|Select a region where you want to create the EIP. You can associate an EIP with a cloud resource, such as an ECS instance, NAT gateway, SLB instance, HAVIP, or secondary ENI. Make sure that the EIP and the cloud resource are deployed in the same region. |
    |**ISP**|Select a line type for the EIP.     -   **BGP \(Multi-ISP\)**: Up to 89 high-quality BGP lines are available worldwide. Direct connections can be established across all regions in mainland China through lines of the following Internet service providers \(ISPs\): China Telecom, China Unicom, China Mobile, China Mobile Tietong, China Netcom, China Education and Research Network \(CERNET\), National Radio and Television Administration, Dr. Peng Telecom & Media Group, and Founder Broadband Network.
    -   **BGP \(Multi-ISP\) Pro**: BGP \(Multi-ISP\) Pro is provided to improve the efficiency of data transmission from regions outside mainland China to mainland China. Compared with BGP \(Multi-ISP\), when BGP \(Multi-ISP\) Pro provides services to clients in mainland China \(excluding data centers\), cross-border connections are established without using international ISP services. This reduces network latency.

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region. |
    |**Network Mode**|Select a network type for the EIP. You can select only Public. |
    |**eip\_flow\_out**|Select a metering method for the EIP.     -   **By bandwidth**: Bills are generated on a daily basis based on the specified maximum bandwidth value of the EIP.
    -   **By traffic**: Bills are generated on an hourly basis based on the amount of traffic. |
    |**eip\_bandwidth\_max**|Specify a maximum bandwidth value for the EIP.|
    |**Name**|Enter a name for the EIP. The name must be 2 to 128 characters in length, and can contain digits, periods \(.\), underscores \(\_\), and hyphens \(-\). It must start with a letter. |
    |**Billing Cycle**|Select a billing cycle for the EIP. For pay-by-bandwidth EIPs that are billed on a daily basis, you can select only Day. For pay-by-data-transfer EIPs that are billed on an hourly basis, you can select only Hour. |
    |**Quantity**|Specify the number of EIPs that you want to purchase.|


## Recover a released EIP

You can specify the IP address or EIP ID to recover an EIP that is released by your Alibaba Cloud account within the last seven days. If the released EIP is already assigned to another Alibaba Cloud account, locked due to security reasons, or not for sale, you cannot recover the EIP.

To recover a released EIP,[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).

-   Recover an EIP that has been released for more than seven days.
-   Recover the static public IP address of an Elastic Compute Service \(ECS\) instance.
-   You can recover EIPs at most 20 times per month. To recover EIPs more than 20 times, request a quota increase.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, click the **Request Custom IP** tab.

4.  In the **Request Custom IP** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**EIP Type**|Select **Request Specific EIP**. You can specify the IP address or ID of the EIP. By default, a recovered EIP is billed on a pay-by-data-transfer basis and the maximum bandwidth of the EIP is 5 Mbit/s. |
    |**Request Method**|Select a request method:    -   **Request by IP Address**: Specify the IP address of the EIP or the static public IP address of the ECS instance.
    -   **Request by EIP Instance ID**: Specify the ID of the EIP. |
    |**IP Address**|Enter the IP address of the EIP that you want to recover.|
    |**Instance ID**|Enter the ID of the EIP that you want to recover. **Note:** You can recover only EIPs that you have used before. |
    |**Connection Type**|Select a line type for the EIP:    -   **BGP \(Multi-ISP\)**
    -   **BGP \(Multi-ISP\) Pro**

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region.

For more information about the differences between BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro, see [Line types](/intl.en-US/User Guide/Overview.md). |


## Apply for contiguous EIPs

You can apply for contiguous EIPs to facilitate network management. A contiguous EIP group consists of contiguous EIPs. Contiguous EIPs are similar to standard EIPs that are randomly allocated from the IP address pool of Alibaba Cloud. You can associate contiguous EIPs with Elastic Compute Service \(ECS\) instances, internal-facing Server Load Balancer \(SLB\) instances, or secondary elastic network interfaces \(ENIs\) deployed in a virtual private cloud \(VPC\). You can also associate contiguous EIPs with NAT gateways or high-availability virtual IP addresses \(HAVIPs\). After you associate contiguous EIPs with cloud resources, the cloud resources can use the contiguous EIPs for communication.

Before you apply for contiguous EIPs, take note of the following rules:

-   Only Alibaba Cloud accounts that are included in the whitelist can apply for contiguous EIPs. To apply for contiguous EIPs,[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).

    **Note:** Alibaba Cloud provides a limited number of contiguous EIPs. After you submit a ticket, Alibaba Cloud reviews your application. After your application is approved, you can apply for contiguous EIPs.

-   The following table describes the differences between contiguous EIPs and standard EIPs.

    |Item|Contiguous EIP|Standard EIP|
    |----|--------------|------------|
    |Billing Method|Supports only the pay-as-you-go billing method.|Supports the subscription and pay-as-you-go billing methods.|
    |Billing method switching|You cannot switch the billing method from pay-as-you-go to subscription.|You can switch the billing method from pay-as-you-go to subscription.|
    |Billable item|In addition to the billable items of standard EIPs, you are charged a specification fee based on the number of contiguous EIPs. For more information about specification fees,[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).|No specification fee is charged.|


1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the left-side navigation pane, choose **Elastic IP Addresses** \> **Elastic IP Addresses**.

3.  In the top navigation bar, select the region where you want to apply for contiguous EIPs.

4.  On the **Elastic IP Addresses** page, click **Request Custom IP**.

5.  In the **Request Custom IP** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**EIP Type**|Select **Request Continuous EIP Group**.|
    |**Continuous EIP Group Mask**|Select the subnet mask length of the contiguous EIP group, and select **I have read and understand that:**. Valid values: 24 to 28. The number of contiguous EIPs varies based on the selected mask length.

    -   /28: allocates 16 contiguous EIPs by default.
    -   /27: allocates 32 contiguous EIPs by default.
    -   /26: allocates 64 contiguous EIPs by default.
    -   /25: allocates 128 contiguous EIPs by default.
    -   /24: allocates 256 contiguous EIPs by default.
**Note:** In some scenarios, the actual number of allocated IP addresses may be less than the expected number because one, three, or four IP addresses may be reserved. |
    |**Network Type**|Select a network type for the contiguous EIPs.     -   **Public**: After contiguous EIPs are associated with cloud resources, the cloud resources can use the contiguous EIPs to communicate with the Internet.
    -   **Hybrid Cloud**: The contiguous EIPs can be used to establish communication within a hybrid cloud.

**Note:** You can select Hybrid Cloud only when your Alibaba Cloud account is included in the whitelist. To select Hybrid Cloud, [submit a ticket](https://page-intl.aliyun.com/form/act150080846/index.htm). |
    |**Billing Method**|Select a billing method for the contiguous EIPs.     -   **Pay by Bandwidth**: Bills are generated on a daily basis. You are charged based on specified bandwidth value instead of actual resource usage.
    -   **Pay by Traffic**: Bills are generated on an hourly basis based on the amount of data transferred over the Internet.
**Note:** Contiguous EIPs that are used within a hybrid cloud support only the pay-by-bandwidth billing method. Pay-by-data-transfer is not supported. |
    |**Bandwidth**|Specify a bandwidth value for the contiguous EIPs. Valid values: 1 to 200. Unit: Mbit/s. |


**Related topics**  


[AllocateEipAddress](/intl.en-US/API reference/EIP/AllocateEipAddress.md)

