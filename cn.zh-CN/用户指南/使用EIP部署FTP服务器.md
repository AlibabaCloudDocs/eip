# 使用EIP部署FTP服务器 {#task_pfc_syx_yfb .task}

您可以通过EIP可见模式将EIP绑定到FTP服务器上对外提供FTP服务。本教程以Windows系统上部署的FTP服务器为例。

1.  [申请EIP](cn.zh-CN/用户指南/申请EIP.md#)。 
2.  将申请的EIP和一个辅助弹性网卡绑定，并使用EIP网卡可见模式。 

    **说明：** 确保选择的辅助弹性网卡没有绑定任何ECS实例。

    配置详情参见[设置EIP网卡可见](cn.zh-CN/用户指南/设置EIP网卡可见.md#)。

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/154384885833631_zh-CN.png)

3.  购买一台Windows Server 2016系统的ECS实例，部署一个FTP服务。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/154384885833630_zh-CN.png)

4.  在EIP列表页面，单击已绑定的ENI链接。 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/65386/154384885833382_zh-CN.png)

5.  在网卡列表页面，找到已绑定EIP的ENI，然后单击**绑定实例**将其和已部署FTP服务的ECS实例绑定。 ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/154384885833632_zh-CN.png) 

配置完成后，使用ENI绑定的EIP地址访问FTP服务。

**说明：** 确保您的ECS实例的安全组规则允许来自公网访问。

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/66339/154384885833633_zh-CN.png)

