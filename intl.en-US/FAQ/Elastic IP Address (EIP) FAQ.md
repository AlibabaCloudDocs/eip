# Elastic IP Address \(EIP\) FAQ {#concept_o35_55m_vdb .concept}

## 1. What is the difference between an EIP and a public IP address of an ECS instance? {#section_dfd_cvm_vdb .section}

-   A public IP can be found on the private NIC of the ECS instance, while an EIP is a NAT IP that is mapped to the private NIC of the ECS instance. Therefore, the EIP cannot be found on the NIC of the ECS instance.

-   You cannot unbind a public IP from the ECS instance but you can bind and unbind an EIP whenever Internet communication is not needed.


## 2. Why can't I find an EIP on the private NIC? {#section_rd3_w5m_vdb .section}

An EIP is configured on the Internet gateway and mapped to the private NIC of the ECS instance. Therefore, it cannot be found on the private NIC.

## 3. How many EIPs can an account create? {#section_sd3_w5m_vdb .section}

An account can create 20 EIPs at most. Open a ticket if you want to apply for more.

## 4. What resources can an EIP be bound to? {#section_td3_w5m_vdb .section}

An ECS or SLB instance of the VPC network, or a NAT Gateway.

## 5. Can an EIP be bound to an ECS instance of the classic network? {#section_ud3_w5m_vdb .section}

No.

## 6. Why can't I access an EIP I have created? {#section_wd3_w5m_vdb .section}

-   The EIP is not bound to any resources.
-   If the EIP is bound to an ECS instance, check the security rules of the ECS instance. For example, if the ECS instance is added to a security group that denies the access from port 80, then you cannot access the EIP over port 80.
-   Check if payment for the EIP is overdue.

## 7. Why can't I bind an EIP to an ECS instance? {#section_gk4_fvm_vdb .section}

-   Check the network type of the ECS instance. An EIP can only be bound to an ECS instance of the VPC network.
-   The regions of the EIP and ECS instance are not the same.
-   The ECS instance is not running or stopped.
-   The ECS instance has been bound to an EIP.
-   The ECS instance has a public IP that is system allocated.

## 8. Why can't I bind an EIP to a NAT Gateway? {#section_a23_w5m_vdb .section}

If you purchased a NAT bandwidth package before January 26, 2018, you still need to use the NAT bandwidth package to provide public IPs for the NAT Gateway. To bind an EIP, open a ticket.

