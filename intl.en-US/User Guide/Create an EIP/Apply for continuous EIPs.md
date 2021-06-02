# Apply for continuous EIPs

This topic describes how to apply for a group of continuous elastic IP addresses \(EIPs\). Continuous EIPs can facilitate network management.

You are in the whitelist that allows users to create continuous EIPs. To apply for continuous EIPs,[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).

**Note:** Alibaba Cloud provides limited number of continuous EIPs. You must be authorized by Alibaba Cloud before you can apply for continuous EIPs. You can apply for continuous EIPs after the permissions are granted.

A continuous EIP group consists of continuous EIPs that are in sequential order. Continuous EIPs are similar to standard EIPs that are randomly allocated from the IP address pool of Alibaba Cloud. You can associate a continuous EIP with an Elastic Compute Service \(ECS\) instance, internal-facing Server Load Balancer \(SLB\) instance, or secondary elastic network interface \(ENI\) deployed in a virtual private cloud \(VPC\). You can also associate a continuous EIP with a NAT gateway or high-availability virtual IP address \(HAVIP\). After you associate a continuous EIP with a cloud resource, the cloud resource can use the continuous EIP for communication.

The following table describes the differences between continuous EIPs and standard EIPs.

|Continuous EIP|Standard EIP|
|--------------|------------|
|Supports only the pay-as-you-go billing method.|Supports the subscription and pay-as-you-go billing methods.|
|You cannot switch the billing method from pay-as-you-go to subscription.|You can switch the billing method from pay-as-you-go to subscription.|
|In addition to the billable items of standard EIPs, you are charged a specification fee based on the number of continuous EIPs. For more information about specification fees,[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).|No specification fee is charged.|

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the left-side navigation pane, choose **Elastic IP Addresses** \> **Elastic IP Addresses**.

3.  In the top navigation bar, select the region where you want to apply for continuous EIPs.

4.  On the **Elastic IP Addresses** page, click **Request Custom IP**.

5.  In the **Request Custom IP** dialog box, set the following parameters and click **OK**.

    |Parameter|Description|
    |---------|-----------|
    |**EIP Type**|Select **Request Continuous EIP Group**.|
    |**Continuous EIP Group Mask**|Select the subnet mask length of the continuous EIP group, and select **I have read and understand that:**. Valid values: /28 to /24. The number of continuous EIPs varies based on the selected mask length.

    -   /28: allocates 16 continuous EIPs by default.
    -   /27: allocates 32 continuous EIPs by default.
    -   /26: allocates 64 continuous EIPs by default.
    -   /25: allocates 128 continuous EIPs by default.
    -   /24: allocates 256 continuous EIPs by default.
**Note:** In some scenarios, the actual number of allocated IP addresses may be less than the expected number because one, three, or four IP addresses may be reserved. |
    |**Network Type**|Select a network type for the continuous EIPs.     -   **Public**: After a continuous EIP is associated with a cloud resource, the cloud resource can use the continuous EIP to communicate with the Internet.
    -   **Hybrid Cloud**: After a continuous EIP is associated with a cloud resource, the cloud resource can use the continuous EIP to establish communication within a hybrid cloud.

**Note:** You can specify the network type only when your account is included in the whitelist. To use this feature, contact your product manager from Alibaba Cloud. |
    |**Billing Method**|Select a billing method for the continuous EIPs.     -   **Pay by Bandwidth**: Bills are generated on a daily basis. You are charged based on specified bandwidth limits instead of actual resource usage.
    -   **Pay by Traffic**: Bills are generated on an hourly basis based on the amount of data transfer sent over the Internet.
**Note:** Continuous EIPs that are used within a hybrid cloud support only the pay-by-bandwidth billing method. Pay-by-data-transfer is not supported. |
    |**Bandwidth**|Specify a bandwidth limit for the continuous EIPs. Valid values: 1 to 200. Unit: Mbit/s. |


After the application for continuous EIPs is approved, the continuous EIPs are labeled with **Continuous EIP**.

![Apply for continuous EIPs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1905958951/p88230.png)

**Related topics**  


[AllocateEipSegmentAddress](/intl.en-US/API reference/EIP/AllocateEipSegmentAddress.md)

