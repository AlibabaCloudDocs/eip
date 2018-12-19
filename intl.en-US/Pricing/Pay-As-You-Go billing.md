# Pay-As-You-Go billing {#concept_rcd_sgl_vdb .concept}

Elastic IP Address \(EIP\) supports the Pay-As-You-Go billing method.

## Billing overview {#section_tdb_dhl_vdb .section}

An EIP is charged based on the traffic usage. Both the charging and billing cycles are hourly.

Total cost of an EIP = EIP retention fee + traffic fee.

-   Retention fee = price x retention time. Each EIP is charged independently.

    Partial hours are billed as full hours.

    **Note:** The EIP retention fee is free of charge when the EIP is bound to an ECS instance in a VPC. However, for SLB instances and NAT Gateways, the retention fee is still collected.

-   Traffic fee = price x charged traffic. Each EIP is charged independently.

    The cumulative outbound traffic of the EIP in an hour is charged. Outbound traffic refers to data transmitted from the Alibaba Cloud data center to the Internet, and the reverse is inbound traffic.

    **Note:** Modifying the bandwidth does not affect the cost. Even so, we recommend that you set the bandwidth based on your actual needs to avoid generating excessive charged traffic due to malicious access.


## Pricing {#section_czs_whl_vdb .section}

If the price on the purchase page is different from the price listed in the table, take the price on the [purchase page](https://common-buy.aliyun.com/eip/postpay?spm=5176.11182188.0.0.1ff84882ER5p1s#/buy?request=%7B%22eip_region_no%22:%22cn-huhehaote-nt12-a01%22%7D) as the standard.

|Regions|Traffic Fee \(USD/GB\)|Retention Fee \(USD/Hour\)|
|:------|:---------------------|:-------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Shenzhen\)|0.123|0.0031|
|Hong Kong|0.153|0.0088|
|Singapore|0.081|0.0063|
|Japan \(Tokyo\)|0.12|0.0047|
|US \(Virginia\)|0.076|0.0047|
|US \(Silicon Valley\)|0.077|0.0047|
|Germany \(Frankfurt\)|0.07|0.006|
|UAE \(Dubai\)|0.447|0.009|

## Billing example {#section_ygt_x3l_vdb .section}

The EIP usage in this example is as follows:

-   Assume that you purchased an EIP in the China \(Hangzhou\) region at 9:30 and set the bandwidth to 10 Mbps.
-   Then you immediately bound this EIP to an ECS instance and used the EIP to access the service deployed on the EC instance.
-   You changed the EIP bandwidth twice that day:
    -   At 17:00, the bandwidth was changed from 10 Mbps to 20 Mbps.
    -   At 23:00, the bandwidth was changed from 20 Mbps to 15 Mbps.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12818/15452151056215_en-US.png)

The total cost of this EIP on that day is USD 7.5.

-   EIP retention fee:

    Because the EIP is bound to an ECS instance of the VPC network, no EIP retention fee is charged.

-   Traffic fee:
    -   The total traffic consumed by the EIP that day is 60 GB.
    -   The traffic fee in the China \(Hangzhou\) region is USD 0.125 per GB.
    -   The total traffic fee is 0.125 x 60 = USD 7.5. 

