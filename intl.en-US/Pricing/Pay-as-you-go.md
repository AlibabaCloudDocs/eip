---
keyword: [elastic IP address, billing method, pay-as-you-go]
---

# Pay-as-you-go

Elastic IP addresses \(EIPs\) support the pay-as-you-go billing method. Pay-as-you-go EIPs support the pay-by-data-transfer and pay-by-bandwidth metering methods.

## Overview

When you use a pay-as-you-go EIP, you must pay for the resources that you use. Pay-as-you-go EIPs are billed based on the following rules:

-   You can release a pay-as-you-go EIP at any time. After an EIP is released, the bill of the current hour or day is generated the next hour or day, and then fees are deducted from your account balance.
-   When you associate an EIP with an Elastic Compute Service \(ECS\) instance that is deployed in a VPC, you are not charged a configuration fee for the EIP. However, you are charged a configuration fee when you associate an EIP with a NAT gateway, Server Load Balancer \(SLB\) instance, secondary elastic network interface \(ENI\), or high-availability virtual IP address \(HAVIP\).

Pay-as-you-go EIPs are billed based on data transfer or bandwidth. The peak bandwidth varies based on the metering method of an EIP. The following table describes the differences.

|Item|Pay-by-data-transfer EIP|Pay-by-bandwidth EIP|
|----|------------------------|--------------------|
|Bandwidth guarantee|The bandwidth limit of an EIP indicates the upper limit of bandwidth and is only for reference. The peak bandwidth is not guaranteed. In scenarios where demands exceed resource supplies, the peak bandwidth may be lower than the specified bandwidth limit value.|The bandwidth limit is a guaranteed value. In scenarios where demands exceed resource supplies, the peak bandwidth is guaranteed.|
|Maximum bandwidth limit|For each Alibaba Cloud account, the sum of the peak bandwidth of all pay-by-data-transfer EIPs in a region cannot exceed 5 Gbit/s. If your business requires guaranteed bandwidth or larger bandwidth, you must purchase pay-by-bandwidth EIPs.|For each Alibaba Cloud account, the sum of the bandwidth limits of all pay-by-bandwidth EIPs in each region cannot exceed 50 Gbit/s. You can contact the product manager from Alibaba Cloud to increase the quota.|

## Pay-by-data-transfer

Total fees of a pay-by-data-transfer EIP = Configuration fee + Data transfer fee. The billing cycle is one hour. Fees are calculated and bills are generated on an hourly basis. If you use an EIP for less than 1 hour, you are charged for one hour.

The configuration fee and data transfer fee are calculated by using the following formula:

-   Configuration fee = Instance unit price \(USD/hour\) × Usage duration \(hours\)

    The usage duration refers to the time period from when an EIP is created to when it is released.

-   Data transfer fee = Unit price of data transfer \(USD/GB\) × Amount of data transfer \(GB\)

    The amount of data transfer refers to the cumulative outbound traffic of an EIP. You are not charged for inbound traffic. Outbound traffic refers to the traffic that is transmitted from Alibaba Cloud to the Internet.


**Note:** After you change the bandwidth limit of an EIP, the unit price of the EIP and unit price of data transfer remain unchanged. We recommend that you set the bandwidth limit based on your business requirements to prevent unexpected data transfer charges caused by malicious requests or program errors.

EIPs support BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. If you use EIPs of different line types, you are charged at different instance unit prices and different data transfer unit prices.

**Note:** If the information about the regions and prices in the following table is different from that on the buy page in the console,the information on the [buy page](https://common-buy-intl.alibabacloud.com/eip/postpay) shall prevail.

|Region|Instance unit price \(USD/hour\)|Data transfer unit price \(USD/GB\)|
|:-----|--------------------------------|:----------------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou\), China \(Hohhot\), China \(Shenzhen\), China \(Heyuan\), and China \(Chengdu\)|0.0031|0.125|
|China \(Qingdao\)|0.0031|0.113|
|China \(Hong Kong\)|0.0088|0.156|
|Singapore \(Singapore\)|0.0063|0.117|
|Japan \(Tokyo\)|0.0047|0.120|
|US \(Virginia\)|0.0047|0.078|
|US \(Silicon Valley\)|0.0047|0.078|
|Germany \(Frankfurt\) and UK \(London\)|0.006|0.070|
|UAE \(Dubai\)|0.009|0.153|
|Australia \(Sydney\)|0.006|0.130|
|Malaysia \(Kuala Lumpur\)|0.003|0.125|
|Indonesia \(Jakarta\) and India \(Mumbai\)|0.006|0.117|

|Region|Instance unit price \(USD/hour\)|Data transfer unit price \(USD/GB\)|
|------|--------------------------------|-----------------------------------|
|China \(Hong Kong\)|0.0088|0.452|

## Pay-by-bandwidth

Total fees of a pay-by-bandwidth EIP = Configuration fee + Bandwidth fee. The configuration fee and bandwidth fee are billed on an hourly basis. If you use an EIP for less than 1 hour, you are charged for 1 hour. The billing cycle is one day. Fees are calculated and bills are generated on a daily basis.

The configuration fee and bandwidth fee are calculated by using the following formula:

-   Configuration fee = Instance unit price \(USD/day\) × \[Usage duration \(hours\)/24\] \(days\)

    The usage duration refers to the time period from when an EIP is created to when it is released.

-   Bandwidth fees

    -   1 Mbit/s ≤ Bandwidth limit ≤ 5 Mbit/s: Bandwidth fee = Unit price of bandwidth limit from 1 to 5 Mbit/s \(USD/day for every Mbit/s\) × \[Usage duration \(hours\)/24\] \(days\) × Bandwidth limit
    -   Bandwidth limit \> 5 Mbit/s: Bandwidth fee = Unit price of bandwidth limit from 1 to 5 Mbit/s \(USD/day for every Mbit/s\) × \[Usage duration \(hours\)/24\] \(days\) × 5 + Unit price of bandwidth limit higher than 5 Mbit/s \(USD/day for every Mbit/s\) × \[Usage duration \(hours\)/24\] \(days\) × \(n-5\).

        In the preceding formula, n represents the bandwidth limit value.

    The bandwidth fee is calculated based on a tiered pricing model with 5 Mbit/s as the standard bandwidth value.

    You can modify the bandwidth limit of an EIP at any time. If you change the bandwidth limit of an EIP, the bandwidth fee for the day is calculated based on the highest bandwidth limit value on that day.


EIPs support BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. If you use EIPs of different line types, you are charged at different instance unit prices and different bandwidth unit prices.

**Note:** If the information about the regions and prices in the following table is different from that on the buy page in the console,the information on the [buy page](https://common-buy-intl.alibabacloud.com/eip/postpay) shall prevail.

|Region|Instance unit price \(USD/day\)|
|:-----|-------------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou\), China \(Hohhot\), China \(Shenzhen\), China \(Heyuan\), China \(Chengdu\), and China \(Qingdao\)|0.0744|
|China \(Hong Kong\)|0.2112|
|Singapore \(Singapore\)|0.1512|
|Japan \(Tokyo\), US \(Virginia\), and US \(Silicon Valley\)|0.1128|
|Germany \(Frankfurt\), UK \(London\), Australia \(Sydney\), and Indonesia \(Jakarta\)|0.144|
|Malaysia \(Kuala Lumpur\)|0.072|

|Region|Bandwidth unit price \(USD/day\)|
|1 Mbps|2 Mbps|3 Mbps|4 Mbps|5 Mbps|6 Mbit/s and higher \(n represents the bandwidth limit value\)|
|------|:-------------------------------|
|------|:-----|:-----|:-----|:-----|:-------------------------------------------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou\), China \(Hohhot\), China \(Shenzhen\), China \(Heiyuan\), China \(Chengdu\), Malaysia \(Kuala Lumpur\), China \(Hong Kong\), Singapore \(Singapore\), Indonesia \(Jakarta\), US \(Virginia\), US \(Silicon Valley\), Germany \(Frankfurt\), UK \(London\), and Australia \(Sydney\)|0.14|0.28|0.43|0.57|0.71|0.71+\(n-5\)× 0.5|
|China \(Qingdao\)|0.11|0.21|0.32|0.43|0.53|0.53+\(n-5\)× 0.46|
|Japan \(Tokyo\)|0.17|0.34|0.51|0.68|0.85|0.85+\(n-5\)× 0.57|

|Region|Instance unit price \(USD/day\)|Bandwidth unit price \(USD/day\)|
|------|-------------------------------|--------------------------------|
|China \(Hong Kong\)|0.2112|1.430|

## Example

For example, you create an EIP in the China \(Hangzhou\) region at 09:30 \(UTC+8\) and set the bandwidth limit to 10 Mbit/s. Then, you associate the EIP with a NAT gateway. In this case, you are charged a data transfer fee. You have modified the bandwidth limit twice on the same day:

-   At 17:00 \(UTC+8\), you change the bandwidth limit from 10 Mbit/s to 20 Mbit/s.
-   At 23:00 \(UTC+8\), you change the bandwidth limit from 20 Mbit/s to 15 Mbit/s.

![The bandwidth-time graph](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2109039951/p2124.png)

The following table describes how fees are calculated based on the metering method that you select.

|Metering method|Configuration fee|Data transfer fee or bandwidth fee|Total|
|:--------------|:----------------|:---------------------------------|:----|
|Pay-by-data-transfer|Configuration fee: -   Instance unit price: In this example, the instance unit price of the EIP in the China \(Hangzhou\) region is USD 0.003/hour.
-   Usage duration: In this example, the EIP is used for 14.5 hours on that day. The usage duration is rounded up to 15 hours.
-   Configuration fee of the EIP on that day = Instance unit price \(USD/hour\) × Usage duration \(hours\) × Number of EIPs = 0.003 \(USD/hour\) × 15 \(hours\) × 1 = USD 0.045.

|Data transfer fee: -   Unit price of data transfer: In this example, the unit price of data transfer in the China \(Hangzhou\) region is USD 0.123/GB.
-   Amount of data transfer: In this example, 60 GB of data is used on that day.
-   Data transfer fee of the EIP on that day = Unit price of data transfer \(USD/GB\) × Amount of data transfer \(GB\) = 0.123 \(USD/GB\) × 60 \(GB\) = USD 7.38.

|Total fees = Configuration fee \(USD\) + Data transfer fee \(USD\) = USD 0.045 + USD 7.38 = USD 7.425.|
|Pay-by-bandwidth|The configuration fee is: -   Instance unit price: In this example, the instance unit price of the EIP in the China \(Hangzhou\) region is USD 0.074/day.
-   Usage duration: In this example, the EIP is used for 14.5 hours on that day. The usage duration is rounded up to 15 hours.
-   Configuration fee of the EIP on that day = Instance unit price \(USD/day\) × Usage duration \(days\) × Number of EIPs = 0.074 \(USD/day\) × \[15 \(hours\)/24 \(hours\)\] \(days\) × 1 = USD 0.04625.

|Bandwidth fee:

-   Bandwidth limit: The bandwidth fee is calculated based on the highest bandwidth limit value on that day. In this example, the highest bandwidth limit value is 20 Mbit/s.
-   Bandwidth unit price: USD 0.14 \[the unit price of bandwidth limit from 1 to 5 Mbit/s in China \(Hangzhou\) is USD 0.14/day\] × 5 + 0.5 \(the unit price of bandwidth limit higher than 5 Mbit/s is USD 0.5/day\) × \(20 - 5\) = USD 8.2/day.
-   Usage duration: In this example, the EIP is used for 14.5 hours on that day. The usage duration is rounded up to 15 hours.
-   Bandwidth fee of the EIP on that day = 8.2 \(USD/day\) × \[15 \(hours\)/24 \(hours\)\] \(days\) = USD 5.125.

|Total fees = Configuration fee + Bandwidth fee = USD 0.04625 + USD 5.125 = USD 5.17125.|

