**Task 4: Deploy a Linux Virtual Machine**

What to do:

Deploy a VM with the following configuration:

Setting	Value

Image	Ubuntu Server 22.04 LTS

Size	Standard_B1s

Subnet	WebSubnet

Public IP	Yes (for testing — in production you'd use a load balancer)

Authentication	SSH public key (recommended) or password

Inbound ports	SSH (22) — for initial setup only


**After the VM is deployed:**

1.	SSH into the VM

2.	Install Nginx: sudo apt update && sudo apt install nginx -y

3.	Verify Nginx is running: sudo systemctl status nginx

4.	Open a browser and navigate to the VM's public IP — you should see the Nginx welcome page


**Acceptance Criteria:**

•	VM is running with status "Running" in the Portal
<img width="1245" height="644" alt="Screenshot 2026-04-15 231950" src="https://github.com/user-attachments/assets/663f20b2-ef79-4a52-a0c7-4285bf632381" />


•	VM size is Standard_B1s

•	VM is in WebSubnet
<img width="1308" height="652" alt="Screenshot 2026-04-16 222231" src="https://github.com/user-attachments/assets/21acd911-061b-4bc4-9f18-cf4ac0f54547" />
<img width="1051" height="640" alt="Screenshot 2026-04-15 231702" src="https://github.com/user-attachments/assets/d067c781-df00-4229-b55f-d058a92ec30a" />

•	Nginx welcome page loads in browser at the VM's public IP
