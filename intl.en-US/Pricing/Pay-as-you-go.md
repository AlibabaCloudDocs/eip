---
keyword: [Elastic IP Address, billing method, pay-as-you-go]
---

# Pay-as-you-go

This topic describes the pay-as-you-go billing method of elastic IP addresses \(EIPs\). Pay-as-you-go EIPs are billed based on data transfer or bandwidth usage.

## Overview

The pay-as-you-go billing method requires you to pay fees based on the actual resource usage. Pay-as-you-go EIPs are billed based on the following rules:

-   You can release a pay-as-you-go EIP at any time. After an EIP is released, the bill of the current hour or day is generated the next hour or day, and then fees are deducted from your account.
-   When you associate an EIP with an Elastic Compute Service \(ECS\) instance, you are not charged a configuration fee. However, you are charged a configuration fee when you associate an EIP with a NAT gateway, a Server Load Balancer \(SLB\) instance, a secondary Elastic Network Interface \(ENI\) instance, or a high-availability virtual IP address \(HAVIP\).

Pay-as-you-go EIPs are billed based on data transfer or bandwidth usage. The maximum bandwidth varies based on the billing methods described in the following table.

|Pay-by-data-transfer|Pay-by-bandwidth|
|--------------------|----------------|
|The maximum bandwidth indicates the upper limit of the bandwidth and is for reference only. The peak bandwidth is not guaranteed. In scenarios where demands exceed resources, the peak bandwidth may be limited.|The maximum bandwidth equals the peak bandwidth. In scenarios where demands exceed resources, the peak bandwidth can reach the maximum bandwidth.|
|The sum of the peak bandwidth of all pay-by-data-transfer EIPs in each region cannot exceed 5 Gbit/s. If your business requires a guaranteed bandwidth or larger bandwidth, you can purchase pay-by-bandwidth EIPs.|The sum of the maximum bandwidth of all pay-by-bandwidth EIPs in each region cannot exceed 50 Gbit/s. You can contact your product manager to increase the quota.|

## Pay-by-data-transfer

Total fee = Configuration fee + Data transfer fee. The billing cycle is one hour. Fees are calculated and bills generated on an hourly basis. If you use an EIP for less than one hour, the usage duration is rounded up to one hour.

The configuration fee and data transfer fee are calculated in the following ways:

-   Configuration fee = Instance unit price \(USD/hour\) × Usage duration \(hours\)

    Usage duration refers to the time period from when an EIP is created to when it is released.

-   Data transfer fee = Unit price of data transfer \(USD/GB\) × Amount of data transfer \(GB\)

    Data transfer refers to the cumulative outbound traffic of an EIP. Inbound traffic is not charged. Outbound traffic refers to the traffic that is transmitted from the data center of Alibaba Cloud to the Internet.


**Note:** After you change the maximum bandwidth of an EIP, the unit price of EIPs and unit price of data transfer remain unchanged. We recommend that you set the maximum bandwidth based on your requirements in case malicious requests or program errors incur an excessive data transfer fee.

EIPs support BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. EIPs of different line types are charged at different instance unit prices and different data transfer unit prices.

**Note:** If the information in the following table is different from that on the buy page in the console,the information on the [buy page](https://common-buy-intl.alibabacloud.com/eip/postpay) shall prevail.

|Region|Instance unit price \(USD/hour\)|Data transfer unit price \(USD/GB\)|
|:-----|--------------------------------|:----------------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Shenzhen\), China \(Heyuan\), and China \(Chengdu\)|0.0031|0.125|
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

Total fee = Configuration fee + Bandwidth fee. The configuration fee and bandwidth usage fee are billed on an hourly basis. If you use the service for less than one hour, the usage duration is rounded up to one hour. The billing cycle is one day. Fees are calculated and bills are generated on a daily basis.

The configuration fee and bandwidth usage fee are calculated in the following ways:

-   Configuration fee = Instance unit price \(USD/day\) × \[Usage duration \(hours\)/24\] \(days\)

    Usage duration refers to the time period from when an EIP is created to when it is released.

-   Bandwidth usage fee

    -   1 Mbit/s ≤ Maximum bandwidth ≤ 5 Mbit/s: Bandwidth usage fee = Bandwidth unit price \(USD/day for every Mbit/s\) × \[Usage duration \(hours\)/24\] \(days\) × Maximum bandwidth
    -   Maximum bandwidth \> 5 Mbit/s: Bandwidth usage fee = Unit price of bandwidth from 1 to 5 Mbit/s \(USD/day for every Mbit/s\) × \[Usage duration \(hours\)/24\] \(days\) × 5 + Unit price of bandwidth higher than 5 Mbit/s \(USD/day for every Mbit/s\) × \[Usage duration \(hours\)/24\] \(days\) × \(n-5\).

        In the preceding formula, n represents the maximum bandwidth value.

    The bandwidth usage fee is calculated based on a tiered pricing model with 5 Mbit/s as the standard bandwidth value.

    You can modify the maximum bandwidth at any time. If you increase or decrease the maximum bandwidth, the bandwidth usage fee is calculated based on the highest value on that day.


EIPs support BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro. EIPs of different line types are charged at different instance unit price and bandwidth unit prices.

**Note:** If the information in the following table is different from that on the buy page in the console,the information on the [buy page](https://common-buy-intl.alibabacloud.com/eip/postpay) shall prevail.

|Region|Instance unit price \(USD/day\)|
|:-----|-------------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Shenzhen\), China \(Heyuan\), China \(Chengdu\), and China \(Qingdao\)|0.0744|
|China \(Hong Kong\)|0.2112|
|Singapore \(Singapore\)|0.1512|
|Japan \(Tokyo\), US \(Virginia\), and US \(Silicon Valley\)|0.1128|
|Germany \(Frankfurt\), UK \(London\), Australia \(Sydney\), Indonesia \(Jakarta\), and India \(Mumbai\)|0.144|
|Malaysia \(Kuala Lumpur\)|0.072|

|Region|Bandwidth unit price \(USD/day\)|
|1 Mbps|2 Mbps|3 Mbps|4 Mbps|5 Mbps|6 Mbit/s and higher \(n represents the bandwidth value\)|
|------|:-------------------------------|
|------|:-----|:-----|:-----|:-----|:-------------------------------------------------------|
|China \(Hangzhou\), China \(Shanghai\), China \(Beijing\), China \(Zhangjiakou-Beijing Winter Olympics\), China \(Hohhot\), China \(Shenzhen\), China \(Chengdu\), Malaysia \(Kuala Lumpur\), China \(Hong Kong\), Singapore, Indonesia \(Jakarta\), US \(Virginia\), US \(Silicon Valley\), Germany \(Frankfurt\), UK \(London\), and Australia \(Sydney\)|0.14|0.28|0.43|0.57|0.71|0.71+\(n-5\)× 0.5|
|China \(Qingdao\)|0.11|0.21|0.32|0.43|0.53|0.53+\(n-5\)× 0.46|
|Japan \(Tokyo\)|0.17|0.34|0.51|0.68|0.85|0.85+\(n-5\)× 0.57|

|Region|Instance unit price \(USD/day\)|Bandwidth unit price \(USD/day\)|
|------|-------------------------------|--------------------------------|
|China \(Hong Kong\)|0.2112|1.430|

## Example

Assume that you create an EIP in the China \(Hangzhou\) region at 09:30:00 \(UTC+8\) and set the maximum bandwidth to 10 Mbit/s. Then, you associate the EIP with a NAT gateway and then your services incur a data transfer fee. You have modified the maximum bandwidth twice on the same day:

-   At 17:00:00 \(UTC+8\), you change the maximum bandwidth from 10 Mbit/s to 20 Mbit/s.
-   At 23:00:00 \(UTC+8\), you change the maximum bandwidth from 20 Mbit/s to 15 Mbit/s.

![Example](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/2109039951/p2124.png)

The following table describes how fees are calculated based on the billing method that you select.

|Billing method|Configuration fee|Data transfer fee or bandwidth usage fee|Total fee|
|:-------------|:----------------|:---------------------------------------|:--------|
|Pay-by-data-transfer EIPs|The configuration fee is: -   Instance unit price: Assume that the instance unit price of the EIP in the China \(Hangzhou\) region is USD 0.003/hour.
-   Usage duration: Assume that the EIP is used for 14.5 hours on that day. The usage duration is rounded up to 15 hours.
-   Configuration fee = Instance unit price \(USD/hour\) × Usage duration \(hours\) × Number of EIPs = 0.003 \(USD/hour\) × 15 \(hours\) × 1 = USD 0.045.

|The data transfer fee is: -   Unit price of data transfer: Assume that the unit price of data transfer in the China \(Hangzhou\) region is USD 0.123/GB.
-   Amount of data transfer: Assume that 60 GB of data is used on that day.
-   Data transfer fee = Unit price of data transfer \(USD/GB\) × Amount of data transfer \(GB\) = 0.123 \(USD/GB\) × 60 \(GB\) = USD 7.38.

|Total fee = Configuration fee \(USD\) + Data transfer fee \(USD\) = USD 0.045 + USD 7.38 = USD 7.425.|
|Pay-by-bandwidth EIPs|The configuration fee is: -   Instance unit price: Assume that the instance unit price of the EIP in the China \(Hangzhou\) region is USD 0.074/day.
-   Usage duration: Assume that the EIP is used for 14.5 hours on that day. The usage duration is rounded up to 15 hours.
-   Configuration fee = Instance unit price \(USD/day\) × Usage duration \(hours\) × Number of EIPs= 0.074 \(USD/day\)/24 \(hours\) × 15 \(hours\) × 1 = USD 0.04625.

|The bandwidth usage fee is:

-   Maximum bandwidth: This indicates the maximum bandwidth set for the EIP on that day, which is 20 Mbit/s.
-   Bandwidth unit price: USD 0.14 \(the unit price of bandwidth from 1 to 5 Mbit/s is USD 0.14/day\) × 5 + 0.5 \(the unit price of bandwidth higher than 5 Mbit/s is USD 0.5/day\) × \(20 - 5\) = USD 8.2/day.
-   Usage duration: Assume that the EIP is used for 14.5 hours on that day. The usage duration is rounded up to 15 hours.
-   Bandwidth usage fee on that day= 8.2 \(USD/day\)/24 \(hours\) × 15 \(hours\) = USD 5.125.

|Total fee = Configuration fee + Bandwidth usage fee = USD 0.04625 + USD 5.125 = USD 5.17125.|

