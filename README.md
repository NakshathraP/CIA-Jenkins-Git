# LA-1-Personal-CV

> blockquote
> bq1

**bold**
*italicized*

1. first
2. second
3. third

- ul1
- ul2
- ul3

`code
code `

--- horizontal rule ---

# CI/CD Pipeline: GitHub to Azure Web App

This guide provides steps to set up a Continuous Integration and Continuous Deployment (CI/CD) pipeline to automatically deploy code from a GitHub repository to an Azure Web App. This pipeline uses GitHub Actions to trigger builds and deployments on commits or pull requests.

## Prerequisites

1. **GitHub Repository**: Have a GitHub repository with your application code.
2. **Azure Web App**: Create an Azure Web App in the [Azure portal](https://portal.azure.com/).
3. **Azure Service Principal**: Generate Azure credentials for GitHub Actions to deploy to your Azure Web App.

## Step 1: Create an Azure Service Principal

1. Open Azure Cloud Shell or use your local terminal with Azure CLI installed.
2. Run the following command, replacing `<app-name>` and `<resource-group>` with your web app and resource group names:

   ```bash
   az ad sp create-for-rbac --name "<app-name>" --role contributor \
       --scopes /subscriptions/{subscription-id}/resourceGroups/{resource-group} \
       --sdk-auth
