
# **Create Log Analytics Workspace & Diagnostic Settings**


## **Acceptance Criteria:**


Log Analytics workspace exists

<img width="1033" height="421" alt="Screenshot 2026-06-13 013125" src="https://github.com/user-attachments/assets/414d515d-ef18-449a-9f50-64507735d30d" />

<br><br>
At least one diagnostic setting is configured and sending data

<img width="1288" height="477" alt="Screenshot 2026-06-13 132213" src="https://github.com/user-attachments/assets/4550ea0e-63fe-4427-a0c8-2d9f151e5693" />

<br><br>
You can run a KQL query and see results

<img width="1302" height="506" alt="Screenshot 2026-06-13 125643" src="https://github.com/user-attachments/assets/8c4f695c-eee2-482f-82e0-db03a83e4150" />

<br><br>

## **Create Log Analytics Workspace**

**Step 1: Create Workspace**

Go to Azure Portal

Search: Log Analytics workspaces

Click Create

<br><br>
<img width="891" height="283" alt="Screenshot 2026-06-13 012754" src="https://github.com/user-attachments/assets/72c7b1a0-2001-4966-80a0-31d126bb94f8" />

<br><br>
**Basics Configuration**

Fill in:

Setting	Value

Subscription:	Your subscription

Resource Group:	rg-novatech-mo-westEU

Name:	log-novatech-{id}-prod

Region	East US

<br><br>
<img width="782" height="584" alt="Screenshot 2026-06-13 012958" src="https://github.com/user-attachments/assets/c335b227-d443-4823-a4f3-6a023156fa61" />

<br><br>

<img width="614" height="418" alt="Screenshot 2026-06-13 013030" src="https://github.com/user-attachments/assets/87b314ff-bfa1-4f31-a8a0-5d59b76b65ad" />

Click Review + Create → Create

<br><br>

Go to the VM

Open Virtual Machines → New VM

Go to “Settings” section → Extensions + applications

Install Azure Monitor Agent 

Go to: Extensions + applications

Then click: + Add extension

Select: Azure Monitor Agent

Install it.

<br><br>
<img width="811" height="492" alt="Screenshot 2026-06-13 015311" src="https://github.com/user-attachments/assets/8b126dab-74f7-4508-a23a-b6a097632640" />

<br><br>

**Create Data Collection Rule**

Search in Azure: Data Collection Rules

Click: + Create

<br><br>
<img width="870" height="428" alt="Screenshot 2026-06-13 020002" src="https://github.com/user-attachments/assets/7d7ca7cd-c7d3-4e7f-948b-f878e074221d" />

<br><br>

Configure:

Name:	vm-dcr-novatech

Resource group

Region:	same as VM


**Add resources**

Add VM(s)

<br><br>
**Select Data Source**

Choose: Performance counters

Syslog

Destination: Select log-novatech-mo-prod

<br><br>
<img width="612" height="588" alt="Screenshot 2026-06-13 121209" src="https://github.com/user-attachments/assets/c8009554-8efa-4ee9-98ca-d48d166f5821" />

<br><br>
<img width="680" height="585" alt="Screenshot 2026-06-13 121226" src="https://github.com/user-attachments/assets/7ed89f61-71d8-4c21-8c39-9ced99cabcb5" />

<br><br>

Click Create

<br><br>
<img width="1017" height="399" alt="Screenshot 2026-06-13 122548" src="https://github.com/user-attachments/assets/a9edeb40-8f8a-4fb0-b883-a7ff4af5897b" />

<br><br>

**Then test in Log Analytics**

Go to: Log Analytics Workspace → Logs

Under Tables, find Heartbeat.

Click the Run button next to Heartbeat.

<br><br>
<img width="1148" height="509" alt="Screenshot 2026-06-13 124449" src="https://github.com/user-attachments/assets/ebfe4421-7c87-4d0f-9a32-6f9a1ccc5a7f" />

<br><br>
Heartbeat returned records

<img width="1302" height="506" alt="Screenshot 2026-06-13 125643" src="https://github.com/user-attachments/assets/ee492acd-95fc-41f6-8ad6-1606dffd52de" />

<br><br>
The important takeaway is:

The VM is sending Heartbeat data to Log Analytics

The Log Analytics Workspace is receiving data

The Azure Monitor Agent / Data Collection Rule is working
