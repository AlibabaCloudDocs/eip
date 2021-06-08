---
keyword: [EIP, Elastic IP Address, history, custom]
---

# Recover a released EIP

This topic describes how to recover a released elastic IP address \(EIP\). You can recover an EIP that belongs to your account within the first seven days after the EIP is released. To recover the EIP, you must specify the IP address or ID of the EIP. You are not allowed to recover EIPs that are allocated to other accounts, locked for security purposes, or expired.

1.  Log on to the [Elastic IP Address console](https://vpc.console.aliyun.com/eip).

2.  In the top navigation bar, select the region where the EIP is deployed.

3.  On the **Elastic IP Addresses** page, click the **Request Custom IP** tab.

4.  In the **Request Custom IP** dialog box, set the following parameters.

    |Parameter|Description|
    |---------|-----------|
    |**EIP Type**|Select **Request Specific EIP**. You can specify the IP address or ID of the EIP. The system automatically checks the requested IP address or EIP ID. If the EIP that you request is expired, allocated to another account, or locked for security purposes, the request is denied. By default, a recovered EIP is billed on a pay-by-data-transfer basis and the bandwidth limit of the EIP is 5 Mbit/s.

**Note:** If you want to use the following features,[submit a ticket](https://workorder-intl.console.aliyun.com/#/ticket/createIndex):

    -   Recover an EIP that is released for more than seven days.
    -   Recover the static public IP address of an Elastic Compute Service \(ECS\) instance.
    -   You can recover EIPs at most 20 times per month. To recover EIPs more than 20 times, request a quota increase. |
    |**Request Method**|Select a request method:    -   **Request by IP Address**: Specify the IP address of the EIP or the static public IP address of the ECS instance.
    -   **Request by EIP Instance ID**: Specify the ID of the EIP. |
    |**IP Address**|Enter the IP address of the EIP that you want to recover. **Note:** You can recover only EIPs that you have used before. |
    |**Instance ID**|Enter the ID of the EIP that you want to recover. **Note:** You can recover only EIPs that you have used before.. |
    |**Connection Type**|Select a line type for the EIP:    -   **BGP \(Multi-ISP\)**
    -   **BGP \(Multi-ISP\) Pro**

**Note:** BGP \(Multi-ISP\) Pro is supported only in the China \(Hong Kong\) region.

For more information about the differences between BGP \(Multi-ISP\) and BGP \(Multi-ISP\) Pro, see [Line types](/intl.en-US/User Guide/Overview.md). |

5.  Click **OK**.


