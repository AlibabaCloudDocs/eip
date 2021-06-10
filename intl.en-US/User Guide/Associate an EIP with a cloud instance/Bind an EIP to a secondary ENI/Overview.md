# Overview

You can associate elastic IP addresses \(EIPs\) with elastic network interfaces \(ENIs\). You can associate EIPs with ENIs and associate the ENIs with an Elastic Compute Service \(ECS\) instance. This way, the ECS instance can use multiple EIPs. You can use EIPs to improve the service availability, flexibility, and scalability.

Each ENI is assigned a private IP address. After you associate an EIP with an ENI, both the private IP address and the EIP are available for the ENI. You can change the private IP address and public IP address of an ECS instance by replacing the secondary ENI that is associated with the ECS instance. When you replace the secondary ENI of an ECS instance, the reliability and availability of your service are not affected.

![Associate ENIs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1006401261/p10409.png)

You can associate multiple ENIs with an ECS instance. Make sure that an EIP is associated with each ENI. This way, the ECS instance can use multiple EIPs. The ECS instance can use the EIPs to provide Internet-facing services. You can configure security group rules for the ECS instance to control access from the Internet.

![Associate multiple ENIs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1006401261/p10410.png)

## Association modes

You can associate an EIP with an ENI in one of the following two modes:

-   NAT mode
-   Cut-through mode

**Note:** The cut-through mode is supported in the following regions: China \(Hangzhou\), China \(Shanghai\), China \(Qingdao\), China \(Beijing\), China \(Zhangjiakou\), China \(Hohhot\), China \(Shenzhen\), China \(Chengdu\), Singapore \(Singapore\), Indonesia \(Jakarta\), Germany \(Frankfurt\), UK \(London\), and US \(Virginia\).

The following table describes the differences between these modes.

|Item|NAT mode|Cut-through mode|
|----|--------|----------------|
|Whether the EIP is displayed in the ENI information of the operating system|No|Yes **Note:** You can run the ifconfig or ipconfig command to query the public IP address of the ENI. |
|Types of ENIs that can be associated with EIPs|Primary and secondary ENIs|Secondary ENIs|
|Number of EIPs that can be associated with a primary ENI|1|N/A|
|Number of EIPs that can be associated with a secondary ENI|Depends on the number of private IP addresses of the secondary ENI**Note:** Each EIP is mapped to a private IP address of a secondary ENI. If a secondary ENI is assigned 10 private IP addresses, you can associate at most 10 EIPs with the secondary ENI.

|1**Note:** You can associate an EIP with only the primary private IP address of a secondary ENI in cut-through mode. |
|Whether private network features of a secondary ENI are available after an EIP is associated with the secondary ENI|Yes|No|
|Supported protocols|EIPs deployed as NAT application layer gateways \(ALGs\) do not support protocols such as H.323, Session Initiation Protocol \(SIP\), Domain Name System \(DNS\), Real Time Streaming Protocol \(RTSP\), and Trivial File Transfer Protocol \(TFTP\).|EIPs support all IP protocols, including FTP, H.323, SIP, DNS, RTSP, and TFTP.|

## FAQ

**Am I charged an instance fee for an EIP after I associate the EIP with a secondary ENI?**

Yes.

You are not charged an instance fee for an EIP only when you associate the EIP with an ECS instance. You are charged instance fees if you associate EIPs with other types of resources.

**Do I need to configure an ECS instance after I attach an ENI that is associated with an EIP to an ECS instance?**

-   If you want the ECS instance to provide Internet-facing services, such as web services, you do not need to configure routes for the ECS instance or the virtual private cloud \(VPC\) where the ECS instance is deployed. The ECS instance uses the EIP to provide services.
-   If you want the ECS instance to access the Internet, you must configure the default route of the ECS instance or create specific routes for the ECS instance. By default, packets are transmitted from the primary ENI. You can modify route priorities to allow packets to access the Internet through the secondary ENI. You can also create specific routes to forward packets to the Internet through multiple ENIs or a random ENI to implement load balancing.

