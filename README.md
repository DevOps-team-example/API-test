# AGL.Next.EIP.APIM.Apps
AGL Enterprise Integration Platform API Management API Definition and Assets
# Prerequisites
### **Platform Access**
This section outlines access roles and permissions for Azure Portal and Azure DevOps. These should be done via Terraform.

| **Platform**   | **Group Name**                          | **Other Details**                                                    |
|----------------|-----------------------------------------|----------------------------------------------------------------------|
| Azure Portal   | App-DG-Retail-EIPNext-Developer         | Role: API Management Service Contributor <br> Scope: DEV API Management Instance <br> Description: Role that can update API Management instance APIs <br> Environment: DEV |
| Azure Portal   | eip-application-{env}-rg-workspace-owner| Role: API Management Service Contributor <br> Scope: All API Management Service <br> Description: Permission for EIP Azure DevOps Principal to perform deployments to EIP API Management instances via APIOps <br> Environment: ALL |
| Azure Portal   | App-DG-Retail-EIPNext-Developer         | Role: Key Vault Secret Officer <br> Scope: Key Vault for API Management <br> Description: Role assignment to EIP Developer, so they can create secrets and link to API Management Named Values <br> Environment: ALL |
| Azure DevOps   | Developer                               | Can run extractor (CI) and publisher (CD)                           |
| Azure DevOps   | Release Managers                        | Can approve deployments (SIT, PPD, PRD)                             |
| Azure Pipeline | -                                       | The build agent should run on a Linux operating system with PowerShell Core capability. |
