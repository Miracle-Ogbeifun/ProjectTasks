
Create Azure Budget

**Acceptance Criteria:**

Budget exists with $30 limit

<img width="831" height="592" alt="Screenshot 2026-06-13 145719" src="https://github.com/user-attachments/assets/909069c3-e08e-4ced-8d9c-94e422843d30" />


Three alert thresholds are configured (50%, 80%, 100%)

<img width="774" height="602" alt="Screenshot 2026-06-13 145554" src="https://github.com/user-attachments/assets/520db718-1133-414e-9e00-f69bb3ab2de2" />


Your email is set as the notification recipient

<img width="947" height="568" alt="Screenshot 2026-06-13 145756" src="https://github.com/user-attachments/assets/07b0d602-4be7-46a3-b59f-fd14bea5ee00" />

**To Create Azure Budget**

Open Cost Management
In Azure Portal, search for:
Cost Management + Billing

<img width="750" height="356" alt="Screenshot 2026-06-13 144510" src="https://github.com/user-attachments/assets/7ce06e39-db2a-491c-ac5e-47c49242be1f" />

Open it.
Navigate to Budgets

On the left menu, select:

Cost Management → Budgets

Click:+ Add

<img width="954" height="542" alt="Screenshot 2026-06-13 144549" src="https://github.com/user-attachments/assets/70d0d603-6cd0-464a-8a37-fd07f7bb09bc" />


Configure Budget Basics

Fill in:

Name	budget-novatech-{id}
Reset period	Monthly
Budget amount	30
Budget unit	USD ($)
Start date	Current month
Expiration date	Optional / No expiration

<img width="785" height="578" alt="Screenshot 2026-06-13 144900" src="https://github.com/user-attachments/assets/002094e6-a325-47cd-b0c4-eeca7df1bbf8" />

Click Next.


Configure Alert 1 (50%)

Click Add alert condition.

Configure:

Alert type:	Actual coast
% of budget:50
Contact emails	Your email address

Configure Alert 2 (80%)

Click Add alert condition again.

Alert type:	Actual cost
% of budget:80


Configure Alert 3 (100%)

Alert type:	Actual cost
% of budget:100
Contact emails	Your email address

<img width="774" height="602" alt="Screenshot 2026-06-13 145554" src="https://github.com/user-attachments/assets/44a756d5-af82-4373-815a-45ff64ded92a" />


This means:

50% of $30 = $15
80% of $30 = $24
100% of $30 = $30

Azure automatically calculates the amount from the percentage.

Click on review and Save.



**Verify the Budget**

Go back to: Cost Management → Budgets

Open: budget-novatech-mo

Confirm:
Budget
Amount = $30
Period = Monthly

<img width="831" height="592" alt="Screenshot 2026-06-13 145719" src="https://github.com/user-attachments/assets/42d7c8ba-0e15-4922-8864-b87e874a1994" />


Notifications
50% threshold
80% threshold
100% threshold

Recipient
Your email address

<img width="947" height="568" alt="Screenshot 2026-06-13 145756" src="https://github.com/user-attachments/assets/90b2ef39-f083-45da-85d7-d96a3f8fc83f" />


