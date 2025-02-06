# AGL.Next.EIP.APIM.Apps
AGL Enterprise Integration Platform API Management API Definition and Assets
## Prerequisites
### **Platform Access**
| **Platform**   | **Group Name**                          | **Other Details**                                                    |
|----------------|-----------------------------------------|----------------------------------------------------------------------|
| Azure Portal   | App-DG-Retail-EIPNext-Developer         | Role: API Management Service Contributor <br> Scope: DEV API Management Instance <br> Description: Role that can update API Management instance APIs <br> Environment: DEV |
| Azure Portal   | eip-application-{env}-rg-workspace-owner| Role: API Management Service Contributor <br> Scope: All API Management Service <br> Description: Permission for EIP Azure DevOps Principal to perform deployments to EIP API Management instances via APIOps <br> Environment: ALL |
| Azure Portal   | App-DG-Retail-EIPNext-Developer         | Role: Key Vault Secret Officer <br> Scope: Key Vault for API Management <br> Description: Role assignment to EIP Developer, so they can create secrets and link to API Management Named Values <br> Environment: ALL |
| Azure DevOps   | Developer                               | Can run extractor (CI) and publisher (CD)                           |
| Azure DevOps   | Release Managers                        | Can approve deployments (SIT, PPD, PRD)                             |
| Azure Pipeline | -                                       | The build agent should run on a Linux operating system with PowerShell Core capability. |

## Pipelines

APIOps has two major pipelines, the **extractor** (build) and the **publisher** (deploy) pipeline.

| **Pipeline**   | **Description**                                                                                              | **Pipeline Structure**                                                                                         |
|----------------|--------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| **Extractor**  | The extractor generates APIOps artifacts from an existing APIM instance. These artifacts can then be used as the source of truth for your APIM environment; make changes to them and have a CI/CD process update your Azure environment. | The Extractor pipeline is created under the `API Management/Extractor` location. The pipeline name is based on a business unit in a Pascal case format. |
| **Publisher**  | The Publisher tool updates the Azure APIM instance with the artifact folder contents. It also picks up changes in the configuration YAML file when running the publisher. | The Publisher pipeline is created under the `API Management/Publisher` location. The pipeline name is based on a business unit in a Pascal case format. |
