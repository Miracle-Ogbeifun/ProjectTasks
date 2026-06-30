# **Deploy Azure Function (Webhook)**


## **Acceptance Criteria:**

Function App exists and shows "Running"

HTTP trigger function is accessible at its URL

Sending a test POST request returns a success response

(Bonus) Messages appear in the Storage Queue

<br><br>

Function App exists and shows "Running"

<img width="1019" height="529" alt="Screenshot 2026-06-03 112840" src="https://github.com/user-attachments/assets/90871646-481c-47b5-883d-ecaa5dd80ae0" />

<br><br>

Sending a test POST request returns a success response

<img width="1330" height="584" alt="Screenshot 2026-06-03 123503" src="https://github.com/user-attachments/assets/2ac140a2-8c05-42c0-afe4-a0185b056f20" />

<br><br>

(Bonus) Messages appear in the Storage Queue

<img width="1258" height="482" alt="Screenshot 2026-06-03 124932" src="https://github.com/user-attachments/assets/c897c443-84b0-46a6-9989-9c8403b85e49" />

<br><br>

## **Create the Function App**

In Azure Portal:

Search for Function App

Click + Create

<img width="705" height="413" alt="Screenshot 2026-06-03 111302" src="https://github.com/user-attachments/assets/d5e229ca-0255-49de-9d8d-40bf35d01da3" />

<br><br>

Name: func-novatech-{id}-webhook

Runtime: Node.js 20 or Python 3.11

Hosting plan: Consumption (Serverless) — free tier

Storage Account: Create new (auto-generated name is fine)


<img width="901" height="593" alt="Screenshot 2026-06-03 112529" src="https://github.com/user-attachments/assets/6a5e9e7a-2162-41b3-bf5d-d3564774d478" />


Review + Create


<img width="1019" height="529" alt="Screenshot 2026-06-03 112840" src="https://github.com/user-attachments/assets/70b9022c-712a-4aac-b1ac-c56974f952cf" />

<br><br>

**Create the HTTP Trigger Function**

After deployment:

Open the Function App.

Select Functions in the Overview setion from the left menu.

Select a Template. Click on HTTP Trigger and sellect Next


<img width="1045" height="608" alt="Screenshot 2026-06-03 122233" src="https://github.com/user-attachments/assets/d6343f2b-dc7e-4598-bc55-de3d3d8d757c" />

<br><br>

Setting	Value

Template:	HTTP Trigger

Function Name:	webhook

Authorization Level:	Function


<img width="1038" height="602" alt="Screenshot 2026-06-03 122138" src="https://github.com/user-attachments/assets/2e8cebbd-df99-4a2f-9070-08d1c3e4c4ac" />

Click + Create.

<br><br>

**After the function is created:**

Click the webhook function.

Look for Code + Test.

<br><br>

<img width="1310" height="590" alt="Screenshot 2026-06-03 122404" src="https://github.com/user-attachments/assets/b92d2977-e4c3-4987-8a74-ba48e0fcce9f" />

<br><br>

<img width="1339" height="578" alt="Screenshot 2026-06-03 122516" src="https://github.com/user-attachments/assets/0ff17175-56fc-4635-abcf-70bbdfd414c8" />


Replace the default code with with the provided code and click Save

<br><br>

**Add Queue Output Binding**

To add the Storage Queue output:

Go to Integration tab → + Add output


<img width="992" height="504" alt="Screenshot 2026-06-03 122759" src="https://github.com/user-attachments/assets/020a8a47-f3b6-465d-a5e5-7b4405e7ae2c" />


Binding type: Azure Queue Storage

Queue name: support-requests

Parameter name: supportQueue

Storage account connection: Select your storage account

<br><br>

<img width="1348" height="596" alt="Screenshot 2026-06-03 122945" src="https://github.com/user-attachments/assets/df07ecbc-7105-4a64-893b-1c928063c099" />

Click Add.


Click Test/Run → set Method: POST, Body: {"customerId": "CUST-001", "message": "Test"}

<img width="1333" height="578" alt="Screenshot 2026-06-03 123238" src="https://github.com/user-attachments/assets/24e82ad7-392c-4fc1-87f5-7ccd6de619d4" />

<br><br>

<img width="1340" height="603" alt="Screenshot 2026-06-03 123415" src="https://github.com/user-attachments/assets/d3ab5935-31ff-4683-996e-0d2798c6f2bb" />

<br><br>

<img width="1328" height="603" alt="Screenshot 2026-06-03 123428" src="https://github.com/user-attachments/assets/fe19645b-b65e-48b9-a3a2-bcdbc1d05908" />

<br><br>

Click Run — you should get a 200 response


<img width="1330" height="584" alt="Screenshot 2026-06-03 123503" src="https://github.com/user-attachments/assets/8585b0a7-5feb-4173-9a71-1cbac35f8473" />

