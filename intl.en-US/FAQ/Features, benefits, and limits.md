# Features, benefits, and limits

This topic provides answers to some frequently asked questions about the features, benefits, and limits of elastic IP addresses \(EIPs\).

-   [What is an EIP?](#section_ml9_wcl_5n2)
-   [What are the benefits of EIPs?](#section_0n3_4vh_26p)
-   [What are the differences between an EIP and a static public IP address of an ECS instance?](#section_r2s_8pz_7kw)
-   [How many EIPs can I apply for with an Alibaba Cloud account?](#section_nco_5ln_zv6)
-   [Is the number of times that I can call the EIP API limited?](#section_182_8za_tum)
-   [Can I resolve the domain name of a website to an EIP?](#section_7un_t6d_cht)

## What is an EIP?

An EIP is a public IP address that you can purchase and use as an independent resource. You can associate EIPs with Elastic Compute Service \(ECS\) instances, internal-facing Server Load Balancer \(SLB\) instances, secondary elastic network interfaces \(ENIs\), NAT gateways, and high-availability virtual IP addresses \(HAVIPs\). The ECS instances, internal-facing SLB instances, and secondary ENIs must be deployed in virtual private clouds \(VPCs\).

EIPs are NAT IP addresses deployed on the Internet-facing gateway of Alibaba Cloud, and are mapped to the associated cloud resources through NAT. After EIPs are associated with cloud resources, the cloud resources can use the EIPs to communicate with the Internet.

## What are the benefits of EIPs?

EIPs have the following benefits:

-   Purchase and use as independent resources

    You can purchase and use an EIP as an independent resource. EIPs are not bundled with other computing or storage resources.

-   Associate with resources at any time

    You can associate EIPs with resources at any time. You can also disassociate EIPs from resources and release the EIPs that you no longer need. This prevents unexpected charges.

-   Modify bandwidth limits on demand

    You can modify the bandwidth limit of an EIP at any time based on your business requirements. The modification immediately takes effect.


## What are the differences between an EIP and a static public IP address of an ECS instance?

The following table describes the differences between an EIP and a static public IP address of an ECS instance.

|Feature|EIP|Static public IP address|
|:------|:--|:-----------------------|
|Supported network|VPC|VPC and classic network|
|Used as an independent resource|Supported|Not supported|
|Associated with and disassociated from an ECS instance at any time|Supported|Not supported|
|Displayed in the ENI information of the operating system of the associated ECS instance|**Cut-through mode**: Displayed|Classic network: Displayed

VPC: Not displayed |

## How many EIPs can I apply for with an Alibaba Cloud account?

You can apply for at most 20 EIPs with an Alibaba Cloud account. To apply for more EIPs, request a quota increase. For more information, see [Manage quotas](/intl.en-US/User Guide/Manage quotas.md).

## Is the number of times that I can call the EIP API limited?

Yes. You can call the EIP API at most 500 times within one day. Subsequent API calls that are sent within the day are denied.

## Can I resolve the domain name of a website to an EIP?

Yes. You can create a DNS record to resolve a domain name to an EIP or a private IP address. For more information, see [Create a DNS record for a website](https://www.alibabacloud.com/help/zh/doc-detail/106535.htm).

