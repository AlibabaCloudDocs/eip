# Reinstate a released EIP

This topic describes how to reinstate a released elastic IP address \(EIP\) under your account based on the specified IP address or EIP ID. You cannot reinstate an EIP that has been allocated to another account.

1.  Log on to the [EIP console](https://vpc.console.aliyun.com/eip).

2.  In the upper-left corner, select the region where the EIP is created.

3.  On the **Elastic IP Addresses** page, click the **Request Custom IP** tab.

4.  In the **Request Custom IP** dialog box, set the following parameters:

    |Parameter|Description|
    |---------|-----------|
    |**EIP Type**|Select **Request Specific EIP**.You can request an EIP based on the specified IP address or EIP ID. The system automatically checks the requested IP address or EIP ID. If the EIP that you request has already been allocated to another account, the request fails. By default, a reinstated EIP is billed on a pay-by-data-transfer basis. The default maximum bandwidth of the EIP is 5 Mbit/s.

**Note:** You can reinstate up to 20 EIPs per month. If you want to increase the quota limit, [submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex). |
    |**Request Method**|Select a request method:    -   **Request by IP Address**: reinstate an EIP by specifying an IP address.
    -   **reinstate an EIP by specifying an EIP ID**: request an EIP by specifying an EIP ID. |
    |**IP Address**|Enter the IP address of the EIP that you want to request.**Note:** You can request only EIPs that you have used before. |
    |**Instance ID**|Enter the ID of the EIP that you want to reinstate.**Note:** You can reinstate only EIPs that you have used before. . |
    |**Connection Type**|Select a line type for the EIP:    -   **BGP \(Multi-ISP\)**
    -   **BGP \(Multi-ISP\)\_Pro**

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region.

For more information about the differences between BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro, see [Line types](/intl.en-US/User Guide/Overview.md). |

5.  Click **OK**.


