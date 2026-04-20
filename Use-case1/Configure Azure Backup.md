Task 6: Configure Azure Backup

What to do:

Create a Recovery Services vault

Create a backup policy with daily backups at 11:00 PM, retained for 7 days

Enable backup for your VM using this policy



Acceptance Criteria:

Recovery Services vault exists

<img width="782" height="623" alt="Screenshot 2026-04-17 213551" src="https://github.com/user-attachments/assets/353b6431-5e1a-4782-9956-409f9c121aba" />



Backup policy shows daily backup at 11:00 PM, 7-day retention

<img width="820" height="627" alt="Screenshot 2026-04-17 214940" src="https://github.com/user-attachments/assets/214884bc-ba58-4bb7-8de6-06361e721b2d" />



VM appears as a protected item in the vault


<img width="1122" height="639" alt="Screenshot 2026-04-17 215318" src="https://github.com/user-attachments/assets/fd492b59-b48d-43ec-97e7-55f36b100609" />




To create a Recovery Services vault:


1.	Sign in to the Azure portal.
   
3.	Search for Resiliency, and then go to the Resiliency dashboard.


<img width="878" height="593" alt="Screenshot 2026-04-17 213129" src="https://github.com/user-attachments/assets/65cedffc-5295-4209-8428-dab20a8a638c" />



Click on manage>> on the Vault pane, select + Vault.

<img width="1006" height="643" alt="Screenshot 2026-04-17 213153" src="https://github.com/user-attachments/assets/87127911-d526-4d7f-86a2-df8ef4da0eed" />



Select Recovery Services vault > Continue.

<img width="895" height="633" alt="Screenshot 2026-04-17 213304" src="https://github.com/user-attachments/assets/bb4ae5b3-4510-43cc-ac37-796a7e68fcf4" />



Enter the following values:

•	Subscription: Select your Azure subscription.

•	Resource Group: Select the previously created RG

•	Name: Give the Valt a name.

•	Region: Select an Azure location East US

After you provide the values, select Review + create.


<img width="872" height="648" alt="Screenshot 2026-04-17 213459" src="https://github.com/user-attachments/assets/4bff180f-7f48-47cd-91bb-efc6091f74cd" />



To finish creating the Recovery Services vault, select Create.

<img width="782" height="623" alt="Screenshot 2026-04-17 213551" src="https://github.com/user-attachments/assets/8755843f-0398-4d76-a295-ce6a0dbb7387" />



Apply a backup policy

To apply a backup policy to your Azure VMs, follow these steps:

1.	Go to Resiliency and select + Configure protection.


<img width="908" height="647" alt="Screenshot 2026-04-17 213754" src="https://github.com/user-attachments/assets/f3e8994d-2999-4dbf-ae7a-e0496a420a74" />



2. On the Configure protection pane,
select Resource managed by as Azure,
Datasource type as Azure Virtual machines,
Solution as Azure Backup, and then select Continue.


<img width="772" height="652" alt="Screenshot 2026-04-17 213917" src="https://github.com/user-attachments/assets/86ece01d-9e76-4854-aff6-fd173075e6e0" />



3.	On the Start: Configure Backup pane,
   select Azure Virtual machines as the Datasource type and
   select the vault you have created. Then select Continue.

<img width="833" height="640" alt="Screenshot 2026-04-17 214307" src="https://github.com/user-attachments/assets/f7982caa-1b57-4af7-939a-08b8a7449328" />



Backup policy shows daily backup at 11:00 PM, 7-day retention
4.	On the Configure backup pane, select the Policy sub type as Enhanced
select Create New,

<img width="1188" height="638" alt="Screenshot 2026-04-17 214735" src="https://github.com/user-attachments/assets/98788e4f-6593-4e7e-841d-302bac36d05f" />



<img width="820" height="627" alt="Screenshot 2026-04-17 214940" src="https://github.com/user-attachments/assets/ba67b8ed-1292-47e7-b365-ec10fe32c083" />



VM appears as a protected item in the vault
The Select virtual machines blade will open. 
Select the VMs you want to back up using the policy. Then select OK.

<img width="1122" height="639" alt="Screenshot 2026-04-17 215318" src="https://github.com/user-attachments/assets/c6427966-db63-4fff-adbd-76be8194c711" />


<img width="1031" height="526" alt="Screenshot 2026-04-17 215636" src="https://github.com/user-attachments/assets/1d9abc7e-719b-4a00-b999-6016b900ccb9" />
