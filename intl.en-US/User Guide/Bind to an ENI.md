# Bind to an ENI {#concept_y1m_k2j_y2b .concept}

You can bind an EIP to an Elastic Network Interface \(ENI\). Binding an EIP to an ENI allows you to build a more robust, flexible and scalable IT solution and enable a single server to use multiple public IPs.

## ENI overview {#section_bn1_r2j_y2b .section}

Elastic Network Interface \(ENI\) is an independent network interface instance. You can attach an ENI to an ECS instance, or detach the ENI from the ECS instance and then attach it to another ECS instance. After you move an ENI from one instance to another one, the network traffic is also directed to the new instance.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18789/153567848410404_en-US.png)

Besides, you can attach multiple ENIs to the same ECS instance, so that the instance can use multiple public IPs to provide external services.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18789/153567848410407_en-US.png)

## Scenarios {#section_nnr_ngj_y2b .section}

Binding EIP to ENI is applicable to the following scenarios:

-   Highly reliable IP migration

    ENI provides a private IP itself. After an ENI is bound with an EIP, the ENI has both a private IP and a public IP. When moving an ENI bound with an EIP from an ECS instance to another instance, the public IP and private IP are also migrated. It provides a highly reliable and available IP migration solution for cloud servers that use both public IP and private IP.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18789/153567848410409_en-US.png)

-   Use multiple pubic IPs to provide services

    You can bind multiple ENIs to an ECS instance and bind an EIP to each ENI, thus the ECS instance has multiple public IPs. You can flexibly use these public IPs to provide external services with corresponding security group rules.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/18789/153567848410410_en-US.png)


## FAQ {#section_ubl_jkj_y2b .section}

**Is the EIP instance fee charged after an EIP is bound to an ENI?**

Yes.

An EIP is free from instance fee only when it is bound to an ECS instance.

**How many EIPs can an ENI bind to?**

One.

**Is additional configuration required after an EIP is bound to an ENI that is attached to an ECS instance?**

-   If an application that provides external services is deployed on the ECS instance, such as a website, you do not need to configure additional routing in the ECS instance or in the VPC. You can directly use the EIP bound to the ENI to provide external service.
-   If an application that requires the Internet access is deployed on the ECS instance, you must customize the default routing or add a new route. The default route is sent from the primary NIC. You can adjust the route priority to allow packets to be sent out through ENI. You can also configure a route to distribute packets from multiple NICs in a load-sharing way or randomly distribute them from a NIC.

## Bind an ENI {#section_h2d_zlj_y2b .section}

To bind an ENI, complete these steps:

1.  Log on to the [VPC console](https://vpcnext.console.aliyun.com).
2.  In the left-side navigation pane, click **Elastic IP Addresses**.
3.  On the Elastic IP Addresses page, select the region of the target EIP.
4.  Locate the target EIP, and then click **Bind**.
5.  On the Bind Elastic IP Address page, select the region of the ENI to bind and the ENI instance, and then click **OK**.

