# **Azure Monitor Dashboard**

## **Acceptance Criteria:**


Diagnostic settings are enabled on at least one resource

<img width="1327" height="565" alt="Screenshot 2026-06-03 152821" src="https://github.com/user-attachments/assets/c495c304-fb23-44d8-8107-91cd843a19ec" />

<br><br>

Dashboard exists with at least 2 metric tiles

<img width="1344" height="583" alt="Screenshot 2026-06-03 161407" src="https://github.com/user-attachments/assets/64e273f5-799e-4c30-ab63-25df4ff92188" />


Metrics show data (even if minimal — a few test requests count)

<br><br>

## **Enable Diagnostic Settings (AI Foundry / OpenAI)**

Find the Azure OpenAI resource from AI Foundry

Open your AI Foundry project.

Go to Management Center.

Look for Connected resources → Resources

<img width="1261" height="601" alt="Screenshot 2026-06-03 152042" src="https://github.com/user-attachments/assets/01f7d823-f405-488f-b86a-1c99d3ca48c5" />

<br><br>

Find the Azure OpenAI resource associated with your project.

Click Open in Azure Portal.

<img width="961" height="563" alt="Screenshot 2026-06-03 152120" src="https://github.com/user-attachments/assets/c280ea02-87bd-47a8-9e33-c209747a8056" />

<br><br>

Left menu:

Monitoring → Diagnostic settings

Click on + Add diagnostic setting

Configure it and Fill in:

Name: openai-logs

Categories:

RequestResponse

Audit

destination details: Send to Log Analytics workspace

If none exists:

Click Create new workspace


<img width="1107" height="549" alt="Screenshot 2026-06-03 152616" src="https://github.com/user-attachments/assets/96a313a4-4073-47e2-ad6b-77de1fec8626" />

<br><br>

Click Save

<img width="1327" height="565" alt="Screenshot 2026-06-03 152821" src="https://github.com/user-attachments/assets/91c726c8-2b26-42bd-9986-f8f7f55ee842" />

<br><br>

**Create an Azure Monitor Dashboard:**

Add tiles for: API request count, average latency, error rate (HTTP 4xx/5xx)

(If App Service deployed) Add: App Service response time, HTTP server errors



Open your App Service (app-novatech-...-support).

In the left menu, look for: Monitoring → Metrics

Open Metrics.

Create a chart for Requests. select private

Click Pin to dashboard.


<img width="1017" height="558" alt="Screenshot 2026-06-03 160742" src="https://github.com/user-attachments/assets/f3cc85a7-cb71-42df-b39e-bd34e89639da" />


Create a second chart for Average Response Time (or Http Server Errors).

Click Pin to dashboard again.

Then go back to Dashboard and you should see both tiles.


<img width="1344" height="583" alt="Screenshot 2026-06-03 161407" src="https://github.com/user-attachments/assets/4fefda6d-73a0-4287-9593-98915fc5f204" />
