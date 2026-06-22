
# **Deploy Azure Container Instance**


## **Acceptance Criteria:**

ACI shows status "Running"

<br><br>
<img width="1206" height="541" alt="Screenshot 2026-06-13 003045" src="https://github.com/user-attachments/assets/121848c6-9e28-4f96-8b2e-77ddbac57e95" />

<br><br>
Nginx is accessible via the ACI's public IP


Container logs show Nginx started successfully

<br><br>
<img width="1172" height="595" alt="Screenshot 2026-06-13 003753" src="https://github.com/user-attachments/assets/4ac7f321-e04c-4797-b32f-4ef86d31bbf2" />

<br><br>

## **Create the Container Instance**

In the Azure Portal Search for Container Instances.

Click Create.

<br><br>
<img width="810" height="573" alt="Screenshot 2026-06-12 231402" src="https://github.com/user-attachments/assets/5dd86e2b-a3cb-4c0e-9da7-e0448f388b51" />

<br><br>
Configure Basic Settings

Under the Basics tab, enter:

Subscription:	Select your subscription

Resource Group:	Your existing resource group

Container name:	aci-novatech-{id}-api

Region:	West Europe (same region as the VNet)

Image source:	Docker Hub or Other Registry

Image type:	Public

Image:	nginx:latest

OS Type:	Linux

Size	1 vCPU, 1.5 GB Memory

<br><br>
<img width="829" height="584" alt="Screenshot 2026-06-12 231421" src="https://github.com/user-attachments/assets/a28fed3c-0d76-46ed-852b-db1740a65cf8" />

<br><br>
Click Next: Networking.

Under Networking Type, select:

Public

Leave DNS name label blank.

**Ensure**: Public IP = Enabled

Port = 80

Under Ports, add:

Protocol	TCP

Port:	80

<br><br>
<img width="797" height="592" alt="Screenshot 2026-06-12 231846" src="https://github.com/user-attachments/assets/60755ecd-f806-432c-93ad-b77a8ed5c666" />

<br><br>
Click Next: Advanced.


**Configure Advanced Settings**

Setting	Value

Restart Policy	Always

Leave other settings as default.

<br><br>
<img width="931" height="587" alt="Screenshot 2026-06-12 231953" src="https://github.com/user-attachments/assets/5065a399-11c8-4778-b515-07d5976f7fc9" />

<br><br>
Click Review + Create.

<br><br>
<img width="724" height="577" alt="Screenshot 2026-06-12 232030" src="https://github.com/user-attachments/assets/3869349e-322e-49a4-8b65-614bd433b551" />

<br><br>
Wait for validation to pass.
Click Create.

<br><br>
<img width="1031" height="449" alt="Screenshot 2026-06-13 002948" src="https://github.com/user-attachments/assets/d84920cc-73e1-4c1c-88ee-dc766bb6eb0e" />

<br><br>
**Verify Container Status**

After deployment Open the Container Instance.

Go to Overview.

Verify:

State:	Running

OS:	Linux

Image:	nginx:latest

CPU	1

Memory	1.5 GB

This satisfies:

<br><br>
<img width="1206" height="541" alt="Screenshot 2026-06-13 003045" src="https://github.com/user-attachments/assets/68cc3bef-9f7c-4317-be14-22e14d8d9943" />


ACI shows status Running

<br><br>


**Check the logs**

Go to:

Container Instance → Containers → Logs

<br><br>
<img width="1357" height="517" alt="image" src="https://github.com/user-attachments/assets/f0356e39-0d3f-4563-b06b-b669c3d8cdf1" />

<br><br>

You should see messages similar to:

/docker-entrypoint.sh: Configuration complete; ready for start up

or other Nginx startup messages.

<br><br>
<img width="1172" height="595" alt="Screenshot 2026-06-13 003753" src="https://github.com/user-attachments/assets/324680a3-0602-4d36-b4ce-568904f8f970" />

<br><br>
This would satisfy that Container logs show Nginx started successfully.


**NOTE:** The lab instructions appear to combine two deployment models: VNet Deploymenet and Public Deployment

Azure Container Instances typically use one model or the other. I used the VNet Deployment in order to select the specified VNet.

<br><br>
VNet Deployment
Deploy into Europe WebSubnet
Gets private IP (like 172.16.1.4)
No public IP

<br><br>
Public Deployment
Deploy with Public networking
Gets public IP
Not attached to WebSubnet

<br><br>
<img width="861" height="582" alt="Screenshot 2026-06-13 004944" src="https://github.com/user-attachments/assets/9e3fa31d-8612-4bc0-8301-e3f6f2f8ab61" />


