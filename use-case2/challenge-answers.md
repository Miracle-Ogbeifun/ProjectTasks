
# Challenge Answers

## 1. Scenario: Using Public IPs Instead of VNet Peering

Using public IP addresses on both VMs and communicating over the internet introduces several security and performance risks.

### Security Risks

* Increased attack surface because the VMs are exposed to the public internet.
* Greater risk of unauthorized access attempts, brute-force attacks, and vulnerability scanning.
* Data transmitted between VMs could be intercepted if encryption is not properly configured.
* Additional firewall and Network Security Group (NSG) rules are required to secure the communication.

### Performance Risks

* Higher network latency because traffic travels over public internet routes.
* Less predictable performance compared to Azure's private backbone network.
* Increased dependency on internet connectivity and routing conditions.

### Recommended Alternative

For hybrid connectivity between Azure and on-premises environments, alternatives to VNet Peering include:

* Site-to-Site VPN Gateway
* Azure ExpressRoute

A VPN Gateway provides encrypted communication over the internet, while ExpressRoute provides a dedicated private connection with higher reliability, lower latency, and improved security.

<br><br>

## 2. Scenario: Automatic Scaling for the Web Application

Instead of manually adding virtual machines, I would recommend using Azure Virtual Machine Scale Sets (VMSS).

### Why VMSS?

Virtual Machine Scale Sets allow Azure to automatically increase or decrease the number of VM instances based on demand while integrating with Azure Load Balancer.

### Example Autoscale Rules

* Scale out when average CPU utilization exceeds 70% for 10 minutes.
* Add 1 or more VM instances automatically.
* Scale in when CPU utilization falls below 30% for 15 minutes.
* Remove unnecessary VM instances to reduce costs.

This approach ensures high availability, better performance during peak traffic periods, and optimized costs during low-demand periods.

<br><br>

## 3. Scenario: Database Connection String Stored in GitHub

Storing connection strings directly in application code is a security risk because anyone with access to the repository may obtain sensitive credentials.

### How Azure Key Vault Prevents This

1. The secret is stored securely in Azure Key Vault.
2. The application authenticates using a Managed Identity or service principal.
3. The application requests the secret from Key Vault.
4. Key Vault verifies permissions using Azure RBAC.
5. Key Vault returns the secret securely.
6. The application uses the secret at runtime without storing it in source code.

### Flow

Application → Managed Identity Authentication → Azure Key Vault → Secret Retrieval → Application Uses Secret

Benefits include:

* No secrets stored in source code.
* Centralized secret management.
* Easier secret rotation.
* Improved auditing and access control.

<br><br>

## 4. Scenario: Proving No Unauthorized Traffic Reached the DataSubnet

The primary Azure feature used to provide this evidence is Network Security Group (NSG) Flow Logs.

### Information Provided by NSG Flow Logs

* Source IP addresses
* Destination IP addresses
* Ports and protocols used
* Allowed or denied traffic
* Timestamps of network activity

### Analysis Tools

I would use:

* Log Analytics Workspace
* Azure Monitor Logs
* Kusto Query Language (KQL)

These tools allow security teams to search historical traffic records, identify suspicious connections, and verify whether unauthorized traffic attempted to access the DataSubnet during the previous 30 days.

<br><br>

## 5. Scenario: ACI vs AKS

Azure Container Instances (ACI) is a good choice for small, simple workloads that require minimal management.

### When ACI Becomes the Wrong Choice

ACI may not be suitable when:

* Multiple containerized services must work together.
* Automatic scaling is required.
* High availability across multiple nodes is needed.
* Complex networking and service discovery are required.
* Rolling updates and advanced deployment strategies are needed.
* Container orchestration is required.

### When AKS Is the Right Choice

Azure Kubernetes Service (AKS) is recommended when:

* Running large-scale microservices applications.
* Managing many containers across multiple hosts.
* Implementing automated scaling and self-healing.
* Supporting CI/CD pipelines and DevOps practices.
* Requiring enterprise-grade orchestration and monitoring.

<br><br>

### Conclusion

ACI is ideal for lightweight applications, development environments, testing, and short-lived workloads. AKS is the better choice for production-grade, scalable, highly available containerized applications that require orchestration and automated management.
