# **Configure VNet Peering**


## **Acceptance Criteria:**

Both peering connections show status "Connected"

<br><br>

<img width="1325" height="402" alt="image" src="https://github.com/user-attachments/assets/f30cee21-25f8-4ca0-b362-ede29c048d05" />

<br><br>

<img width="1323" height="424" alt="image" src="https://github.com/user-attachments/assets/a2bc8179-138c-49cf-ae1a-a09d44266609" />

<br><br>

<img width="1068" height="381" alt="image" src="https://github.com/user-attachments/assets/bea2659f-cb9c-43ca-9e75-36e309ffe1a1" />

<br><br>

Allow forwarded traffic is enabled on both sides

Allow gateway transit is disabled

<br><br>

<img width="608" height="538" alt="image" src="https://github.com/user-attachments/assets/540c3310-e21c-4905-8446-0f69a8a745a6" />

<br><br>




## **Create Peering from US VNet to Europe VNet**

Open Virtual Networks in Azure Portal.

Select your Europe VNet Created.

Under Settings, click Peerings.

Click + Add.

<img width="1165" height="556" alt="image" src="https://github.com/user-attachments/assets/6dc91215-66fd-4c74-acee-75e2c852c732" />


<br><br>

Configure:

**Local Network:** Peering link name	peer-eastus-to-westeurope

<img width="874" height="463" alt="image" src="https://github.com/user-attachments/assets/40d81aa5-5fae-491e-84b0-91d31bcffd64" />


**Remote Network:** Peering link name	peer-westeurope-to-eastus

Virtual network	Select Europe VNet

**Traffic Configuration**

Allow access to remote virtual network	Enabled

Allow forwarded traffic	Enabled

Allow gateway transit	Disabled

Use remote gateway	Disabled

Click Add.
<br><br>

<img width="831" height="429" alt="image" src="https://github.com/user-attachments/assets/d20db458-e3aa-47d1-9af8-7d66346d85a2" />

<br><br>
Azure automatically create the reverse peering if you configure both local and remote names in the same wizard.


<br><br>

Step 2: Verify the Reverse Peering

Navigate to Europe VNet → Peerings

Check whether a peering named: peer-westeurope-to-eastus

already exists.

<br><br>

Step 3: Verify Connection Status

Check both VNets. US VNet

Go to: US VNet → Peerings

You should see: Peering

peer-eastus-to-westeurope

Status: Connected

<br><br>

<img width="1325" height="402" alt="image" src="https://github.com/user-attachments/assets/61563ead-3226-477d-a3fa-e7ae815a34d1" />

<br><br>

<img width="1323" height="424" alt="image" src="https://github.com/user-attachments/assets/26a5b40e-fcbd-4df7-81e0-bf7569024c3f" />
