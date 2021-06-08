# Apply for, allocate, and recover an EIP

This topic provides answers to some frequently asked questions about applying for, allocating, and recovering elastic IP addresses \(EIPs\).

-   [Why does the message "eip frequent purchase" appear when I apply for an EIP?](#section_dm3_h54_7wx)
-   [Why am I unable to access an EIP?](#section_dk9_ltz_iai)
-   [How are EIPs allocated?](#section_gr9_7ut_dxo)
-   [When can I recover an EIP after I release it?](#section_4pa_nt8_hum)

## Why does the message "eip frequent purchase" appear when I apply for an EIP?

Cause: The frequency at which you send requests to apply for and change EIPs has triggered a security alert. As a result, your applications for EIPs are denied for a limited period of time.

Solution: If the number of EIPs that you apply for in the next seven days does not exceed the quota, the system automatically removes the limit after seven days. For more information about how to view the number of EIPs that can be owned by an Alibaba Cloud account, see [Manage quotas](/intl.en-US/User Guide/Manage quotas.md).

## Why am I unable to view the EIP that I purchased?

Possible causes:

-   The system is in the process of allocating the EIP to your account. The process normally takes 3 to 5 minutes.
-   The region that you selected is different from the region where the EIP is purchased.

Solution: Go to the **Billing Management** page and click **Orders**. You can find the order of the EIP that you purchased on the Orders page. To view the region where the EIP is purchased, click View Details. Then, return to the EIP console and select the region where the EIP is purchased. You can view information about the EIP on the Elastic IP Addresses page.

## Why am I unable to access an EIP?

Possible causes:

-   The EIP is not associated with a cloud resource.
-   A security group rule is configured for the Elastic Compute Service \(ECS\) instance that is associated with the EIP. For example, if the ECS instance is added to a security group that denies access to port 80, you cannot access the EIP over port 80.
-   The EIP has an overdue payment.

## How are EIPs allocated?

By default, after you apply for an EIP, the system randomly allocates an EIP to your account. If you have applied for and released EIPs multiple times, the system may allocate EIPs that you have used before to your account.

## When can I recover an EIP after I release it?

After you release an EIP, you can recover the EIP before the next hour begins by specifying its IP address. For example, if you release an EIP at 05:05 \(UTC+8\) on December 27, you can recover the EIP before 06:00 \(UTC+8\) on December 27 by specifying its IP address.

