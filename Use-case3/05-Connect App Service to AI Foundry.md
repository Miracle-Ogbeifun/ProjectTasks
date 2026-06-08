**Connect App Service to AI Foundry**

What to do:

Get your AI Foundry endpoint URL and API key from the deployment in Task 2 (go to Deployments → your model → find the endpoint and key)

Add these as Application Settings (environment variables) in the App Service:

Setting Name	Value

AZURE_OPENAI_ENDPOINT	Your AI Foundry endpoint URL

AZURE_OPENAI_KEY	Your API key

AZURE_OPENAI_DEPLOYMENT	gpt-4o-mini

⚠️ Security: NEVER hardcode the API key in source code. Use App Settings or Key Vault references.

<br><br>

**Acceptance Criteria:**

App Settings contain the 3 environment variables (key value hidden in Portal)

<img width="1311" height="553" alt="Screenshot 2026-06-03 104054" src="https://github.com/user-attachments/assets/f19e7666-c393-4a89-b37d-791b14282f74" />

<br><br>

API key is NOT visible in any source code file

<img width="1332" height="512" alt="Screenshot 2026-06-03 104424" src="https://github.com/user-attachments/assets/fce7fc41-7119-4382-b419-94d283f5f128" />

<br><br>

(If backend deployed) Chat UI successfully queries the AI model and returns responses

<img width="1037" height="666" alt="Screenshot 2026-06-03 110722" src="https://github.com/user-attachments/assets/9a5ef137-ede8-48db-9518-09c7a00c9071" />

<br><br>

**Get your AI Foundry endpoint URL and API key from the deployment in Task 2 (go to Deployments → your model → find the endpoint and key)**

<img width="975" height="615" alt="Screenshot 2026-06-03 103613" src="https://github.com/user-attachments/assets/586c5d5b-5c5e-4a15-b1f7-23db1e47f535" />

<br><br>

**Add these as Application Settings (environment variables) in the App Service:
**
Setting Name	Value
AZURE_OPENAI_ENDPOINT	Your AI Foundry endpoint URL
AZURE_OPENAI_KEY	Your API key
AZURE_OPENAI_DEPLOYMENT	gpt-4o-mini

<br><br>

**In Azure AI Foundry portal:**

Open the AI Foundry Project.

Go to My Assets →Models + endpoints.

Select your GPT-4o Mini deployment.

Look for Endpoint

<img width="1311" height="553" alt="Screenshot 2026-06-03 104054" src="https://github.com/user-attachments/assets/4d300590-b010-4b30-ab25-5ad6002c588d" />

<br><br>

**Add Environment Variables to App Service**

In Azure Portal:

Open the App Service (app-novatech-{id}-support)

Go to:
Settings → Environment variables

Click + Add for each setting.

Add the following values separately:

Name	Value

AZURE_OPENAI_ENDPOINT	Your AI Foundry endpoint URL

AZURE_OPENAI_KEY	Your API key

AZURE_OPENAI_DEPLOYMENT	Your deployment name

<img width="1039" height="590" alt="Screenshot 2026-06-03 104254" src="https://github.com/user-attachments/assets/292657b7-0edb-4c16-8cea-9850e0821a5c" />


**After adding all three settings value:**

Click Apply or Save.

Azure will usually prompt: Restart application?

Click Continue or manually click Restart.

<br><br>

**Test the Chat:**

Open your web app and send a message

<img width="1037" height="666" alt="Screenshot 2026-06-03 110722" src="https://github.com/user-attachments/assets/f276ded8-616c-41e2-a00d-b37bdf65ae2e" />
