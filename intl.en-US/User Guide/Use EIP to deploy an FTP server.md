# Use EIP to deploy an FTP server {#task_pfc_syx_yfb .task}

You can use the EIP cut-through mode to bind an EIP to an FTP server to provide FTP service. This tutorial takes an FTP server deployed on a Windows system as an example.

1.  [Create an EIP](reseller.en-US/User Guide/Create an EIP.md#). 
2.  Bind the EIP to a secondary ENI and select the EIP cut-through mode. 

    **Note:** Make sure that the selected secondary ENI is not bound to any ECS instance.

    For more information, see [Configure the cut-through mode](reseller.en-US/User Guide/Configure the cut-through mode.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155487280533631_en-US.png)

3.  Purchase an ECS instance of the Windows Server 2016 system and deploy an FTP service. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155487280533630_en-US.png)

4.  On the page of Elastic IP addresses, click the link of the bound ENI. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155487280533382_en-US.png)

5.  On the Network Interfaces page, find the ENI bound to the EIP and click **Bind to Instance** to bind the ENI to the ECS instance deployed with the FTP service. ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155487280533632_en-US.png) 

Then use the EIP address bound to the ENI to access the FTP service.

**Note:** Make sure that the security group rules of the ECS instance allow access from the Internet.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155487280633633_en-US.png)

