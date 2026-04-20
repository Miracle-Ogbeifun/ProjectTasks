**Task 5: Create Storage Account with Blob and File Share**

What to do:

Create a Storage Account and configure:

**Setting	Value**

Name	stnovatech{id}prod001

Performance	Standard

Redundancy	LRS (Locally Redundant Storage)

Blob container	company-assets (Private access level)

File share	it-department (Quota: 5 GB)

Upload a test file (any small file — a text file, image, etc.) to the blob container.


**Acceptance Criteria:**

Storage Account exists with LRS redundancy

<img width="1206" height="647" alt="Screenshot 2026-04-16 230952" src="https://github.com/user-attachments/assets/ddc8a4d1-188c-4326-afbb-826e19a42b38" />



Blob container company-assets exists with Private access level

<img width="1193" height="643" alt="Screenshot 2026-04-16 231435" src="https://github.com/user-attachments/assets/1a0b34ac-7217-4a36-a3a5-54c0b8ec1903" />



File share it-department exists with 5 GB quota

<img width="1235" height="586" alt="Screenshot 2026-04-17 212602" src="https://github.com/user-attachments/assets/239de7cd-e9f6-4da9-82d8-e00be7c02156" />


At least one test file is uploaded to the blob container

<img width="1157" height="532" alt="Screenshot 2026-04-16 231657" src="https://github.com/user-attachments/assets/3513cdb6-7f0f-46a9-a5e4-7c5c40e95f4f" />




Deploy a Linux Virtual Machine in Azure portal

1.	Sign in to the Azure portal.
   
3.	In the search box at the top of the portal, type Storage Account . Select Storage Account in the search results.
   
5.	Select **+ Create.**


   Enter the following values:

   
•	Subscription: Select your Azure subscription.

•	Resource Group: Select the previously created RG

•	Name: Give the Network storage account a name.

•	Region: Select an Azure location East US

•	Performance: Standard

<img width="869" height="646" alt="Screenshot 2026-04-16 224152" src="https://github.com/user-attachments/assets/9fff4167-f7cc-4403-a112-79a02a71d370" />


<img width="977" height="653" alt="Screenshot 2026-04-16 224204" src="https://github.com/user-attachments/assets/9ff6802a-7426-4bd6-ae17-e5da3ac0fd15" />


Click review **+ create to create.**

<img width="1037" height="562" alt="Screenshot 2026-04-16 224254" src="https://github.com/user-attachments/assets/9ec8d195-fad4-416a-bd08-6ebf2d70a5a0" />


Blob container company-assets exists with Private access level

Open the storage account

Click on Data storage>> containers

Click on +Add container


<img width="1190" height="626" alt="Screenshot 2026-04-16 231056" src="https://github.com/user-attachments/assets/4165f6e2-3dc2-4b03-934b-2cb0c596d6cf" />


**Container is Created**

<img width="1193" height="643" alt="Screenshot 2026-04-16 231435" src="https://github.com/user-attachments/assets/8e6c9b06-eb1a-4d69-af24-1039635fc0e7" />




Click on the container to open

**Click on +Add Directory to upload a file to the container
**

<img width="1333" height="603" alt="Screenshot 2026-04-16 231606" src="https://github.com/user-attachments/assets/ca209126-6a03-4047-ab94-4691ddc00881" />




**At least one test file is uploaded to the blob container**

<img width="1157" height="532" alt="Screenshot 2026-04-16 231657" src="https://github.com/user-attachments/assets/a03c6123-d3f2-4f41-9569-2a208e79001d" />




**File share it-department exists with 5 GB quota**

Click on Data storage>> File shares

Click on **+File share**

<img width="987" height="619" alt="Screenshot 2026-04-16 231938" src="https://github.com/user-attachments/assets/f8e33439-05fc-4ec2-8148-cdd1a50aa0b0" />




**Click on review to create**

<img width="802" height="532" alt="Screenshot 2026-04-16 232802" src="https://github.com/user-attachments/assets/01a982ff-3278-47a4-9de0-e73cedba5387" />


**To change the quota, click on the three (…) at the right hand corner of the screen
**
<img width="1235" height="586" alt="Screenshot 2026-04-17 212602" src="https://github.com/user-attachments/assets/0a8f72b7-f66b-42a9-a393-e5014b52bafb" />

