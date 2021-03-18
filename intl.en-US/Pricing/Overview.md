# Overview

Elastic IP Address \(EIP\) supports two line types: BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. Both types support the pay-as-you-go and subscription billing methods. You may be charged when you associate a pay-as-you-go EIP or a subscription EIP with a cloud resource.

**Note:** BGP \(Multi-ISP\) is supported in all regions. BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region.

## Description

EIPs of different billing methods and metering methods are charged for different billable items. The following table lists the billable items for EIPs.

**Note:**

-   "-" indicates that the fee is not charged and "✔" indicates that the fee is charged.
-   Subscription and pay-as-you-go EIPs purchased in the India \(Mumbai\) and UAE \(Dubai\) regions do not support the pay-by-bandwidth metering method.

|Billing Method|Metering method|Configuration fee|Bandwidth usage fee|Data transfer fee|
|--------------|---------------|-----------------|-------------------|-----------------|
|Subscription|Pay-by-bandwidth|-|√|-|
|Pay-as-you-go|Pay-by-data-transfer|-   No configuration fee is charged when an EIP is associated with an Elastic Compute Service \(ECS\) instance that is deployed in a virtual private cloud \(VPC\).
-   Configuration fees are charged when an EIP is associated with a NAT gateway, Server Load Balancer \(SLB\) instance, secondary elastic network interface \(ENI\), or high-availability virtual IP address \(HAVIP\).

|-|√|
|Pay-by-bandwidth|√|-|

## EIP association fee

EIP association fees may be charged per Alibaba Cloud account per region based on the following rules:

**Note:** Users who purchase EIPs for the first time after 00:00 \(UTC+8\), January 15, 2020 are charged for associating EIPs with other resources. Users who purchased EIPs before 00:00 \(UTC+8\), January 15, 2020 can associate EIPs with other resources free of charge.

If the number of times you associate your EIPs that belong to an Alibaba Cloud account in a region within a calendar day is less than or equal to five times the quota, no association fee is charged. For the times that exceed five times the quota,you are charged at USD 0.149 per time. Association fees are calculated and bills are generated on a daily basis.

**Note:** The quota equals the default number of EIPs that you can keep for your Alibaba Cloud account. For more information about how to view the quota, see [Quota management](/intl.en-US/User Guide/Quota management.md).

For example, if you can keep 20 EIPs for your Alibaba Cloud account, you can associate EIPs that belong to your Alibaba Cloud account 100 times in each region within a calendar day free of charge. For the times that exceed 100,you are charged at USD 0.149 per time, which means that you are charged at USD 0.149 per time from the 101st association.you are charged at USD 0.149 per time, which means that you are charged at USD 0.149 per time from the 110th association.USD 1.49.

