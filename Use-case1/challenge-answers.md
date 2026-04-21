
## **Challenge Questions**

Answer these in your challenge-answers.md file. These are AZ-104 and AZ-305 exam-style scenario questions.

**1.Scenario:** NovaTech's CTO asks you to ensure the web server is accessible from the internet but the database server (in DataSubnet) should never be directly reachable. A new developer accidentally creates a VM in DataSubnet with a public IP. What Azure feature would prevent this from happening again? (Hint: Think beyond NSGs)

**Answer:** NSGs can control traffic, but they won’t stop someone from creating a VM with a public IP in the first place.
The solution is to create Azure Policy. Azure Policy lets you enforce rules at the platform level so that bad configurations are blocked before they happen.

**2.Scenario:** The CFO is concerned about the cost of running all infrastructure in a single region. They ask: "What happens to our web server if the East US region goes completely offline?" How would you design for this? What Azure services would you recommend?

**Answer:** Running all infrastructure in a single region (e.g., East US) creates a single point of failure. If the region goes offline, the web application becomes completely unavailable.

To address this, a **multi-region architecture** should be implemented:

- Deploy workloads in at least two regions (Primary and Secondary)
- Enable Geo-Redundant Storage (GRS) for data durability
- Configure health checks for automatic failover

For cost optimization, adopt an **active-passive setup**, where the secondary region runs at lower capacity and scales only during failover.
This approach ensures **high availability, fault tolerance, and business continuity** while balancing cost.


**3.Scenario:** An auditor asks you: "How do you know who created or modified resources in your Azure environment?" Which Azure service provides this audit trail, and where would you find it?

**Answer:** Resource creation and modification in Azure are tracked using the **Azure Activity Log**.

- It provides an audit trail of **who performed an action, what was done, and when it occurred**
- Logs include operations such as create, update, and delete
For extended retention and deeper analysis, logs can be integrated with Azure Monitor Logs / Log Analytics.
This ensures **accountability, traceability, and compliance** within the Azure environment.

**4.Scenario:** NovaTech's storage account currently uses LRS. The company handles customer financial data. The compliance team requires data to survive a complete datacenter failure. What would you change, and what are the cost implications?

**Answer:** The current use of Locally Redundant Storage (LRS) does not meet compliance requirements, as it only replicates data within a single datacenter and cannot withstand a full datacenter failure.

To ensure durability and compliance, the storage account should be upgraded to:

- **Geo-Redundant Storage (GRS)** or  
- **Read-Access Geo-Redundant Storage (RA-GRS)**

### Benefits:
- Replicates data to a secondary region
- Protects against complete datacenter or regional failures
- Ensures high durability for sensitive financial data

### Cost Implications:
- Higher cost compared to LRS due to cross-region replication
- Increased storage and data transfer charges
- RA-GRS is more expensive than GRS due to read access in the secondary region
This change improves **data resilience, compliance, and business continuity**, with a trade-off of increased storage costs.

**5.Scenario:** You need to give a contractor temporary access to upload files to the blob container without giving them full Storage Account keys. What Azure feature allows this?

**Answer:** Temporary access to upload files to a blob container can be granted using a **Shared Access Signature (SAS)**.

- Provides **secure, time-limited access** without exposing storage account keys  
- Allows control over **permissions** (e.g., upload/write only)  
- Supports **expiry time** and optional IP restrictions  

This ensures **least-privilege access** while maintaining security and control over the storage account.
