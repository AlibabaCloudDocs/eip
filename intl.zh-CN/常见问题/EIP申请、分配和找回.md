# EIP申请、分配和找回

本文介绍了EIP的申请、分配和找回的常见问题。

-   [为什么申请EIP时提示：eip frequent purchase？](#section_dm3_h54_7wx)
-   [为什么无法访问EIP？](#section_dk9_ltz_iai)
-   [新申请的EIP的分配策略是什么？](#section_gr9_7ut_dxo)
-   [EIP释放是否有保护时间？](#section_4pa_nt8_hum)

## 为什么申请EIP时提示：eip frequent purchase？

原因：阿里云识别您在近期出现频繁申请并更换EIP的行为，已触发阿里云非正常购买行为安全告警，阿里云将暂时限制您的EIP购买权限。

解决方法：请确保未来一周内申请EIP的个数不超过您账户允许保有的最大EIP个数，EIP购买权限可在一周后自动恢复。关于如何查看账户可保有的EIP个数，请参见[管理配额](/intl.zh-CN/用户指南/管理配额.md)。

## 为什么控制台找不到也不显示已购买的EIP？

可能原因如下：

-   EIP生产需要时间，一般需要3 ～５分钟。
-   查看EIP的地域与实际购买EIP的地域不一致。

解决方法：您可以在**费用中心**的**订单管理**，找到EIP的购买记录，查看订单详情中该EIP的地域，再切换到对应的地域查看已购买的EIP信息。

## 为什么无法访问EIP？

无法访问EIP的原因如下：

-   EIP没有绑定到云资源。
-   ECS实例配置了安全策略。例如ECS实例所在的安全组策略禁止80端口的访问，则无法访问该EIP的80端口。
-   EIP已经欠费。

## 新申请的EIP的分配策略是什么？

默认是随机分配EIP，但对于频繁申请又释放的用户，会优先分配之前使用过的EIP。

## EIP释放是否有保护时间？

一般情况下，释放EIP后到下一个整点前仍可以通过自定义IP找回释放的IP。例如您在12月27日05点05分释放了EIP实例，则在12月27日05点05分到12月27日06点00分仍可通过自定义IP找回释放的EIP。

