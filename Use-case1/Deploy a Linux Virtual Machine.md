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




**Create virtual machine**

Enter virtual machines in the search.

Under Services, select Virtual machines.

In the Virtual machines page, select Create and then Virtual machine. The Create a virtual machine page opens.


<img width="1172" height="495" alt="Screenshot 2026-04-15 213851" src="https://github.com/user-attachments/assets/b4a5dd9b-62cd-4169-ab81-19ee4de06749" />



Enter the following values:

•	**Subscription:** Select your Azure subscription.

•	**Resource Group:** Select the previously created RG

**•	Name:** Give the Virtual machine a name.

<img width="960" height="598" alt="Screenshot 2026-04-15 222207" src="https://github.com/user-attachments/assets/f883ec78-ab6d-4a22-921f-fceab0c7fed9" />


**Availability zone:** select the desired zone

**Image:** select Ubuntu Server 22.04 LTS

**Size:** Standard_B1s

Authentication type: will be using SSH public key

<img width="1013" height="580" alt="Screenshot 2026-04-15 222243" src="https://github.com/user-attachments/assets/ae1c6476-9da7-411c-a1ff-3e6ae8477d42" />


<img width="904" height="584" alt="Screenshot 2026-04-15 222315" src="https://github.com/user-attachments/assets/4544ba77-7e79-4e0f-a28f-d35b5ac73e8a" />




**Selected port:** SSH (22)


<img width="948" height="654" alt="Screenshot 2026-04-15 222345" src="https://github.com/user-attachments/assets/b2f2a7f7-8f87-48e9-91eb-b960c03d1859" />


**OS disk type:**  locally-reduntant storage


<img width="861" height="651" alt="Screenshot 2026-04-15 222433" src="https://github.com/user-attachments/assets/7563807d-cc9a-4126-976a-13bf03a895a4" />


Virtual Network: Select the vnet previously created

Click on the drop-down arrow to select the previously created WebSubnet

Select Basic for the NIC network

Click on **review + create** to review and create the VM

<img width="929" height="636" alt="Screenshot 2026-04-15 222630" src="https://github.com/user-attachments/assets/089cc509-8339-49e5-9054-f01ea01ca8ae" />


**The VM has been created**

<img width="1245" height="644" alt="Screenshot 2026-04-15 231950" src="https://github.com/user-attachments/assets/9abe4974-220a-4ff0-aa80-09cac2bb8f9e" />



<img width="1308" height="652" alt="Screenshot 2026-04-16 222231" src="https://github.com/user-attachments/assets/0414538e-0f7e-4ad5-ac07-847d4062123d" />



For authentication, I downloaded the **SSH public key** after the VM creation.

Run ssh -I <your-private-key-file> .pem azureuser@<your_public-ip> on Cloud Shell inside the Azure portal to connect as the root user.

<img width="945" height="638" alt="Screenshot 2026-04-16 220504" src="https://github.com/user-attachments/assets/de2d3f0e-72ba-4008-919f-a1bccc6a82bb" />


<img width="1101" height="562" alt="Screenshot 2026-04-16 220522" src="https://github.com/user-attachments/assets/2e78a107-e4c2-43fd-99d5-af9c680bc6a9" />



**Install Nginx: sudo apt update && sudo apt install nginx -y**

<img width="1033" height="637" alt="Screenshot 2026-04-16 220709" src="https://github.com/user-attachments/assets/39ce77d4-1b00-4d43-8155-5c6a3b798132" />



**Verify Nginx is running: sudo systemctl status nginx**


<img width="1109" height="371" alt="Screenshot 2026-04-16 220812" src="https://github.com/user-attachments/assets/08ee54e8-e957-4587-9a92-6faae6c34226" />



