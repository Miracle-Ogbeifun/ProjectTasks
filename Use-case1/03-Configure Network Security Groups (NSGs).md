**Task 3: Configure Network Security Groups (NSGs)**

What to do:

Create three NSGs and associate them with their respective subnets:

NSG	Rules	Associate With

nsg-novatech-{id}-web	Allow inbound HTTP (80) and HTTPS (443) from Any	WebSubnet

nsg-novatech-{id}-app	Allow inbound port 8080 from WebSubnet only (10.0.1.0/24)	AppSubnet

nsg-novatech-{id}-data	Deny all inbound from Internet. Allow inbound from AppSubnet only (10.0.2.0/24)	DataSubnet


**Acceptance Criteria:**

Each NSG exists and is associated with the correct subnet
<img width="1127" height="392" alt="Screenshot 2026-04-15 213729" src="https://github.com/user-attachments/assets/3bc5800d-409e-4282-9a43-aa7d21f61dd2" />

WebNSG allows 80 and 443 from Any source
<img width="1299" height="533" alt="Screenshot 2026-04-15 210407" src="https://github.com/user-attachments/assets/01201bc1-bebb-420b-96c0-424f361ff754" />

AppNSG allows 8080 only from 10.0.1.0/24
<img width="1273" height="626" alt="Screenshot 2026-04-15 204652" src="https://github.com/user-attachments/assets/49b1e119-768d-4f8b-bf26-e7220ec38635" />

DataNSG has an explicit deny for Internet and allow from 10.0.2.0/24
<img width="1284" height="565" alt="Screenshot 2026-04-15 213158" src="https://github.com/user-attachments/assets/28ea648e-2046-45b9-863f-544d6bc0ff2b" />


**Create Network Security Group**

1.	In the search box at the top of the portal, type Network Security Group. Select Network Security group in the search results.

2.	Select + Create.
<img width="1154" height="609" alt="Screenshot 2026-04-15 200340" src="https://github.com/user-attachments/assets/910d79a8-973f-445c-ba31-76b1650c1807" />


3.	On the Basics tab of Create virtual network, enter, or select the following information:

Enter the following values:

•	Subscription: Select your Azure subscription.

•	Resource Group: Select the previously created RG

•	Name: Give the Network Security group a name.

•	Region: Select an Azure location East US
<img width="965" height="660" alt="Screenshot 2026-04-15 200517" src="https://github.com/user-attachments/assets/781e084b-1e5f-4c6b-992a-74bbc4523f83" />


Click on Review and Create
<img width="787" height="639" alt="Screenshot 2026-04-15 201531" src="https://github.com/user-attachments/assets/c90d4dff-06dd-4033-8fc5-e95fa941344a" />


Network Security Group has been created.
Click on Go to resource
<img width="998" height="588" alt="Screenshot 2026-04-15 202448" src="https://github.com/user-attachments/assets/4e284205-2c8e-4c23-a8bf-e9076e244eb1" />


Three network security groups were created.

WebNSG

AppNSG

DataNSG

<img width="1127" height="392" alt="Screenshot 2026-04-15 213729" src="https://github.com/user-attachments/assets/cb1b1781-55b6-4986-9e12-98abe3666614" />


To associate the NSGs with their respective Subnets

Select the Network Security Group you want to associate with

Select Settings >> Click on Subnets

Click on + Associate

Select Subnet to Associate with the NSG. Click OK

<img width="1137" height="618" alt="Screenshot 2026-04-15 211003" src="https://github.com/user-attachments/assets/432ef0ee-0543-4fb5-ac40-dbcd562ac4fc" />
<img width="1149" height="619" alt="Screenshot 2026-04-15 211031" src="https://github.com/user-attachments/assets/c9e78e11-d095-4f67-bcda-b9753dfd86f6" />


DataNSG has an explicit deny for Internet and allow from 10.0.2.0/24

In the DataNSG select Inbound security rules

Click on +Add

Under Source: select Service Tag

Source service tag: Select Internet

Select Deny and click OK
<img width="1096" height="655" alt="Screenshot 2026-04-15 213024" src="https://github.com/user-attachments/assets/cea2185d-eedb-405b-bd71-a3e5a296e4c4" />
<img width="1284" height="565" alt="Screenshot 2026-04-15 213158" src="https://github.com/user-attachments/assets/8e435e53-80e9-4dd2-af73-4153c833b1e0" />

