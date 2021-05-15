# Overview

Elastic IP Address \(EIP\) supports two line types: BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. Both types support the pay-as-you-go and subscription billing methods. You may be charged when you associate a pay-as-you-go EIP or a subscription EIP with a cloud resource.

**Note:** BGP \(Multi-ISP\) is supported in all regions. BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region.

## Description

The billable items of EIPs vary based on the billing method. The following table describes the billable items for EIPs.

**Note:** "-" indicates that the fee is not charged and "√" indicates that the fee is charged.

|Billing method|Metering method|Configuration fee|Bandwidth usage fee|Data transfer fee|
|--------------|---------------|-----------------|-------------------|-----------------|
|Subscription|Pay-by-bandwidth|-|√|-|
|Pay-as-you-go|Pay-by-data-transfer|-   You are not charged a configuration fee if you associate an EIP with an Elastic Compute Service \(ECS\) instance that is deployed in a virtual private cloud \(VPC\).
-   You are charged a configuration fee if you associate an EIP with a NAT gateway, Server Load Balancer \(SLB\) instance, secondary elastic network interface \(ENI\), or high-availability virtual IP address \(HAVIP\).

|-|√|
|Pay-by-bandwidth|√|-|

## EIP association fee

You may be charged an EIP association fee based on the number of times that you associate EIPs.

**Note:** EIP association fees apply to users whose first-time purchases of EIPs are made after 00:00 \(UTC+8\), January 15, 2020. If you have purchased an EIP before 00:00 \(UTC+8\), January 15, 2020, you are not charged an association fee for the EIPs that you purchased before and after the time.

Alibaba Cloud provides daily quotas for users of EIPs. You are charged an association fee if the number of times that you associate EIPs exceeds the daily quota. The daily quota is calculated by using the formula: The number of times that you can use an account to associate EIPs with resources in a region = 5 × N \(Number of EIPs that belong to the account\). If the number of times that you associate EIPs exceeds the daily quota,the association fee is calculated by using the formula: Association fee = \(Number of times that you associate EIPs - Daily quota\) × USD 0.149. Association fees are calculated and bills are generated on a daily basis.

**Note:** The number of times that you can associate EIPs in a region is five times the number of the EIPs that belong to your account. For more information about how to view the daily quota, see [Manage quotas](/intl.en-US/User Guide/Manage quotas.md).

For example, if your account has 20 EIPs, you can associate EIPs 100 times in each region within a calendar day. In this case, you are not charged an association fee. If you associate EIPs more than 100 times, you are charged an association fee.If you associate EIPs 101 times, the association fee is USD 0.149.If you associate EIPs 110 times, the association fee is USD 1.49.You are charged USD 0.149 for each additional number of times that exceeds 100.

