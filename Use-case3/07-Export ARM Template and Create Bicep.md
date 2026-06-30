# **Export ARM Template and Create Bicep**



What to do:


Go to your resource group → Export template (in the left menu)

Download the ARM template JSON

Open it in VS Code — observe the structure (parameters, variables, resources, outputs)

Create a simplified Bicep file for just the App Service resource:

<br><br>

## **Acceptance Criteria:**

ARM template JSON is downloaded and saved in your GitHub repo

<img width="717" height="694" alt="Screenshot 2026-06-08 210204" src="https://github.com/user-attachments/assets/880f889b-44d9-4de0-bf3d-a099bde9d96e" />

<br><br>

**Bicep file is created and saved in your GitHub repo**

<img width="1145" height="677" alt="Screenshot 2026-06-03 131641" src="https://github.com/user-attachments/assets/50ee9e49-4830-4f78-b49c-78d3f7136079" />

<br><br>

**You can explain the difference between ARM JSON and Bicep syntax**

ARM is hard to read while Bicep is clean and readable

<br><br>

**(Bonus) Bicep deployment succeeds**

<img width="1330" height="600" alt="Screenshot 2026-06-03 131537" src="https://github.com/user-attachments/assets/13cef7ab-aac4-430e-aefd-72492bff0ffd" />


<br><br>


## **Export ARM Template (Portal)**

Go to Resource Group

rg-novatech-{id}-ai-eastus
Click on Export template (left menu)
Click on Download

You’ll get a .zip file containing:

template.json (this is the ARM template)

parameters.json

<img width="1144" height="583" alt="Screenshot 2026-06-03 125445" src="https://github.com/user-attachments/assets/815c011d-3586-4eb7-ba90-f1c1d40744e0" />

<br><br>

Open template.json in VS Code


<img width="717" height="694" alt="Screenshot 2026-06-08 210204" src="https://github.com/user-attachments/assets/ffd4fe50-abb1-4e4b-813b-6bf8546283df" />

<br><br>

**Create Bicep file in VS Code**

Open Visual Studio Code on your computer.

Create a new file:

File → New File

Save it as a Bicep file

Click File → Save As

Then name it: app-service.bicep

Paste your code


<img width="1145" height="677" alt="Screenshot 2026-06-03 131641" src="https://github.com/user-attachments/assets/daa537e0-0814-454b-ae18-556f4ecb8255" />

<br><br>

**Deploy it (after file is created)**

Run in the Azure portal:

az deployment group create \
  --resource-group rg-novatech-{id}-ai-eastus \
  --template-file app-service.bicep


<img width="1330" height="600" alt="Screenshot 2026-06-03 131537" src="https://github.com/user-attachments/assets/993281da-3874-4090-bdd0-74af8f2997f1" />

<br><br>

<img width="1351" height="601" alt="Screenshot 2026-06-03 131548" src="https://github.com/user-attachments/assets/a39bdcde-bbd5-4b79-970b-b4715e50c7bf" />

