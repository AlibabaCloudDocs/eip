# Pay-As-You-Go {#concept_rcd_sgl_vdb .concept}

 Elastic IP Addresses \(EIPs\) are charged with the traffic-based billing method of Pay-As-You-Go. This topic describes the billing method of EIPs. 

## Billing items {#section_tdb_dhl_vdb .section}

The total fees of an EIP include an instance fee and a traffic fee. EIPs are billed and charged on an hourly basis. Billing periods less than an hour are calculated as an hour.

The instance fee and traffic fee are calculated as follows:

-   Instance fee = unit price \(USD/hour\) × usage period

    The usage period refers to the period between the time when the EIP is created and the time when the EIP is released.

-   Traffic fee = unit price \(USD/GB\) × charged traffic

    The charged traffic refers to the cumulative outbound traffic of the EIP to be billed in an hour.


**Note:** Modifying the peak bandwidth does not affect the unit price. However, we recommend that you set the bandwidth based on your actual needs to avoid generating excessive charged traffic due to malicious access.

## Pricing {#section_czs_whl_vdb .section}

The following table lists the unit prices of the instance fee and the traffic fee.

**Note:** If the price on the purchase page is different from the price listed in the following table, take the price on the [purchase page](https://common-buy.aliyun.com/?spm=5176.8050872.0.0.2a9c737e2bEyW1&commodityCode=eip_pre#/buy) as the standard.

|Region|Instance fee \(USD/hour\)|Traffic fee \(USD/GB\)|
|:-----|-------------------------|:---------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou\), China \(Shenzhen\), China \(Hohhot\)|0.003|0.123|
|China \(Qingdao\)|0.003|0.11|
|Hong Kong|0.009|0.153|
|Singapore|0.006|0.081|
|Japan \(Tokyo\)|0.005|0.087|
|USA \(Virginia\)|0.005|0.076|
|US \(Silicon Valley\)|0.005|0.077|
|Germany \(Frankfurt\), UK \(London\)|0.006|0.070|
|UAE \(Dubai\)|0.009|0.447|
|Australia \(Sydney\)|0.006|0.096|
|Malaysia \(Kuala Lumpur\)|0.003|0.077|
|Indonesia \(Jakarta\), India \(Mumbai\)|0.006|0.090|

## Example {#section_ygt_x3l_vdb .section}

In this example, the following EIP is used:

-   Assume that you created an EIP in the China \(Hangzhou\) region at 9:30 of one day and set the peak bandwidth to 10 Mbit/s.
-   Then you immediately associated this EIP with an ECS instance and used the EIP to access the service deployed on the EC instance.
-   Assume that you changed the EIP bandwidth twice that day:
    -   At 17:00, you changed the bandwidth from 10 Mbit/s to 20 Mbit/s.
    -   At 23:00, you changed the bandwidth from 20 Mbit/s to 15 Mbit/s.

 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/12818/15615380466215_en-US.png) 

For the preceding example, the total cost of this EIP for the day you created it is USD 7.5.

-   Instance fee:

    No EIP instance fee is charged. This is because the EIP is associated with an ECS instance of the VPC network.

-   Traffic fee:
    -   The total traffic consumed by the EIP that day is 60 GB.
    -   The unit price of the traffic fee in the China \(Hangzhou\) region is USD 0.125 per GB.
    -   The traffic fee is calculated through the following formula: 0.125 USD/GB × 60 GB = USD 7.5.

