
Create Azure Monitor Alerts

**Acceptance Criteria:**

Action group exists with your email configured

<img width="1246" height="334" alt="Screenshot 2026-06-13 133910" src="https://github.com/user-attachments/assets/5959b046-227b-4f48-81dc-344f18507e9f" />

Both alert rules exist and are enabled

<img width="1282" height="440" alt="Screenshot 2026-06-13 143217" src="https://github.com/user-attachments/assets/d8da45b0-e5f6-448d-b3ea-9cffdae01207" />


Alert conditions reference the correct VMs and thresholds



Create the Action Group

In Azure Portal, search for Monitor.
Open Monitor.
Under Alerts, select Action groups.
Click + Create.

<img width="1100" height="429" alt="image" src="https://github.com/user-attachments/assets/a43e7991-0c1a-41aa-8b87-d70e357cdd1d" />

Basics Tab Setting	Value
Subscription	
Resource Group	
Region	Global
Action Group Name	ag-novatech-{id}-email
Display Name	NovaTechEmail

<img width="831" height="596" alt="Screenshot 2026-06-13 133121" src="https://github.com/user-attachments/assets/db5b565a-9e5b-4992-984f-68019ee90d97" />


Click Next: Notifications.

Notifications Tab
Click + Add notification.

Configure:

Notification type	Email/SMS message/Push/Voice
Name	EmailNotification
Email	Your email address

Click OK.

<img width="960" height="583" alt="Screenshot 2026-06-13 133651" src="https://github.com/user-attachments/assets/cb73baea-f4e7-4cc9-a290-015c53408fdd" />


Click Review + Create.

<img width="762" height="581" alt="Screenshot 2026-06-13 133739" src="https://github.com/user-attachments/assets/2637e46d-0ff9-4179-b880-66ee6dace388" />


Click Create.


Verify

Go to: Monitor → Alerts → Action Groups

Confirm: ag-novatech-{id}-email exists.

<img width="1246" height="334" alt="Screenshot 2026-06-13 133910" src="https://github.com/user-attachments/assets/716ac7cd-bedf-4813-a1df-2fedd592d398" />



**Create High CPU Alert**

Open Alerts
Go to Monitor.
Select Alerts.

<img width="1090" height="355" alt="Screenshot 2026-06-13 134036" src="https://github.com/user-attachments/assets/04de36de-9f67-44ab-a0da-5f05ff02bd4b" />


Click + Create → Alert rule.

<img width="723" height="407" alt="Screenshot 2026-06-13 134241" src="https://github.com/user-attachments/assets/a3fce80f-0551-4184-8a7c-0807cc1a3196" />

Scope

Select the VM you want to monitor.

If the lab has two VMs, repeat these alert steps for each VM if required.

<img width="759" height="589" alt="Screenshot 2026-06-13 134824" src="https://github.com/user-attachments/assets/d8f7f76f-0617-415c-b937-4742587c7679" />


Condition

Click Add condition.

Search for:

Percentage CPU

Select:

Percentage CPU

Configure:

Setting	Value
Threshold	Static
Operator	Greater than
Aggregation	Average
Threshold value	80
Check every	1 minute
Lookback period	5 minutes

<img width="775" height="575" alt="Screenshot 2026-06-13 134815" src="https://github.com/user-attachments/assets/53f656e3-1756-4077-bf00-7c941cb7bf5d" />


This effectively means: CPU > 80% for 5 minutes

Click Done and Click Next.


Actions

Click: Select action groups

Choose: ag-novatech-{id}-email

<img width="1034" height="579" alt="Screenshot 2026-06-13 135207" src="https://github.com/user-attachments/assets/370eccf6-e19d-4489-befb-e1475f50fa34" />

Click Apply.


**Details**

Configure: Setting	Value

Alert Rule Name	High CPU
Severity	2 (Warning)

<img width="723" height="590" alt="Screenshot 2026-06-13 135140" src="https://github.com/user-attachments/assets/7520aff8-a5d6-419d-99e8-b37a8e49b19a" />

Click Review + Create.

<img width="857" height="593" alt="Screenshot 2026-06-13 135234" src="https://github.com/user-attachments/assets/573aedba-e2a9-4d7f-998c-7978a8fbf42d" />

Click Create.


**Create High Disk Alert**

**Create Another Alert Rule Again:**

Monitor → Alerts → Create → Alert Rule

<img width="1352" height="421" alt="Screenshot 2026-06-13 135316" src="https://github.com/user-attachments/assets/1c1aa4e2-8180-490d-8e42-5f82374e00f4" />

Scope

Select the same VM


**Click Add condition.**

Search for:

Disk

Depending on your VM and monitoring configuration, I choose Disk Write Operation/Sec because none of the below option was available:

OS Disk Used Percentage
Disk Used Percentage
Logical Disk % Used Space

Selected the closest matching metric.

Configure:

Setting	Value
Operator	Greater than
Threshold value	90
Aggregation	Average
Lookback period	5 minutes

<img width="741" height="591" alt="Screenshot 2026-06-13 142905" src="https://github.com/user-attachments/assets/0fbb2b28-8979-4a15-855b-9df8cb827019" />

Click Done.

**Actions**

Select: ag-novatech-{id}-email


**Details**

Alert Rule Name:	High Disk
Severity	2

<img width="664" height="580" alt="Screenshot 2026-06-13 142956" src="https://github.com/user-attachments/assets/e7785808-fea7-492b-9362-b3c3dfe54ea5" />


Click Review + Create.

Click Create.


**Verify Both Alerts**

Go to: Monitor → Alerts → Alert Rules

You should see:

High CPU
High Disk

Status should be: Enabled

<img width="1282" height="440" alt="Screenshot 2026-06-13 143217" src="https://github.com/user-attachments/assets/4b32f5b7-f350-4ecb-9f8c-7170e37ff1a1" />



