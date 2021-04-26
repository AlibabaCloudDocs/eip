# Billing

This topic provides answers to some frequently asked questions about the billing of elastic IP addresses \(EIPs\).

-   [Can I renew multiple subscription EIPs at a time?](#section_h2t_4ks_41m)
-   [Why am I still charged after I release a pay-as-you-go EIP?](#section_t11_23y_fdv)
-   [Why do I need to set a maximum bandwidth value for a pay-by-data-transfer EIP?](#section_0a5_rz8_faa)
-   [Am I still charged for an EIP after I associate the EIP with an EIP bandwidth plan?](#section_554_wkr_x72)

## Can I renew multiple subscription EIPs at a time?

Yes.

You can go to the [Renewal](https://usercenter2-intl.aliyun.com/renew/manual) page to renew subscription EIPs.

## Why am I still charged after I release a pay-as-you-go EIP?

For a pay-as-you-go EIP, the bill is generated within the next hour. You receive the bill after the EIP is released. Upon its release, the system stops calculating the fee. For example:

After you release a pay-by-data-transfer EIP instance at 10:30, you receive the bill for the data transfer from 10:00 to 11:00.

## Why do I need to set a maximum bandwidth value for a pay-by-data-transfer EIP?

For a pay-by-data-transfer EIP, we recommend that you set maximum bandwidth to avoid unnecessary fees due to excessive outbound traffic.

The maximum bandwidth is not guaranteed for a pay-by-data-transfer EIP. For example, if the maximum bandwidth value of a pay-by-data-transfer EIP is set to 200 Mbit/s, the peak bandwidth may not reach 200 Mbit/s. If you want to use an EIP with a guaranteed maximum bandwidth value, you must purchase a pay-by-bandwidth EIP or an EIP bandwidth plan.

## Am I still charged for an EIP after I associate the EIP with an EIP bandwidth plan?

After you associate an EIP with an EIP bandwidth plan, whether the EIP is charged is based on the actual scenario:

-   In scenarios where the Elastic Compute Service \(ECS\) instance that is associated with the EIP is also associated with the EIP bandwidth plan, the maximum bandwidth of the EIP bandwidth plan replaces that of the EIP. In addition, the billing of the EIP stops regardless of its billing method.
-   In other scenarios, whether you are charged for an EIP is irrelevant to whether the EIP is associated with an EIP bandwidth plan. For example, in scenarios where the EIP is associated with a NAT gateway, associated with a Server Load Balancer \(SLB\) instance, or not associated with a cloud resource, you are charged for the EIP.

