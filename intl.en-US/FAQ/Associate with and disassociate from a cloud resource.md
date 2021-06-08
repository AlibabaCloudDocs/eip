# Associate with and disassociate from a cloud resource

This topic provides answers to some frequently asked questions about associating an elastic IP address \(EIP\) with and disassociating an EIP from a cloud resource.

-   [What are the cloud resources with which I can associate EIPs?](#section_pap_ugo_jeh)
-   [Can I associate an EIP with multiple cloud resources?](#section_ote_h91_ws7)
-   [Can I associate an EIP with a cloud resource that is deployed in a different region?](#section_uu3_mql_s9i)
-   [Can I associate an EIP with a cloud resource that is deployed in a different zone?](#section_m0l_vvo_hts)
-   [How many EIPs can I associate with a cloud resource?](#section_n2w_txw_ezn)
-   [Can I associate an EIP with an SLB instance?](#section_n0f_o8t_tfe)
-   [Why am I unable to view the associated SLB instance in the EIP console?](#section_92e_zg7_cex)
-   [Why am I unable to associate an EIP with a NAT gateway?](#section_oml_rxp_5uc)
-   [If an EIP is associated with an ECS instance, can I use the DNAT feature of a NAT gateway to enable the ECS instance to provide Internet-facing services?](#section_wa9_tjs_eb2)
-   [Why am I unable to associate an EIP with an ECS instance?](#section_77i_2nv_smy)
-   [Why am I unable to view the EIP in the operating system of the ECS instance after I associate the EIP with the ECS instance?](#section_9y3_r2h_ran)
-   [How can I associate multiple EIPs with one ECS instance?](#section_c6w_x9a_b7m)
-   [Why am I unable to access services over the Internet after I associate an EIP with an ECS instance or ENI?](#section_m3e_7x3_xo5)
-   [Can I use an EIP as the origin IP address for Web Application Firewall \(WAF\)?](#section_qln_3p7_4ta)

## What are the cloud resources with which I can associate EIPs?

You can associate EIPs with Elastic Compute Service \(ECS\) instances, internal-facing Server Load Balancer \(SLB\) instances, secondary elastic network interfaces \(ENIs\), NAT gateways, and high-availability virtual IP addresses \(HAVIPs\). The ECS instances, internal-facing SLB instances, and secondary ENIs must be deployed in VPCs.

## Can I associate an EIP with multiple cloud resources?

No. You can associate an EIP with only one cloud resource.

## Can I associate an EIP with a cloud resource that is deployed in a different region?

No.

The EIP and the cloud resource with which you want to associate the EIP must be deployed in the same region. For example, an EIP deployed in the China \(Beijing\) region cannot be associated with a cloud resource deployed in the China \(Hangzhou\) region.

## Can I associate an EIP with a cloud resource that is deployed in a different zone?

Yes.

Zones do not apply to EIPs. If a cloud resource and an EIP are deployed in the same region, you can associate the EIP with the cloud resource.

## How many EIPs can I associate with a cloud resource?

-   NAT gateways

    You can associate at most 20 EIPs with a NAT gateway. You can associate at most 10 pay-by-data-transfer EIPs with a NAT gateway.

    You can go to the [Quota Management](https://vpc.console.aliyun.com/quota) page to increase the quota. For more information, see [Quota management](/intl.en-US/Common Configurations/Quota management.md).

-   HAVIPs

    You can associate only one EIP with an HAVIP.

-   SLB instances

    You can associate only one EIP with an internal-facing SLB instance that is deployed in a VPC.


## Can I associate an EIP with an SLB instance?

You can associate an EIP with only an internal-facing SLB instance that is deployed in a VPC. You cannot associate an EIP with an Internet-facing SLB instance. You can associate only one EIP with an internal-facing SLB instance that is deployed in a VPC. You can associate an EIP with an internal-facing SLB instance that is deployed in a VPC only in the EIP console. You cannot perform the operation in the SLB console.

## Why am I unable to view the associated SLB instance in the EIP console?

Possible causes:

-   The resource group ID of the EIP is different from that of the SLB instance.
-   If the account that you use to log on to the EIP console is a RAM user, the associated SLB instance is not displayed in the console. You must use the Alibaba Cloud account that grants the permissions to the RAM user to log on to the EIP console.

## Why am I unable to associate an EIP with a NAT gateway?

If you purchased a NAT service plan before January 26, 2018, you must use the NAT service plan to provide public IP addresses for the NAT gateway. To associate an EIP with a NAT gateway, [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex).

## If an EIP is associated with an ECS instance, can I use the DNAT feature of a NAT gateway to enable the ECS instance to provide Internet-facing services?

No.

The limits are:

-   If an EIP is associated with an ECS instance, you cannot use the DNAT feature of a NAT gateway to enable the ECS instance to provide Internet-facing services.

    Before you can use the DNAT feature, you must disassociate the EIP from the ECS instance. After you disassociate the EIP, you can create DNAT entries for the ECS instance. For more information, see [Disassociate EIPs](/intl.en-US/User Guide/Create NAT gateways.md) and [Configure DNAT to provide Internet-facing services](/intl.en-US/User Guide/Configure DNAT to provide Internet-facing services.md).

-   After you create DNAT entries for an ECS instance, you cannot associate an EIP with the ECS instance.

    Before you can associate an EIP with the ECS instance, you must delete the DNAT entries that you created for the ECS instance. After you delete the DNAT entries, you can associate an EIP with the ECS instance. For more information, see [Delete a NAT gateway](/intl.en-US/User Guide/Create NAT gateways.md) and [Associate EIPs](/intl.en-US/User Guide/Create NAT gateways.md).


**Note:** If DNAT entries are created for an ECS instance with which an EIP is associated, the ECS instance uses the EIP instead of DNAT to communicate with the Internet.

## Why am I unable to associate an EIP with an ECS instance?

Possible causes:

-   You can associate an EIP with only one ECS instance that is deployed in a VPC. If the ECS instance is not deployed in a VPC, you cannot associate an EIP with the ECS instance.
-   The EIP and ECS instance are deployed in different regions.
-   The ECS instance is in a state that does not allow you to associate an EIP with the ECS instance. You can associate an EIP with only an ECS instance that is in the Running or Stopped state.
-   The ECS instance is assigned a public IP address or another EIP is associated with the ECS instance.

## Why am I unable to view the EIP in the operating system of the ECS instance after I associate the EIP with the ECS instance?

EIPs are deployed on the Internet-facing gateway of Alibaba Cloud and are mapped to the private ENIs of the associated ECS instances through NAT. Therefore, you cannot view the EIP on the private ENI of the ECS instance.

When you associate an EIP with a secondary ENI, you can select the cut-through mode. In cut-through mode, the EIP replaces the private IP address of the secondary ENI. The secondary ENI functions as a public network interface controller \(NIC\) and the private network feature is no longer available. To view the EIP in the ENI information of the operating system, run the ifconfig or ipconfig command. For more information, see [Associate an EIP with a secondary ENI in cut-through mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate an EIP with a secondary ENI in cut-through mode.md).

## How can I associate multiple EIPs with one ECS instance?

You can associate multiple EIPs with one ECS instance by using the following methods:

-   You can associate multiple secondary ENIs with an ECS instance. Make sure that an EIP is associated with each secondary ENI. The number of secondary ENIs that can be associated with an ECS instance varies based on the specification of the ECS instance. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).
-   If you associate an EIP with a secondary ENI in **NAT Mode**, you can associate multiple EIPs with the secondary private IP address of the secondary ENI. Then, you can associate the secondary ENI with an ECS instance. For more information, see [Associate multiple EIPs with a secondary ENI in NAT mode](/intl.en-US/Best practices/Associate multiple EIPs with a secondary ENI in NAT mode.md).

## Why am I unable to access services over the Internet after I associate an EIP with an ECS instance or ENI?

If an application that requires access to the Internet is deployed in the ECS instance, you must modify the default route of the ECS instance or configure specific routes. By default, packets are transmitted from the primary ENI. You can modify route priorities to allow packets to access the Internet through the secondary ENI. You can also configure specific routes to forward packets to the Internet through multiple ENIs or a random ENI to implement load balancing.

## Can I use an EIP as the origin IP address for Web Application Firewall \(WAF\)?

Yes.

