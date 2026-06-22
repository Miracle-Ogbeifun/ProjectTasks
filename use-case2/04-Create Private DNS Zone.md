
# **Create Private DNS Zone**


## **Acceptance Criteria:**

DNS Zone exists with the name novatech-{id}.internal

Two VNet links are visible (one for each VNet)

Auto-registration is enabled on both links

A records appear for any existing VMs


<br><br>
DNS Zone exists with the name novatech-{id}.internal

<img width="1292" height="368" alt="image" src="https://github.com/user-attachments/assets/f2adc5a1-359d-4069-b65d-4e62ccac9c99" />

<br><br>
Two VNet links are visible (one for each VNet)

Auto-registration is enabled on both links

<img width="1352" height="514" alt="image" src="https://github.com/user-attachments/assets/7f5b79b5-1b44-4318-a8e1-0a3f926b30fb" />

<br><br>
There is no existing VM

<img width="1347" height="533" alt="image" src="https://github.com/user-attachments/assets/8fbffd9e-a426-4905-957f-a33ec81a8367" />

<br><br>

## **Create the Private DNS Zone**

In the Azure Portal, search for Private DNS Zones.

Click + Create.

<br><br>

<img width="565" height="461" alt="image" src="https://github.com/user-attachments/assets/e6a92a7f-afcd-4c66-a915-b8085647bad2" />

<br><br>

Configure the following:

Subscription	

Resource Group

Name	novatech-{id}.internal

Click Review + Create → Create.
<br><br>

<img width="748" height="579" alt="image" src="https://github.com/user-attachments/assets/babe11ec-409a-436c-992e-6b3fef242f5a" />

<br><br>

<img width="1000" height="429" alt="image" src="https://github.com/user-attachments/assets/c1b98b4e-ba4b-4176-b54f-f41b52bf871b" />

<br><br>

**Link the US VNet**

Open the newly created Private DNS Zone.

Under Settings, select Virtual network links.

Click + Add.

<br><br>

<img width="791" height="496" alt="image" src="https://github.com/user-attachments/assets/30cf1493-9602-4492-aa9c-86b23520cf20" />

<br><br>

Configure:

Link name:	us-vnet-link

Virtual network:	US VNet

Enable auto registration:	Yes

Click OK or Create.
<br><br>

<img width="626" height="578" alt="image" src="https://github.com/user-attachments/assets/c24db554-f944-4bf4-913d-e613cb6f9e52" />


<br><br>

Still inside the DNS Zone, click + Add again.

Configure:

Link name:	europe-vnet-link

Virtual network:	Europe VNet

Enable auto registration:	Yes

Click OK or Create.

<br><br>

<img width="683" height="587" alt="image" src="https://github.com/user-attachments/assets/819a6c10-0fd1-42dd-aa07-42316b3497aa" />


<br><br>

<img width="1352" height="514" alt="image" src="https://github.com/user-attachments/assets/45608423-a7b3-4b5a-96d8-67608b061a3e" />

