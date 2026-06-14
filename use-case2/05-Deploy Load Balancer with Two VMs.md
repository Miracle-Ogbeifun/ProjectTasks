
Deploy Load Balancer with Two VMs

Acceptance Criteria:

Both VMs are running (no public IPs)

<img width="1312" height="443" alt="Screenshot 2026-06-11 153550" src="https://github.com/user-attachments/assets/092a8ceb-adbc-4de1-aecf-a94b7e4bc967" />

Load Balancer has a public IP

<img width="1174" height="446" alt="image" src="https://github.com/user-attachments/assets/1f4d3187-f9cb-438c-91bd-1757da21b947" />


Backend pool shows both VMs as "Healthy"

<img width="1296" height="495" alt="Screenshot 2026-06-11 171032" src="https://github.com/user-attachments/assets/8044cced-e1e0-4306-991e-df941b9430da" />


Browsing to the LB's public IP shows the Nginx welcome page

<img width="1141" height="578" alt="image" src="https://github.com/user-attachments/assets/1a54f865-1958-4da8-8683-32df0e14cb3d" />


Refreshing multiple times continues to work (traffic distributed)


What to do:

Deploy 2 VMs (B1s, Ubuntu 22.04) in the US WebSubnet:
vm-novatech-{id}-web01
vm-novatech-{id}-web02
Install Nginx on both (same as UC1)
Do NOT assign public IPs to these VMs — they'll be behind the LB
Create a Standard Load Balancer (public):
Frontend IP: New public IP
Backend pool: Both VMs
Health probe: HTTP on port 80, interval 5 seconds
Load balancing rule: HTTP (port 80) → backend pool port 80



Deploy VM 1

Go to Azure Portal → Virtual Machines → Create

<img width="1077" height="491" alt="Screenshot 2026-06-11 145446" src="https://github.com/user-attachments/assets/2e35b82e-6a6a-4b9b-a883-91f8121d607d" />


Basics configuration
Resource Group
VM Name	
Region	East US
Image	Ubuntu Server 22.04 LTS
Size	Standard B1s
Authentication	SSH Key or Password
Username	Your choice

<img width="874" height="549" alt="Screenshot 2026-06-11 150957" src="https://github.com/user-attachments/assets/eccff22d-d5e4-4d04-bbef-15c91e861238" />

<img width="794" height="562" alt="Screenshot 2026-06-11 151035" src="https://github.com/user-attachments/assets/92ed0b74-9263-42d4-80ea-11d054659c58" />



Networking

Select:
Virtual Network	US VNet
Subnet	WebSubnet
Public IP	None
NIC Network Security Group	Basic

Important: Set Public IP = None

<img width="951" height="595" alt="Screenshot 2026-06-11 151215" src="https://github.com/user-attachments/assets/b616973d-c764-44fc-b9a3-b2b0faf3803c" />

Click Review + Create → Create

<img width="1339" height="391" alt="Screenshot 2026-06-11 151858" src="https://github.com/user-attachments/assets/285bab51-86ad-4b33-aa50-87e93d9373de" />



Deploy VM 2

Repeat the same process.

Use:

Setting	Value
VM Name	vm-novatech-{id}-web02
Region	East US
Size	Standard B1s

<img width="862" height="578" alt="Screenshot 2026-06-11 152210" src="https://github.com/user-attachments/assets/db88b3a4-5408-44bf-91d8-82af29e32e54" />

<img width="898" height="582" alt="Screenshot 2026-06-11 152250" src="https://github.com/user-attachments/assets/68988f48-2698-47b6-90d1-7b8729b1a583" />



VNet	US VNet
Subnet	WebSubnet
Public IP	None

<img width="887" height="580" alt="Screenshot 2026-06-11 152458" src="https://github.com/user-attachments/assets/7514fb6f-654b-483b-875f-08b9f8b1702a" />

Create the VM.

<img width="1312" height="443" alt="Screenshot 2026-06-11 153550" src="https://github.com/user-attachments/assets/9e287d5b-43ba-4783-a0c7-e0507c265142" />




**To Install Nginx**

For each VM:

Open the VM.
Select Operations → Run command.
Choose RunShellScript.
Paste:
sudo apt update
sudo apt install nginx -y
sudo systemctl enable nginx
sudo systemctl start nginx
Click Run.

<img width="1279" height="607" alt="Screenshot 2026-06-11 163337" src="https://github.com/user-attachments/assets/bf6aa964-2985-46a1-9ecd-0ba0a85ada23" />

<img width="1250" height="614" alt="Screenshot 2026-06-11 163317" src="https://github.com/user-attachments/assets/cdf8b146-d12d-45ce-9388-b9891d60b016" />

Repeat for:

vm-novatech-{id}-web01
vm-novatech-{id}-web02

This executes the commands inside the VM without requiring SSH access.

Verify Nginx is Working

For each VM:

Go to Run command.
Run:
curl http://localhost

<img width="1362" height="608" alt="Screenshot 2026-06-11 163454" src="https://github.com/user-attachments/assets/44ce77bd-907c-4b74-b269-b1443dfca68c" />


If successful, you should see HTML beginning with something like:

<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>

<img width="1141" height="578" alt="Screenshot 2026-06-12 224918" src="https://github.com/user-attachments/assets/90871379-8847-43f2-9064-bbce87a6ea14" />



**Create a Standard Load Balancer**

Search for Load Balancers.

Click Create.

<img width="797" height="394" alt="Screenshot 2026-06-11 165500" src="https://github.com/user-attachments/assets/290ab6c5-dd74-4967-900a-3155a462e8d1" />


Basics Setting	Value
Name	novatech-lb
Region	East US
Type	Public
SKU	Standard

<img width="847" height="577" alt="Screenshot 2026-06-11 170228" src="https://github.com/user-attachments/assets/832d0254-07e0-48f0-9ed9-970e44a126a0" />

Create Frontend IP

lb-public-ip

<img width="973" height="375" alt="Screenshot 2026-06-11 170245" src="https://github.com/user-attachments/assets/9b02c87b-aac7-4b4c-811c-9eaaaad5f842" />


Create the Load Balancer.



Configure Backend Pool

Open the Load Balancer.

Navigate:

Settings → Backend Pools

Click:

+ Add

<img width="907" height="482" alt="Screenshot 2026-06-11 170526" src="https://github.com/user-attachments/assets/f45c6a11-3340-469d-80aa-4aef67e7d390" />


Name:

web-backend-pool

Add:


<img width="1255" height="575" alt="Screenshot 2026-06-11 170822" src="https://github.com/user-attachments/assets/855b669c-de6f-4bae-b6f0-6d05a6a630e3" />

vm-novatech-{id}-web01
vm-novatech-{id}-web02

Save.

<img width="1296" height="495" alt="Screenshot 2026-06-11 171032" src="https://github.com/user-attachments/assets/55500163-78dc-4125-8aec-84364eca3547" />


**Create Health Probe**

Navigate:

Health Probes

Click:

+ Add

<img width="913" height="494" alt="Screenshot 2026-06-11 171111" src="https://github.com/user-attachments/assets/f0b61d49-e036-44c3-94a4-17e28b4f8617" />


Configure:

Setting	Value
Name	http-probe
Protocol	HTTP
Port	80
Interval	5 seconds

<img width="770" height="585" alt="Screenshot 2026-06-11 171207" src="https://github.com/user-attachments/assets/b9765f57-a115-4811-95b8-83bb024a7ece" />

Save.


**Create Load Balancing Rule**

Navigate:

Load Balancing Rules

Click:

+ Add

<img width="894" height="530" alt="Screenshot 2026-06-11 171253" src="https://github.com/user-attachments/assets/3912699a-4bca-45ae-80dd-fa1db565bcec" />


Configure:

Setting	Value
Name	http-rule
Frontend IP	Public Frontend
Protocol	TCP
Frontend Port	80
Backend Port	80
Backend Pool	web-backend-pool
Health Probe	http-probe

<img width="800" height="587" alt="Screenshot 2026-06-11 171554" src="https://github.com/user-attachments/assets/0bbd205d-d70e-41a8-8bbd-394f91733afa" />

<img width="853" height="575" alt="Screenshot 2026-06-11 171616" src="https://github.com/user-attachments/assets/1c3221f5-cf2b-4945-90ee-88e489ee231e" />

Save.


<img width="1090" height="591" alt="Screenshot 2026-06-12 121705" src="https://github.com/user-attachments/assets/28a5cd40-5ed6-415a-836e-01f49aa1222c" />


Verify Health

Open:

Load Balancer → Backend Pools

You should see:

vm-novatech-{id}-web01
Healthy

vm-novatech-{id}-web02
Healthy

<img width="1323" height="559" alt="Screenshot 2026-06-12 134620" src="https://github.com/user-attachments/assets/08d65807-191c-4ce0-8f18-b3d2488103a2" />
