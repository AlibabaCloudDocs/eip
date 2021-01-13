# Associate with and disassociate from a cloud resource

This topic provides answers to some commonly asked questions about associating an elastic IP address \(EIP\) with and disassociating an EIP from a cloud resource.

-   [What are the cloud resources with which I can associate EIPs?](#section_pap_ugo_jeh)
-   [Can I associate an EIP with multiple cloud resources?](#section_ote_h91_ws7)
-   [Can I associate an EIP with a cloud resource that is deployed in another region?](#section_uu3_mql_s9i)
-   [Can I associate an EIP with a cloud resource that is deployed in another zone?](#section_m0l_vvo_hts)
-   [How many EIPs can I associate with one cloud resource?](#section_n2w_txw_ezn)
-   [Can I associate an EIP with an SLB instance?](#section_n0f_o8t_tfe)
-   [Why am I unable to see the associated SLB instance in the EIP console?](#section_92e_zg7_cex)
-   [Why am I unable to associate an EIP with a NAT gateway?](#section_oml_rxp_5uc)
-   [If an ECS instance is associated with an EIP, can I use the DNAT feature of NAT Gateway to provide service to the Internet?](#section_wa9_tjs_eb2)
-   [Why am I unable to associate an EIP with an ECS instance?](#section_77i_2nv_smy)
-   [Why am I unable to view the EIP on the ENI of an ECS instance after I associate the EIP with the ECS instance?](#section_9y3_r2h_ran)
-   [How can I associate multiple EIPs with one ECS instance?](#section_c6w_x9a_b7m)
-   [Why am I unable to access services over the Internet after I associate an ECS instance or an ENI with an EIP?](#section_m3e_7x3_xo5)
-   [Can I associate an ECS instance with an IPv6 address?](#section_h91_8bh_fbx)
-   [Can I use an EIP as the origin IP address for Web Application Firewall \(WAF\)?](#section_qln_3p7_4ta)

## What are the cloud resources with which I can associate EIPs?

You can associate EIPs with Elastic Compute Service \(ECS\) instances, internal Server Load Balancer \(SLB\) instances, secondary elastic network interfaces \(ENIs\), NAT gateways, and high-availability virtual IP addresses \(HAVIPs\). The ECS instances, internal SLB instances, and secondary ENIs must be deployed in VPCs.

## Can I associate an EIP with multiple cloud resources?

No. You can associate an EIP with only one cloud resource.

## Can I associate an EIP with a cloud resource that is deployed in another region?

No.

The EIP and the cloud resource to be associated with must be deployed in the same region. For example, an EIP deployed in the China \(Beijing\) region cannot be associated with a cloud resource deployed in the China \(Hangzhou\) region.

## Can I associate an EIP with a cloud resource that is deployed in another zone?

Yes.

Zones do not apply to EIPs. If a cloud resource and an EIP are deployed in the same region, you can associate the EIP with the cloud resource.

## How many EIPs can I associate with one cloud resource?

-   NAT gateways

    You can associate at most 20 EIPs with a NAT gateway, among which at most 10 pay-by-data-transfer EIPs can be associated.

    You can go to the [Quota Management](https://vpc.console.aliyun.com/quota) page to increase the quota. For more information, see [Quota management](/intl.en-US/Common Configurations/Quota management.md).

-   HAVIPs

    Each HAVIP can be associated with only one EIP.

-   SLB instances

    Each internal SLB instance can be associated with only one EIP.


## Can I associate an EIP with an SLB instance?

You can associate an EIP with only an internal SLB instance instead of a public-facing SLB instance. Each internal SLB instance can be associated with only one EIP. You must associate an EIP with an internal SLB instance in the EIP console instead of the SLB console.

## Why am I unable to see the associated SLB instance in the EIP console?

Possible reasons are:

-   The resource group ID of the EIP is different from that of the SLB instance.
-   If you log on to the EIP console as a RAM user, switch to your Alibaba Cloud account.

## Why am I unable to associate an EIP with a NAT gateway?

If you purchased a NAT bandwidth plan before January 26, 2018, you must use the NAT bandwidth plan to provide Internet IP addresses to the NAT gateway. To associate an EIP with a NAT gateway, submit a ticket.

## If an ECS instance is associated with an EIP, can I use the DNAT feature of NAT Gateway to provide service to the Internet?

No.

The limits include:

-   If an ECS instance is associated with an EIP, you cannot use the Destination Network Address Translation \(DNAT\) feature of NAT Gateway to provide service to the Internet.

    Before you can use the DNAT feature, you must disassociate the EIP from the ECS instance. After you disassociate the EIP, you can add DNAT entries to the ECS instance. For more information, see [Disassociate an EIP from a NAT gateway](/intl.en-US/User Guide/Manage NAT gateways.md) and [Create a DNAT entry to provide Internet-facing services](/intl.en-US/User Guide/Create a DNAT entry to provide Internet-facing services.md).

-   If you have already added DNAT entries to an ECS instance, you cannot associate an EIP with the ECS instance.

    Before you can associate an EIP with the ECS instance, you must delete the DNAT entries. After you delete the DNAT entries, you can associate an EIP with the ECS instance. For more information, see [Delete a NAT gateway](/intl.en-US/User Guide/Manage NAT gateways.md) and [Associate an EIP with a NAT gateway](/intl.en-US/User Guide/Manage NAT gateways.md).


**Note:** If DNAT entries are added to an ECS instance that is associated with an EIP, the ECS instance preferably uses the EIP to communicate with the Internet.

## Why am I unable to associate an EIP with an ECS instance?

Possible reasons:

-   You can associate an EIP only with an ECS instance that is deployed in a VPC. If the ECS instance is not deployed in a VPC, you cannot associate an EIP with the ECS instance.
-   The region of the EIP is different from that of the ECS instance.
-   The state of the ECS instance does not support the association action. You can associate an EIP only with an ECS instance that is in the Running or Stopped state.
-   The ECS instance is already assigned a public IP address or associated with another EIP.

## Why am I unable to view the EIP on the ENI of an ECS instance after I associate the EIP with the ECS instance?

An EIP is configured on the Internet gateway and mapped to the private ENI of the ECS instance through NAT. Therefore, you cannot view the EIP on the private ENI of the ECS instance.

When you associate an EIP with a secondary ENI, you can select the cut-through mode or multi-EIP to ENI mode.

-   Cut-through mode

    In this mode, the EIP replaces the private IP address of the secondary ENI. The secondary ENI becomes a pure Internet network interface controller \(NIC\) and its private network feature is no longer available. You can view the EIP on the ENI of the operating system and run the ifconfig or ipconfig command to obtain the Internet IP address of the ENI. For more information, see [Associate an EIP with a secondary ENI in cut-through mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate an EIP with a secondary ENI in cut-through mode.md).

-   Multi-EIP to ENI mode

    In this mode, the private network feature of the secondary ENI is available. You can view the EIP on the ENI. After the operating system is configured with a static IP address, you can run the ifconfig or ipconfig command to obtain the public IP address of the ENI. For more information, see [Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode.md).


## How can I associate multiple EIPs with one ECS instance?

You can associate multiple EIPs with one ECS instance in the following ways:

-   Associate an EIP with a secondary ENI and associate the secondary ENI with an ECS instance. The number of secondary ENIs that can be associated with an ECS instance varies based on the specification of the ECS instance. For more information, see [Instance families](/intl.en-US/Instance/Instance families.md).
-   If you associate an EIP with a secondary ENI in **NAT Mode**, you can associate multiple EIPs with the secondary private IP address of the secondary ENI. Then, you can associate the secondary ENI with an ECS instance. For more information, see [Associate multiple EIPs with a secondary ENI in NAT mode](/intl.en-US/Best practices/Associate multiple EIPs with a secondary ENI in NAT mode.md).
-   If you associate an EIP with a secondary ENI in **Multi-EIP to ENI Mode**, you can associate multiple EIPs with the secondary ENI. Then, you can associate the secondary ENI with an ECS instance. For more information, see [Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode](/intl.en-US/User Guide/Associate an EIP with a cloud instance/Bind an EIP to a secondary ENI/Associate EIPs with secondary ENIs in multi-EIP-to-ENI mode.md).

## Why am I unable to access services over the Internet after I associate an ECS instance or an ENI with an EIP?

If an application that requires access to the Internet is deployed in the ECS instance, you must modify the default route of the ECS instance or configure specific routes. By default, packets are transmitted from the primary ENI. You can adjust route priorities to allow packets to access the Internet through the secondary ENI. You can also configure specific routes to forward packets to the Internet through multiple ENIs or a randomly selected ENI to implement load balancing.

## Can I associate an ECS instance with an IPv6 address?

Yes.

-   Windows: For more information, see [Use IPv6 addresses of Windows instances]().
-   Linux: For more information, see [Use IPv6 addresses of Linux instances]().

## Can I use an EIP as the origin IP address for Web Application Firewall \(WAF\)?

Yes.

