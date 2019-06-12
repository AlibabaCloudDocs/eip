# Disassociate an EIP from a cloud instance {#task_bh5_dll_vdb .task}

You can disassociate an Elastic IP Address \(EIP\) from a cloud instance when Internet access is no longer required by the cloud instance. After an EIP is disassociated from a cloud instance, you still need to pay the EIP retention fee.

1.  Log on to the [VPC console](https://partners-intl.console.aliyun.com/#/vpc).
2.  In the left-side navigation pane, choose **Elastic IP Addresses**.
3.  Select the region of the target EIP.
4.  On the Elastic IP Addresses page, find the target EIP and click **Unbind** in the **Actions** column. If your EIP is associated with a NAT Gateway for which DNAT or SNAT entries have been created, choose **More** \> **Force Unbind NAT** in the **Actions** column.
5.  In the displayed dialog box, click **OK**.

