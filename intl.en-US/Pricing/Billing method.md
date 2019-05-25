# Billing method {#concept_rcd_sgl_vdb .concept}

Elastic IP Addresses \(EIPs\) are billed based on the traffic usage and with the Pay-As-You-Go method. Each EIP is billed independently.

## Billing method {#section_tdb_dhl_vdb .section}

EIPs are billed and charged on an hourly basis.

Total cost of an EIP = EIP retention fee + traffic fee.

-   Retention fee = price × retention time. Each EIP is charged independently.

    The time less than an hour is calculated as an hour.

    **Note:** No EIP retention fee is incurred when the EIP is associated with an ECS instance in a VPC. However, for SLB instances and NAT Gateways, the retention fee is still collected.

-   Traffic fee = price × charged traffic. Each EIP is charged independently.

    The cumulative outbound traffic of the EIP in an hour is charged. Outbound traffic refers to data transmitted from the Alibaba Cloud data center to the Internet, and the reverse is inbound traffic.

    **Note:** Modifying the peak bandwidth does not affect the cost. However, we recommend that you set the bandwidth based on your actual needs to avoid generating excessive charged traffic due to malicious access.


## Pricing {#section_czs_whl_vdb .section}

If the price on the purchase page is different from the price listed in the table, take the price on the purchase page as the standard.

|Region|Traffic fee \(USD/GB\)|Retention fee \(USD/hour\)|
|:-----|:---------------------|:-------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Shenzhen\)|0.123|0.0031|
|Hong Kong|0.153|0.0088|
|Singapore|0.081|0.0063|
|Japan \(Tokyo\)|0.087|0.005|
|US \(Virginia\)|0.076|0.0047|
|US \(Silicon Valley\)|0.077|0.0047|
|Germany \(Frankfurt\)|0.07|0.006|
|UAE \(Dubai\)|0.447|0.009|
|Australia \(Sydney\)|0.096|0.006|

## Example {#section_ygt_x3l_vdb .section}

In this example, the following EIP is used:

-   Assume that you created an EIP in the China \(Hangzhou\) region at 9:30 of one day and set the peak bandwidth to 10 Mbit/s.
-   Then you immediately associated this EIP with an ECS instance and used the EIP to access the service deployed on the EC instance.
-   You changed the EIP bandwidth twice that day:
    -   At 17:00, the bandwidth was changed from 10 Mbit/s to 20 Mbit/s.
    -   At 23:00, the bandwidth was changed from 20 Mbit/s to 15 Mbit/s.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12818/15587481926215_en-US.png)

The total cost of this EIP on that day is USD 7.5.

-   EIP retention fee:

    Because the EIP is associated with an ECS instance of the VPC network, no EIP retention fee is charged.

-   Traffic fee:
    -   The total traffic consumed by the EIP that day is 60 GB.
    -   The traffic fee in the China \(Hangzhou\) region is USD 0.125 per GB.
    -   Then, the total traffic fee is 0.125 x 60 = USD 7.5.

