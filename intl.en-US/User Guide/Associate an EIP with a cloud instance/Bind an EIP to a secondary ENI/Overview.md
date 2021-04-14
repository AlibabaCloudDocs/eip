# Overview

You can associate elastic IP addresses \(EIPs\) with elastic network interfaces \(ENIs\). You can build a more stable, flexible, and scalable service with servers that use EIPs. Each server can be associated with multiple EIPs. This way, each server is assigned multiple public IP addresses.

Each ENI is assigned a private IP address. After you associate an EIP with an ENI, the ENI is capable of sending and receiving network traffic through both a private IP address and a public IP address. Alibaba Cloud provides a solution for migrating EIPs between two Elastic Compute Service \(ECS\) instances without affecting the reliability and availability of your workloads. If you migrate an ENI that is associated with an EIP from an ECS instance to another ECS instance, both the private and public IP addresses of the ENI are migrated.

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0776838161/p10409.png)

You can associate an ECS instance with multiple ENIs. You can associate each ENI with an EIP. This way, the ECS instance has multiple public IP addresses. You can also use EIPs with security groups to control external access.

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0776838161/p10410.png)

## Association modes

You can associate an ENI with an EIP in the following modes:

-   NAT mode
-   Cut-through mode
-   Multi-EIP-to-ENI mode

**Note:**

-   The cut-through mode is supported in the following regions: China \(Hangzhou\), China \(Shanghai\), China Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Hohhot\), China \(Shenzhen\), China \(Chengdu\), Singapore \(Singapore\), Indonesia \(Jakarta\), Germany \(Frankfurt\), UK \(London\), and US \(Virginia\).
-   The multi-EIP-to-ENI mode is available to only users who have used this mode in public preview. The multi-EIP-to-ENI mode is supported in the following regions: China \(Shenzhen\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Chengdu\), Singapore, Germany \(Frankfurt\), India \(Mumbai\), US \(Virginia\), and UK \(London\).

The following table lists the differences among these modes.

|Item|NAT mode|Cut-through mode|Multi-EIP-to-ENI mode|
|----|--------|----------------|---------------------|
|Whether the EIP is displayed on the ENI in the operating system|No|Yes **Note:** You can run the ifconfig or ipconfig command to query the public IP address of the ENI.

|Yes**Note:** After you configure a static IP address in the operating system, you can run the ifconfig or ipconfig command to query the public IP address of the ENI. |
|Types of ENIs that can be associated with EIPs|Primary and secondary ENIs.|Secondary ENIs.|Secondary ENIs.|
|The maximum number of EIPs that can be associated with a primary ENI|1|EIPs cannot be associated with primary ENIs.|EIPs cannot be associated with primary ENIs.|
|The maximum number of EIPs that can be associated with a secondary ENI|Based on the number of private IP addresses of the secondary ENI.**Note:** Each EIP is mapped to a private IP address of a secondary ENI. If a secondary ENI is assigned 10 private IP addresses, a maximum of 10 EIPs can be associated with the secondary ENI.

|1**Note:** In cut-through mode, an EIP can be mapped to only the primary private IP address of a secondary ENI.

|10**Note:** To request a quota increase, submit a ticket. |
|Whether the secondary ENI supports private networks after an EIP is associated with a secondary ENI|Yes|No|Yes|
|Supported protocols|When an EIP is deployed as a NAT application layer gateway \(ALG\), the following protocols are not supported: H.323, SIP, DNS, and RTSP.|EIPs in cut-through mode support all IP protocols, such as FTP, H.323, SIP, DNS, RTSP, and TFTP.|EIPs in cut-through mode support all IP protocols, such as FTP, H.323, SIP, DNS, RTSP, and TFTP.|

## FAQ

**Does Alibaba Cloud charge EIPs that are associated with ENIs?**

Yes.

Only EIPs that are associated with ECS instances are free of charge. EIPs that are associated with other resources are charged.

**Are additional configurations required after I attach an ENI that is associated with an EIP to an ECS instance?**

-   If the ECS instance is deployed to provide external services, such as web services, you do not need to configure routes for the ECS instance or the VPC where the ECS instance is deployed. The ECS instance can provide services through the EIP.
-   If the ECS instance is deployed to access services on the Internet, you must modify the default route of the ECS instance or configure specific routes. The default route specifies that packets are forwarded to the Internet through the primary NIC of the ECS instance. You must adjust the priority of the routes before packets can be forwarded to the Internet through the ENI that is associated with the EIP. You can also configure specific routes to forward packets to the Internet through multiple ENIs or a randomly selected ENI to implement load balancing.

