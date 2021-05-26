# Associate an EIP with an EIP bandwidth plan

EIP bandwidth plans support bandwidth sharing and transferring on a regional scale. After you purchase an EIP bandwidth plan, you can associate elastic IP addresses \(EIPs\) in the same region with the EIP bandwidth plan. This way, the EIPs share the bandwidth of the EIP bandwidth plan. This saves costs of Internet bandwidth.

-   Make sure that an EIP is purchased and the following requirements are met:

    -   The EIP is billed on a pay-as-you-go basis.
    -   The EIP and the EIP bandwidth plan are purchased in the same region.
    -   The line type of the EIP and the line type of the EIP bandwidth plan are the same.
    For more information, see [Apply for new EIPs](/intl.en-US/User Guide/Create an EIP/Apply for new EIPs.md).

-   An EIP bandwidth plan is purchased. For more information, see [Purchase an EIP bandwidth plan](/intl.en-US/User Guide/Create an EIP bandwidth plan.md).

EIP bandwidth plans are billed on a pay-by-data-transfer basis. For more information, see [Billing](/intl.en-US/Pricing/Billing.md).

After you associate EIPs with an EIP bandwidth plan:

-   Elastic Compute Service \(ECS\) instances, Server Load Balancer \(SLB\) instances, and NAT gateways that are associated with the EIPs share the bandwidth of the EIP bandwidth plan.
-   The predefined bandwidth limits of the EIPs become invalid. The bandwidth limits of the EIPs are the same as the bandwidth limit of the EIP bandwidth plan.
-   The predefined billing methods of the EIPs become invalid. The EIPs function as public IP addresses. Data transfer is not charged for the EIPs.
-   Configuration fees of EIPs are not determined by whether the EIPs are associated with an EIP bandwidth plan.
    -   You are not charged a configuration fee for an EIP if you associate the EIP with an ECS instance in a virtual private cloud \(VPC\).
    -   You are charged a configuration fee for an EIP if you associate the EIP with a NAT gateway, SLB instance, secondary elastic network interface \(ENI\), or high-availability virtual IP address \(HAVIP\).

**Note:**

-   After you associate an EIP with a NAT gateway, when you associate the EIP with an EIP bandwidth plan, your service may be temporarily interrupted. Proceed with caution.
-   You can associate at most 100 EIPs with each EIP bandwidth plan. To associate more EIPs, request a quota increase. For more information, see [Manage resource quotas](/intl.en-US/User Guide/Manage resource quotas.md).

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, find the EIP that you want to manage and choose **![More](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1576420061/p140904.png)** \> **Add to Shared Bandwidth Package** in the **Actions** column.

4.  In the dialog box that appears, select an EIP bandwidth plan and click **OK**.


**Related topics**  


[AddCommonBandwidthPackageIp](/intl.en-US/API reference/EIP bandwidth plan/AddCommonBandwidthPackageIp.md)

