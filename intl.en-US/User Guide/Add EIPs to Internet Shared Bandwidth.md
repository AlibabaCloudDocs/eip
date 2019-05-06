# Add EIPs to Internet Shared Bandwidth {#task_bh5_dll_vdb .task}

Internet Shared Bandwidth provides region-level bandwidth sharing. With Internet Shared Bandwidth, ECS instances, NAT Gateways and VPC SLB instances associated with EIPs added to the bandwidth can share the bandwidth.

Make sure the following conditions are met before you add EIPs to an Internet Shared Bandwidth instance:

-   The EIP adopts the Pay-As-You-Go billing method.

-   The EIP and the Internet Shared Bandwidth instance must be in the same region.

-   You will not add more than 100 EIPs to an Internet Shared Bandwidth instance. You can open a ticket to increase the quota.

-   An Internet Shared Bandwidth instance is created. For more information, see [Create an Internet Shared Bandwidth instance](../../../../reseller.en-US/User Guide/Create an Internet Shared Bandwidth instance.md#).


After you add EIPs to an Internet Shared Bandwidth instance:

-   ECS instances, SLB instances, and NAT Gateways associated with the EIPs share the bandwidth.

-   The original peak bandwidth of each added EIP loses effect and the peak bandwidth of the Internet Shared Bandwidth takes effect.

-   The original billing method of each added EIP loses effect and no additional traffic or bandwidth fee is incurred. Only EIP retention fee is charged on EIPs associated with NAT Gateways or SLB instances, and no additional fee is charged on EIPs associated with ECS instances.


1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  Select the target region and find the target EIP.
4.  Click **More** \> **Add to Shared Bandwidth Package**.
5.  Select the target Internet Shared Bandwidth instance and then click **OK**.

