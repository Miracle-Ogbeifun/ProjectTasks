**Task 7: 🔒 Security Review**


What to do:


Navigate to Azure Advisor in the portal (search "Advisor" in the top search bar)

Review recommendations across all categories: Security, Reliability, Cost, Performance, Operational Excellence

**Take a screenshot of the recommendations page**


<img width="1083" height="623" alt="Screenshot 2026-04-17 220400" src="https://github.com/user-attachments/assets/1727f0a2-0b26-4f5e-b728-5f2040235170" />


<img width="1102" height="644" alt="Screenshot 2026-04-17 220418" src="https://github.com/user-attachments/assets/f8050f1c-aa56-4fdb-9f57-dfea6016e00a" />



<img width="1099" height="638" alt="Screenshot 2026-04-17 220432" src="https://github.com/user-attachments/assets/551f09a9-5b46-4515-aeb2-d11850d67308" />








**Answer the following questions in your thought-process.md file:**

1.	Why is the DataSubnet NSG configured to deny all internet traffic? What types of resources would go in this subnet and why shouldn't they be internet-accessible?

Answer: The DataSubnet NSG denies internet traffic to protect sensitive, backend resources that should never be exposed publicly.
The resources should only be accessed internally, not by the public internet.



2.	What would happen if the Storage Account allowed public blob access instead of private? Describe a real-world scenario where this could cause a data breach.

Answer: If a Storage Account allows public blob access, anyone on the internet can read the data in those containers. That turns the storage from “locked down” into something closer to a public website.
Allowing public blob access exposes stored data to anyone on the internet. In a real-world scenario, this could lead to unauthorized access to sensitive files such as database backups or employee records, resulting in a serious data breach, financial loss, and reputational damage. Keeping blob containers private ensures that only authorized users and services can access the data.


3.	What is your Azure Advisor score? What specific improvements does it suggest? Would you implement all of them — why or why not?

Answer: From the Azure Advisor dashboard, my scores are as follows:

- Reliability: 86%
- Security: 26%
- Operational Excellence: 100%
- Cost: 100%
- Performance: 100%
The overall observation is that while cost, performance, and operational excellence are well optimized, security has a very low score and reliability needs improvement.
Recommendations

Azure Advisor suggests several improvements:

- 19 active security recommendations affecting 5 resources
- 8 reliability recommendations affecting 9 resources
- 1 operational excellence recommendation affecting 3 resources

The key areas needing attention are:

Security:
- Improve security configurations (likely NSGs, public access, or missing protections)
- Apply security best practices to reduce vulnerabilities

Reliability:
- Enable backups for resources
- Improve fault tolerance and availability configurations

Operational Excellence:
- Minor improvements related to resource management or monitoring

Would I implement all recommendations?

I would not implement all recommendations automatically. Instead, I would evaluate them based on necessity and impact.

For example:
- Security recommendations should be prioritized and mostly implemented because they protect against threats and data breaches.
- Reliability improvements such as backups are important and should be implemented to prevent data loss.
- Cost and performance recommendations may not always be necessary if the current setup already meets requirements.
- Some recommendations might increase cost or complexity without significant benefit, especially in a test or development environment.

Therefore, I would implement critical security and reliability recommendations first, while carefully reviewing others based on business needs and cost implications.



4.	Your VM currently has a public IP and SSH (port 22) open. In a production environment, what would you do differently?


Answer: In a production environment, leaving a VM with a public IP and port 22 (SSH) open to the internet is not considered secure. It increases the attack surface and exposes the VM to unauthorized access.
In a production environment, I would not expose a virtual machine directly to the internet with a public IP and open SSH port. Instead, I would place the VM in a private subnet without a public IP. If SSH access is required, I would restrict it to specific trusted IP addresses using NSG rules and enforce SSH key-based authentication. These measures reduce the attack surface and protect the VM from unauthorized access and brute-force attacks.


5.	You chose LRS for the Storage Account. A manager asks: "What happens if the entire datacenter goes down?" How do you respond?

Answer: LRS is more cost-effective and sufficient for non-critical or test workloads, but it does not provide protection against datacenter-level failures.

If the entire datacenter goes down (for example, due to a power outage, natural disaster, or major network failure), the data would become unavailable because all replicas are stored in that same location.

To handle this risk in a production environment, a higher redundancy option such as Zone-Redundant Storage (ZRS) or Geo-Redundant Storage (GRS) would be used. These options replicate data across multiple availability zones or regions, ensuring continued availability even if one datacenter fails.


