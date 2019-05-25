# Deploy an FTP server by using an EIP {#task_pfc_syx_yfb .task}

You can use the EIP cut-through mode to associate an Elastic IP Address \(EIP\) with an FTP server to provide FTP services. This topic takes an FTP server deployed with a Windows system as an example.

1.  [Create an EIP](reseller.en-US/User Guide/Create an EIP.md#). 
2.  Associate the EIP with a secondary Elastic Network Interface \(ENI\) and select the EIP cut-through mode. 

    **Note:** Make sure that the selected secondary ENI is not associated with any ECS instance.

    For more information, see [Configure the cut-through mode](reseller.en-US//Configure the cut-through mode.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155874901233631_en-US.png)

3.  Purchase an ECS instance of the Windows Server 2016 system and deploy an FTP service. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155874901233630_en-US.png)

4.  On the page of EIP list, click the link of the associated ENI. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/155874901233382_en-US.png)

5.  On the Network Interfaces page, find the ENI associated with the EIP and click **Bind to Instance** to associate the ENI with the ECS instance deployed with the FTP service. ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155874901233632_en-US.png) 

Use the EIP address associated with the ENI to access the FTP service.

**Note:** Make sure that the security group rules of the ECS instance allow access from the Internet.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/155874901233633_en-US.png)

