# Billing overview

Elastic IP Address \(EIP\) supports two line types: BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. Both types support the pay-as-you-go and subscription billing methods. You may be charged an association fee when you associate a pay-as-you-go EIP or a subscription EIP with a cloud resource.

**Note:** BGP \(Multi-ISP\) is supported in all regions. BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region.

## Billable items

The billable items of EIPs vary based on the billing method or metering method. The following table describes the billable items for EIPs.

**Note:** "-" indicates that the fee is not charged and "√" indicates that the fee is charged.

|Billing method|Metering method|Configuration fee|Bandwidth fee|Data transfer fee|
|--------------|---------------|-----------------|-------------|-----------------|
|Subscription|Pay-by-bandwidth|-|√|-|
|Pay-as-you-go|Pay-by-data-transfer|-   You are not charged a configuration fee if you associate an EIP with an Elastic Compute Service \(ECS\) instance that is deployed in a virtual private cloud \(VPC\) or an elastic container instance. For more information, see [Associate an EIP with a pod](/intl.en-US/User Guide for Serverless Kubernetes Clusters/Serverless cluster best practices/Associate an EIP with a pod.md).
-   You are charged a configuration fee if you associate an EIP with a NAT gateway, Server Load Balancer \(SLB\) instance, secondary elastic network interface \(ENI\), or high-availability virtual IP address \(HAVIP\).

|-|√|
|Pay-by-bandwidth|√|-|

## Association fees

You may be charged an association fee when you associate an EIP with a cloud resource. EIP association fees are calculated based on the number of times that you associate EIPs in a region.

**Note:** You are charged EIP association fees if your first-time purchase of EIPs was made after 00:00 \(UTC+8\), January 15, 2020. If you purchase EIPs before 00:00 \(UTC+8\), January 15, 2020, you are not charged EIP association fees.

Alibaba Cloud provides daily quotas for EIP users. You are charged an association fee if the number of times that you associate EIPs in a region within one day exceeds the daily quota. Daily quota = Number of times that you can associate EIPs in a region within one day = 5 × N \(Number of EIPs that can be owned by your account\). If the number of times that you associate EIPs exceeds the daily quota,the association fee is calculated by using the formula: Association fee = \(Number of times that you associate EIPs - Daily quota\) × USD 0.149. Association fees are calculated and bills are generated on a daily basis.

**Note:** The number of times that you can associate EIPs in a region within one day is five times the number of the EIPs that can be owned by your account. For more information about how to view the number of EIPs that can be owned by your account, see [Manage quotas](/intl.en-US/User Guide/Manage quotas.md).

If your account can have at most 20 EIPs, you can associate EIPs 100 times in each region within one day free of charge. If you associate EIPs more than 100 times, you are charged USD 0.149 for each additional number of times that exceeds 100. For example, if you associate EIPs 101 times in a region within one day, the association fee is USD 0.149. If you associate EIPs 110 times in a region within one day, the association fee is USD 1.49.

