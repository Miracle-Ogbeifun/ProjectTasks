
# **Create Europe Virtual Network**

## **Acceptance Criteria:**

VNet created in West Europe with 172.16.0.0/16

All 3 subnets exist with correct address ranges

No overlap with the US VNet

<br><br>

## **Create the Europe Virtual Network**

In the Azure Portal search bar, type Virtual Networks.

Select Virtual Networks.

Click + Create.

<br><br>

<img width="885" height="568" alt="image" src="https://github.com/user-attachments/assets/f43ff30b-3765-4619-b493-bf623ef97797" />

<br><br>

Configure the following:

Subscription:	Your subscription

Resource Group:	Select the resource group created

Name: Vnet-Novatech-mo-Europe

Region	West Europe

Click Next: IP Addresses.

<br><br>

<img width="837" height="576" alt="image" src="https://github.com/user-attachments/assets/da6d65d4-e04b-4e30-82ad-95c0ca279325" />

<br><br>

Configure the Address Space

Under IPv4 address space:

Add:172.16.0.0/16

This ensures the Europe VNet uses a different address range than the US VNet (10.0.0.0/16).

<br><br>

<img width="781" height="575" alt="image" src="https://github.com/user-attachments/assets/1315c341-cd51-486e-a017-632a416ba73d" />

<br><br>

**Create the Subnets**

Delete the default subnet if present

Add Subnet 1

Name	WebSubnet

Address Range	172.16.1.0/24

Click Add.

<br><br>

Subnet 2

Name	AppSubnet

Address Range	172.16.2.0/24

Click Add.

<br><br>

Subnet 3

Name	DataSubnet

Address Range	172.16.3.0/24

Click Add.

Click Review + Create.

<br><br>

<img width="1040" height="526" alt="image" src="https://github.com/user-attachments/assets/b64d09f9-1d16-42da-afc8-9b02f9a22b2c" />

<br><br>

US VNet
<br><br>
<img width="890" height="581" alt="image" src="https://github.com/user-attachments/assets/619dfc86-49fe-4a13-807f-90079a00bd38" />

<br><br>

<img width="782" height="580" alt="image" src="https://github.com/user-attachments/assets/e80adbe6-567d-42a2-8c59-742853bad26b" />
