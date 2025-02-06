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
APIOps has two main pipelines: **Extractor** (build) and **Publisher** (deploy).

| **Pipeline**   | **Description**                                          | **Pipeline Structure** | **Configuration File** |
|---------------|--------------------------------------------------|----------------------|----------------------|
| **Extractor**  | Generates APIOps artifacts from an APIM instance for CI/CD updates. | Located in `API Management/Extractor`, named using Pascal case format. | Uses a YAML file to define extracted resources (APIs, named values, products, etc.). Setting `diagnosticNames: [ignore]` excludes all APIs. |
| **Publisher**  | Deploys artifacts to APIM instances and applies YAML config changes. | Located in `API Management/Publisher`, named using Pascal case format. | Uses environment-specific YAML files. Avoids hardcoding by using Azure Key Vault and named values for secure config management. |

## Limitations  
| **Constraint**        | **Description**  |
|----------------------|----------------------------------------------------------|
| **API Schema Extraction** | Extractor does not support extracting API schemas. The feature is under development. Use Terraform as a temporary solution. |

## References  
- [APIOps High-level Overview](#) – E7 - EIP DevSecOps - SDD  
- [API Management Naming Standards](#) – Azure APIM Standards  
- [APIOps How-To Page](#) – APIOps: How-To  

