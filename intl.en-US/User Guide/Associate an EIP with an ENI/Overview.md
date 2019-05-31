# Overview {#concept_y1m_k2j_y2b .concept}

You can associate an Elastic IP Address \(EIP\) with an Elastic Network Interface \(ENI\). In this way, you can build a more robust, flexible, and scalable IT solution and allow a single server to use multiple public IP addresses.

An ENI has a private IP address. After an ENI is associated with an EIP, the ENI has both a private IP address and a public IP address. When you move an ENI that is associated with an EIP from an ECS instance to another ECS instance, the public IP address and private IP address are also migrated.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18789/155928248610409_en-US.png)

You can also associate multiple ENIs with an ECS instance and associate an EIP with each ENI so that the ECS instance has multiple public IP addresses. You can use these public IP addresses to provide external services with corresponding security group rules.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18789/155928248610410_en-US.png)

## Association modes {#section_925_9hi_qqa .section}

You can associate an EIP with an ENI in the following three modes:

-   NAT mode
-   Cut-through mode
-   Multi-EIP to ENI mode

**Note:** Currently, the multi-EIP to ENI mode is supported only in the China \(Beijing\), China \(Zhangjiakou\), Singapore, Germany \(Frankfurt\), and India \(Mumbai\) regions.

The following table lists the differences among these three modes.

|Item|NAT mode|Cut-through mode|Multi-EIP to ENI mode|
|----|--------|----------------|---------------------|
|Can the EIP be read on the ENI of the operating system?|No|Yes **Note:** You can run the ifconfig or ipconfig command to obtain the EIP address of the ENI.

 |Yes **Note:** After the operating system is configured with a static IP address, you can run the ifconfig or ipconfig command to obtain the public IP address of the ENI.

 |
|What types of ENIs can be associated with EIPs?|Primary ENIs and secondary ENIs|Secondary ENIs|Secondary ENIs|
|The number of EIPs that a primary ENI can be associated with.|1|Not supported|Not supported|
|The number of EIPs that a secondary ENI can be associated with.|Depends on the number of private IP addresses of the secondary ENI. **Note:** EIPs are mapped to the private IP addresses of a secondary ENI. For example, if a secondary ENI has 10 private IP addresses, a maximum of 10 EIPs can be associated with the secondary ENI.

 |1 **Note:** In the cut-through mode, an EIP can only be associated with the primary private IP address of the secondary ENI.

 |10 **Note:** If you need to associate more EIPs, open a ticket to apply for an increase to the quota.

 |
|Is the private IP address of the secondary ENI available after the ENI is associated with an EIP?|Yes|No|Yes|
|Supported protocols|When an EIP is deployed as a NAT ALG \(NAT application layer gateway\), protocols such as H.323, SIP, DNS, and RTSP are not supported.|All IP protocols such as FTP, H.323, SIP, DNS, RTSP, and TFTP.|All IP protocols such as FTP, H.323, SIP, DNS, RTSP, and TFTP.|

## FAQ {#section_ubl_jkj_y2b .section}

**Is the EIP instance fee charged after an EIP is associated with an ENI?**

Yes.

The EIP instance fee is not charged only when the EIP is associated with an ECS instance.

**Are additional configurations required after an EIP is associated with an ENI that is attached to an ECS instance?** 

-   If an application that provides external services is deployed on the ECS instance, such as a website, you do not need to configure additional routing in the ECS instance or in the VPC. You can directly use the EIP associated with the ENI to provide external service.
-   If an application that requires Internet access is deployed on the ECS instance, you must customize the default route or add new routes. The default route sends packets from the primary NIC. You can adjust the route priority to allow packets to be sent out through the ENI. You can also configure more routes to distribute packets from multiple NICs to balance the loads or randomly distribute the packets from one NIC.

