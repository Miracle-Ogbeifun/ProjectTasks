**Deploy Azure App Service**

What to do:

Create an App Service Plan: asp-novatech-{id}-support (Free F1 or Basic B1 tier)

Create a Web App: app-novatech-{id}-support

Runtime: Node.js 20 LTS (or Python 3.11)

Deploy a simple chat UI. Use this minimal HTML file as index.html

<br><br>

**Acceptance Criteria:**

App Service is running and accessible via its URL (https://app-novatech-{id}-support.azurewebsites.net)

The chat UI loads in the browser

App Service shows "Running" status in the Portal

<img width="1332" height="517" alt="Screenshot 2026-06-03 102850" src="https://github.com/user-attachments/assets/04cf6d0f-c040-4434-89ea-c68dd5a9fe92" />

<br><br>

<img width="1037" height="666" alt="Screenshot 2026-06-03 110722" src="https://github.com/user-attachments/assets/6c012f8c-9670-44e7-afa3-b1b01fa94c7d" />

<br><br>

Create an App Service Plan: asp-novatech-{id}-support (Free F1 or Basic B1 tier)

In Azure Portal:

Search App Services → + Create


<img width="736" height="559" alt="Screenshot 2026-06-03 054318" src="https://github.com/user-attachments/assets/fd20a796-038a-4859-ab1b-0ac46b53bbf0" />

<br><br>

<img width="796" height="566" alt="Screenshot 2026-06-03 054331" src="https://github.com/user-attachments/assets/82fec972-8de7-4036-840a-cd6f03c51427" />

<br><br>

<img width="608" height="569" alt="Screenshot 2026-06-03 081942" src="https://github.com/user-attachments/assets/8e550fe3-5c65-4f2f-9f4b-e6b088a0fa96" />

<br><br>

Basics tab:

Resource Group: rg-novatech-{id}-ai-eastus

Name: app-novatech-{id}-support

Publish: Code

Operating System: Linux

Region: East US

Pricing Plan: Free F1

Click Review + Create → Create

<img width="1041" height="580" alt="Screenshot 2026-06-03 063509" src="https://github.com/user-attachments/assets/7d05756e-4d63-4c9f-b933-736c84cd09c3" />

<br><br>


**2. Create a Web App: app-novatech-{id}-support**
   
Runtime: Node.js 20 LTS (or Python 3.11)

Search Web App → + Create

<img width="843" height="551" alt="Screenshot 2026-06-03 064139" src="https://github.com/user-attachments/assets/c4fff583-5f83-4f8c-a648-981dd30f870b" />

<br><br>

<img width="787" height="548" alt="Screenshot 2026-06-03 064154" src="https://github.com/user-attachments/assets/1bf2f598-ab88-40bc-b2fc-001d9f6b718b" />

<br><br>

<img width="817" height="593" alt="Screenshot 2026-06-03 064221" src="https://github.com/user-attachments/assets/e0f87f9f-495c-40c0-b344-4931ba066569" />

<br><br>

<img width="1032" height="513" alt="Screenshot 2026-06-03 064422" src="https://github.com/user-attachments/assets/1fdf6ab3-64f7-4c2b-a94d-60d09657f52d" />


<br><br>

After deployment:

Go to your Web App
Click:
Deployment tool → Advanced Tools (Kudu) → Go

<img width="678" height="545" alt="Screenshot 2026-06-03 065002" src="https://github.com/user-attachments/assets/cfe00656-a8c1-4054-9879-ccbde957cd5b" />

**On the Kudu portal **

Click on SSH → SSH to Application

In SSH terminal:
Run: cd /home/site/wwwroot

Create file:

Run: touch index.html

Create server.js in SSH terminal

Create package.json in SSH terminal

<img width="990" height="510" alt="Screenshot 2026-06-03 102720" src="https://github.com/user-attachments/assets/158f34aa-1b05-4ce2-a81a-bd6b6357c015" />

Then open the File Manager in KUDU and paste your chat UI HTML.

Run npm install in the SSH console

<br><br>

**After creating files:**

Go to Azure Portal → app service created

Set: npm install && npm start
In the Startup Command under the stack settings 

Click Save.

<br><br>

Restart the App Service from the Overview page

Test by clicking on the URL

<img width="1332" height="517" alt="Screenshot 2026-06-03 102850" src="https://github.com/user-attachments/assets/9f32db5a-f4bb-4a76-9052-e832a0c5bae9" />

<br><br>

<img width="1048" height="680" alt="Screenshot 2026-06-03 102645" src="https://github.com/user-attachments/assets/62540a51-4e1c-41ea-adf5-575b883f25b4" />

