---
keyword: [EIPs, public IP addresses, EIP bandwidth plans, data transfer plans]
---

# Bandwidth and data transfer

This topic provides answers to some frequently asked questions about bandwidth and data transfer of Elastic IP Addresses \(EIP\).

-   [After I associate an EIP with an Elastic Compute Service \(ECS\) instance, is the bandwidth of the ECS instance affected?](#section_svg_4cp_wxa)
-   [Why does the bandwidth fail to reach the maximum bandwidth value that I purchased in a File Transfer Protocol \(FTP\) staging environment?](#section_lxh_kvk_y93)
-   [What can I do if the system prompts that traffic has reached the upper limit when I change the resource group of an EIP?](#section_39j_bpz_qm9)
-   [Is the bandwidth that I purchase for an EIP shared by multiple users?](#section_1os_v0b_6sw)

## After I associate an EIP with an Elastic Compute Service \(ECS\) instance, is the bandwidth of the ECS instance affected?

The maximum bandwidth of the ECS instance is limited by the specification of the ECS instance and the maximum bandwidth of the EIP. For more information about specifications of ECS instances, see [Instance families with local SSDs](/intl.en-US/Instance/Instance type families/Instance families with local SSDs.md).

## Why does the bandwidth fail to reach the maximum bandwidth value that I purchased in a File Transfer Protocol \(FTP\) staging environment?

The upload and download speed in an FTP staging environment cannot represent the actual bandwidth. The reasons are:

-   The FTP software itself has a speed limit.
-   The upload and download speed is affected by the read and write speed of the disk. For a more accurate result, we recommend that you use iPerf.

## What can I do if the system prompts that traffic has reached the upper limit when I change the resource group of an EIP?

You can call the operation that adds an EIP to a resource group at most 60 times per minute. If you call the operation more than 60 times within one minute, the system prompts that traffic has reached the upper limit.

## Is the bandwidth that I purchase for an EIP shared by multiple users?

In a region, the maximum bandwidth varies based on the actual scenario:

-   In scenarios where the sum of maximum bandwidth for pay-by-data-transfer EIPs does not exceed 5 Gbit/s and the total sum of maximum bandwidth for pay-by-bandwidth EIPs does not exceed 50 Gbit/s, the bandwidth is used only by the user who purchases it.
-   In scenarios where the total sum of maximum bandwidth for pay-by-data-transfer EIPs exceeds 5 Gbit/s or the total sum of maximum bandwidth for pay-by-bandwidth EIPs exceeds 50 Gbit/s, the maximum bandwidth value is for reference only and is not guaranteed. In this case, if the bandwidth demand exceeds the supply, the maximum bandwidth value may be limited. For more information, see [Limits](/intl.en-US/.md).

