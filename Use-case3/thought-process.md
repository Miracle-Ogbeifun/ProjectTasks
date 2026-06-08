
**Run Azure Advisor on your AI resource group**

<img width="1299" height="528" alt="Screenshot 2026-06-03 161950" src="https://github.com/user-attachments/assets/88a92e70-7f5f-4a30-92cc-0673d8677c96" />


Answer the following in your thought-process.md:

<br><br>

**1. Is your App Service enforcing HTTPS-only? How do you verify this? Why does it matter?**


Yes, the App Service is enforcing HTTPS-only communication.


Verification


I verified this by navigating to:


App Service → Settings → Configuration → General Settings


and confirming that the HTTPS Only setting was enabled.


Why it Matters


HTTPS encrypts data exchanged between users and the application. This prevents attackers from intercepting sensitive information such as login credentials, customer data, and API requests. Enforcing HTTPS improves security, protects user privacy, and aligns with industry best practices.

<br><br>

**2. Are the AI Foundry API keys stored securely? Where are they stored? What would be the ideal approach using managed identity?**


Yes, the API keys are stored securely and are not hardcoded into the application source code.


Where They Are Stored


The keys are stored as Application Settings (environment variables) within the Azure App Service:


AZURE_OPENAI_ENDPOINT

AZURE_OPENAI_KEY

AZURE_OPENAI_DEPLOYMENT

Why This Is Secure


Application Settings keep sensitive information separate from the application code and prevent secrets from being exposed in source control repositories.


Ideal Approach Using Managed Identity


The ideal solution would be to use a Managed Identity assigned to the App Service. The managed identity would be granted access to the Azure AI resource, eliminating the need for API keys. This approach is more secure because Azure automatically manages authentication and there are no credentials to store, rotate, or expose.

<br><br>

**3. Does your AI Foundry resource have network restrictions? What's the risk of leaving it publicly accessible?**

At the time of deployment, no additional network restrictions were configured on the AI Foundry resource.

Risks of Public Accessibility

If the resource remains publicly accessible:


Unauthorized users could attempt to access the endpoint.

Stolen API keys could be misused.

Excessive requests could increase operational costs.

The service could become a target for malicious traffic and attacks.

Recommended Security Controls

To improve security, the following controls should be implemented:


Private Endpoints

Virtual Network integration

Firewall rules

Managed Identity authentication

Azure API Management

These controls help reduce exposure and restrict access to trusted systems only.

<br><br>

**4. Is your Function App using managed identity or key-based authentication? Which is more secure and why?**

The Function App is currently using key-based authentication.

Evidence

The HTTP-triggered function was created using Function-level authorization, which relies on function keys for authentication.

Which Is More Secure?

Managed Identity is more secure because:

No secrets need to be stored or shared.

Azure manages authentication automatically.

Access can be controlled through Azure RBAC.

There is no risk of exposed or leaked keys.

For production environments, Managed Identity is generally considered the best practice.

 <br><br>
 
**5. Review Microsoft Defender for Cloud — what is the Secure Score for your subscription? What are the top 3 recommendations?**

Secure Score

I reviewed Microsoft Defender for Cloud by navigating to:

Microsoft Defender for Cloud → Overview

The Secure Score for my subscription was:

[Insert your Secure Score here]

Top 3 Recommendations

The top recommendations shown were:

[Insert Recommendation #1]
[Insert Recommendation #2]
[Insert Recommendation #3]
Observation

Microsoft Defender for Cloud provides security posture management by identifying risks and recommending actions to improve the overall security of Azure resources.

<br><br>

**6. If a malicious user sent 1 million API requests to your AI endpoint, what would happen? What Azure service could prevent this?**

**Potential Impact**

If a malicious user sent 1 million API requests:


Azure AI service costs could increase significantly.

Service performance could degrade.

Legitimate users could experience slower response times.

Resource quotas and rate limits could be reached.

Application availability could be affected.



**Azure Service That Could Prevent This**


The primary Azure service that could help prevent this is Azure API Management.

Azure API Management provides:


Rate limiting

Request throttling

Usage quotas

Authentication and authorization controls




**Additional protection can also be provided through:**


Azure Web Application Firewall (WAF)

Azure Front Door

Microsoft Defender for Cloud


**Recommended Approach**

Azure API Management should be placed in front of the AI endpoint to enforce rate limits and quotas. This would help prevent abuse, protect against excessive costs, and ensure that legitimate users continue to receive service.
