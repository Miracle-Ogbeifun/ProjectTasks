
# **Create Key Vault and Store Secret**


## **Acceptance Criteria:**

Key Vault exists with purge protection enabled

<img width="1075" height="389" alt="Screenshot 2026-06-13 005749" src="https://github.com/user-attachments/assets/99e31c74-a32e-4fea-ab19-3883c8657d5c" />

<br><br>
<img width="678" height="567" alt="Screenshot 2026-06-13 005617" src="https://github.com/user-attachments/assets/255b7849-2cb2-4baa-8692-1d9f981162aa" />

<br><br>
Secret DbConnectionString is stored (value hidden in Portal)

<img width="989" height="461" alt="Screenshot 2026-06-13 011930" src="https://github.com/user-attachments/assets/6ea9e5ff-c084-47c6-ba0d-e0112f132a71" />

<br><br>
You can retrieve the secret value via CLI (screenshot the command output, redact the value)

<img width="1050" height="597" alt="Screenshot 2026-06-13 012234" src="https://github.com/user-attachments/assets/5044368a-a137-46ee-88a7-318ca93e5829" />

<br><br>

## **Create the Key Vault**

In Azure Portal Search for Key Vault.

<br><br>
<img width="1109" height="378" alt="Screenshot 2026-06-13 005103" src="https://github.com/user-attachments/assets/f94ee03d-9311-4d75-a3d7-9905531733cd" />

<br><br>
Click Create.

Configure:

Subscription:	Your subscription

Resource Group:	rg-novatech-mo-westEU

Key Vault Name:	kv-novatech-{id}-prod

Region:	West Europe

Pricing Tier:	Standard

<br><br>
<img width="806" height="493" alt="Screenshot 2026-06-13 005536" src="https://github.com/user-attachments/assets/3e377545-1a25-4fa6-8938-7ecee17967b3" />

Click Next.

<br><br>
**Enable Purge Protection**

Navigate to the Recovery Tab

Configure:

Soft Delete:	Enabled (default)

Purge Protection:	Enabled

<br><br>
<img width="805" height="555" alt="Screenshot 2026-06-13 005557" src="https://github.com/user-attachments/assets/c14746e1-773c-4390-9767-d8c730c9a827" />

<br><br>
Click Review + Create.

Click Create.

<br><br>
<img width="678" height="567" alt="Screenshot 2026-06-13 005617" src="https://github.com/user-attachments/assets/545b2be6-904f-40a4-8c4c-e4045e4d98b3" />

<br><br>
Wait for deployment to finish.

<br><br>
<img width="1012" height="456" alt="Screenshot 2026-06-13 005657" src="https://github.com/user-attachments/assets/04a5e031-cdb2-48b5-9a09-274dfbda34f6" />


**Verify Purge Protection**

Open the newly created Key Vault.

Go to: Settings → Properties

Verify: Purge Protection: Enabled

<br><br>
<img width="1075" height="389" alt="Screenshot 2026-06-13 005749" src="https://github.com/user-attachments/assets/6511579b-49f1-41f4-9818-9431e57a4c2a" />

<br><br>

## **Add the Secret**

Before Creating the Secret, I assigned to myself Key Vault Administrator using IAM inside the key vault created in order to be able to create the Secrect.

**Add a Role Assignment.**

Go to:

Key Vault → Access Control (IAM)

Click: Add → Add role assignment

Assigned Key Vault Administrator to myself

Saved the assignment.
Waited for 5–10 minutes for RBAC propagation.


### **Inside the Key Vault:**

Select Objects → Secrets.

Click Generate/Import.

<br><br>
<img width="1033" height="531" alt="Screenshot 2026-06-13 010021" src="https://github.com/user-attachments/assets/911a25eb-4018-4930-afc6-ea40b6a164eb" />

<br><br>
Configure:

Upload Option:	Manual

Name:	DbConnectionString

Value:	Server=tcp:novatech-db.database.windows.net;Database=NovaTechDB;

Enabled:	Yes

<br><br>
<img width="1087" height="565" alt="Screenshot 2026-06-13 010200" src="https://github.com/user-attachments/assets/8650cd90-2812-4934-aa9f-6b8598ea5509" />

<br><br>
Click Create.

<br><br>
<img width="989" height="461" alt="Screenshot 2026-06-13 011930" src="https://github.com/user-attachments/assets/9244db03-1284-4726-bf0c-53f657bb3a97" />

<br><br>

### **Retrieve the Secret Using Azure CLI**

Using Azure Cloud Shell 

In the Azure Portal Click the Cloud Shell (>_) icon at the top.

Select Bash.

<br><br>
**Run:**

az keyvault secret show \

--vault-name kv-novatech-mo-prod \

--name DbConnectionString \

--query value \

-o tsv

<br><br>
**Expected output:**

Server=tcp:novatech-db.database.windows.net;Database=NovaTechDB;

<br><br>
<img width="1050" height="597" alt="Screenshot 2026-06-13 012234" src="https://github.com/user-attachments/assets/59b8b2ae-a1bd-4a27-bfad-00ccc22a4d7a" />

