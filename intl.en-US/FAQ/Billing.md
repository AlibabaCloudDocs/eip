# Billing

This topic provides answers to some commonly asked questions about the billing of elastic IP addresses \(EIPs\).

-   [Why am I still charged after I release a pay-as-you-go EIP?](#section_t11_23y_fdv)
-   [Why do I need to set a maximum bandwidth value for a pay-by-data-transfer EIP?](#section_0a5_rz8_faa)
-   [Can I transfer an EIP to another Alibaba Cloud account?](#section_q29_e3a_p6a)
-   [Am I still charged for an EIP after I associate the EIP with an EIP bandwidth plan?](#section_554_wkr_x72)

## Why am I still charged after I release a pay-as-you-go EIP?

For a pay-as-you-go EIP, the bill is generated within the next hour. You receive the bill after the EIP is released. Upon its release, the system stops calculating the fee. For example:

After you release a pay-by-data-transfer EIP instance at 10:30, you receive the bill for the data usage from 10:00 to 11:00.

## Why do I need to set a maximum bandwidth value for a pay-by-data-transfer EIP?

For a pay-by-data-transfer EIP, we recommend that you set a maximum bandwidth value to avoid unnecessary fees due to excessive outbound traffic.

The maximum bandwidth is not guaranteed for a pay-by-data-transfer EIP. For example, if the maximum bandwidth value of a pay-by-data-transfer EIP is set to 200 Mbit/s, the peak bandwidth may not reach 200 Mbit/s. If you want to use an EIP with a guaranteed maximum bandwidth value, you must purchase a pay-by-bandwidth EIP or an EIP bandwidth plan.

## Can I transfer an EIP to another Alibaba Cloud account?

To transfer an EIP to another Alibaba Cloud account, the following requirements must be met:

-   The current Alibaba Cloud account to which the EIP belongs and the destination Alibaba Cloud account must belong to Alibaba Cloud China Site.
-   The billing method of the EIP to be transferred must be pay-as-you-go.
-   The EIP must not be associated with a cloud resource.
-   The EIP must not be locked due to risk control or have overdue payments.
-   The destination Alibaba Cloud account has good credit and has an account balance of at least CNY 100.

If all the preceding requirements are met, you can[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex) to transfer the EIP.

## Am I still charged for an EIP after I associate the EIP with an EIP bandwidth plan?

After you associate an EIP with an EIP bandwidth plan, whether the EIP is charged depends on the actual scenario:

-   In scenarios where the Elastic Compute Service \(ECS\) instance that is associated with the EIP is also associated with the EIP bandwidth plan, the maximum bandwidth of the EIP bandwidth plan replaces that of the EIP. In addition, the billing of the EIP stops regardless of its billing method.
-   In other scenarios, whether you are charged for an EIP is irrelevant to whether the EIP is associated with an EIP bandwidth plan. For example, in scenarios where the EIP is associated with a NAT gateway, associated with a Server Load Balancer \(SLB\) instance, or not associated with a cloud resource, you are charged for the EIP.

