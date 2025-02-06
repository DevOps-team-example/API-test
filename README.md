# API-test

# AGL.Next.EIP.APIM.Apps
AGL Enterprise Integration Platform API Management API Definition and Assets
# Prerequisites
# Platform Access
| Platform | Group Name | Other Details |
|----------|----------|----------|
|Azure Portal   | App-DG-Retail-EIPNext-Developer   |Role: API Management Service Contributor 

Scope: DEV API Management Instance

Description: Role that can update API Management instance APIs

Environment: DEV   |
| Azure Portal   |	eip-application-{env}-rg-workspace-owner  | Role: API Management Service Contributor 

Scope: All API Management Service

Description: Permission for EIP Azure DevOps Principal to perform deployments to EIP API Management instances via APIOps

Environment: ALL  |
|Azure Portal   | App-DG-Retail-EIPNext-Developer  | Role: Key Vault Secret Officer

Scope: Key Vault for API Management

Description: Role assignment to EIP Developer, so they can create secrets and link to API Management Named Values

Environment: ALL  |
| Azure DevOps  | Developer  | Can run extractor (CI) and publisher (CD)  |
|Azure DevOps  | Release Managers| Can approve deployments (SIT, PPD, PRD)  |
