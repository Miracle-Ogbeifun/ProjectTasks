**Task 2: Create Virtual Network with Subnets**

What to do:

Create a Virtual Network with the following configuration:

Setting	Value

Address space	10.0.0.0/16

Subnet 1	WebSubnet — 10.0.1.0/24

Subnet 2	AppSubnet — 10.0.2.0/24

Subnet 3	DataSubnet — 10.0.3.0/24


Acceptance Criteria:

VNet shows address space 10.0.0.0/16

All 3 subnets are visible with correct address ranges
<img width="713" height="642" alt="Screenshot 2026-04-14 233900" src="https://github.com/user-attachments/assets/68c8c508-b326-416d-b61f-7475a9a7c21c" />

No overlapping address ranges


**Create a virtual network**

1.	In the search box at the top of the portal, enter Virtual network. Select Virtual networks in the search results.

2.	Select + Create.
   <img width="1258" height="638" alt="Screenshot 2026-04-14 230424" src="https://github.com/user-attachments/assets/105b8567-90d1-4271-b2d1-b19cd18e3dbc" />


3.	On the Basics tab of Create virtual network, enter, or select the following information:

Enter the following values:

•	Subscription: Select your Azure subscription.

•	Resource Group: Select the previously created RG

•	Virtual network name: Give the virtual network a name.

•	Region: Select an Azure location East US
<img width="1014" height="642" alt="Screenshot 2026-04-14 234426" src="https://github.com/user-attachments/assets/ff7c5d96-dc21-4e98-968a-6bc18e03e92c" />


4.	Select Next to proceed to the IP Address Space tab.
<img width="1008" height="639" alt="Screenshot 2026-04-14 233442" src="https://github.com/user-attachments/assets/fc91c266-d7c0-4b05-8891-e5641b5dfb12" />

6.	In the address space box in Subnets, Edit the subnets.
   
WebSubnet: 10.0.1.0/24

AppSubnet: 10.0.2.0/24

DataSubnet: 10.0.3.0/24

<img width="1046" height="593" alt="Screenshot 2026-04-14 233311" src="https://github.com/user-attachments/assets/5d8ef4a4-74bf-4900-b68d-d45b56a4b06b" />
<img width="713" height="642" alt="Screenshot 2026-04-14 233900" src="https://github.com/user-attachments/assets/af5fc562-73fc-4039-89a6-f2459f9947bd" />

