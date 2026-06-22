
<img width="1286" height="560" alt="Screenshot 2026-06-13 151017" src="https://github.com/user-attachments/assets/9590047a-c8a1-4ab3-bc72-7f468fb0773f" />

<br><br>

<img width="1105" height="563" alt="Screenshot 2026-06-13 151125" src="https://github.com/user-attachments/assets/86fd8cf4-e72d-45ec-9324-048c034ce461" />

<br><br>

# Azure Infrastructure Review

## 1. Compare Azure Advisor security scores between East US and West Europe resource groups. Why might they differ?

The Azure Advisor security scores for the East US and West Europe resource groups may differ because the resources deployed in each region are different. Azure Advisor evaluates security recommendations based on the specific services, configurations, and security controls applied to resources within a resource group.

For example, one resource group may contain virtual machines with monitoring and diagnostic settings enabled, while another may have fewer security controls configured. Differences in Network Security Groups (NSGs), Azure Monitor settings, Key Vault configuration, identity settings, and exposed public endpoints can all affect the security score.

Therefore, even though both resource groups belong to the same environment, their security scores may vary because Azure Advisor evaluates each resource group independently based on its security posture.

## 2. Are your Load Balancer health probes using HTTP or HTTPS? Which is more secure and why? What's the trade-off?

The Load Balancer health probes in this lab use HTTP.

HTTPS is more secure because it encrypts communication between the client and the server using TLS, protecting data from interception and tampering. HTTPS also provides certificate validation, helping verify the identity of the endpoint.

The trade-off is that HTTPS requires certificate management and introduces slightly more processing overhead compared to HTTP. HTTP health probes are simpler to configure and are commonly used in lab environments, but HTTPS is recommended for production environments where security is a priority.

## 3. Is your Key Vault using RBAC or access policies for permission management? Which does Microsoft recommend for new deployments and why?

The Key Vault in this lab is using Azure RBAC because a role assignment was required before the secret could be created and accessed.

Microsoft recommends Azure RBAC for new deployments because it provides centralized access management through Azure role assignments. RBAC offers better integration with Azure governance, supports the principle of least privilege, provides more granular permissions, and simplifies auditing and access reviews across Azure resources.

Access Policies are still supported but are considered a legacy access model compared to Azure RBAC.

## 4. Are NSG flow logs enabled on your VNets? Why are flow logs important for security incident investigation?

Yes, NSG flow logs were enabled as part of the monitoring and diagnostic configuration.

NSG flow logs record information about allowed and denied network traffic flowing through Network Security Groups. These logs are important during security investigations because they help identify:

* Suspicious inbound or outbound connections
* Unauthorized access attempts
* Communication between compromised systems
* Sources and destinations of network traffic
* Potential data exfiltration activity

Flow logs provide valuable forensic evidence and improve visibility into network activity.

## 5. Your ACI container uses the nginx:latest image from Docker Hub. Is this a trusted source? What risks does using public container images introduce? What would you do differently in production?

The nginx image is widely used and maintained by the NGINX project, making it a generally trusted public image. However, using public container images still introduces risks.

Potential risks include:

* Vulnerabilities in the image or included packages
* Supply chain attacks
* Unverified image integrity
* Unexpected changes when using the latest tag
* Lack of organizational control over image updates

In production, I would:

* Use a private Azure Container Registry (ACR)
* Scan container images for vulnerabilities
* Pin specific image versions instead of using the latest tag
* Apply image signing and verification controls
* Use approved and tested container images only

For example, I would use a specific version such as nginx:1.31.1 rather than nginx:latest.

## 6. What Azure Advisor cost recommendations appear for your multi-region setup? Would you implement them?

Azure Advisor may recommend:

* Shutting down or resizing underutilized virtual machines
* Removing unused public IP addresses
* Removing unattached disks
* Purchasing reserved instances for predictable workloads
* Optimizing resource sizing based on utilization patterns

Whether I would implement the recommendations depends on the business requirements.

For a production multi-region architecture designed for high availability and disaster recovery, I would not automatically remove resources that appear underutilized because they may be intentionally deployed for redundancy.

However, I would carefully review recommendations related to unused resources, oversized virtual machines, and idle services to reduce unnecessary costs while maintaining availability and performance requirements.
