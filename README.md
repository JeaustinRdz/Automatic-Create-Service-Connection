# Automatic-Create-Service-Connection

This repository contains the step-by-step guide to automatically create a service connection using Azure Pipelines.

## Documentation Used

1. [Create a service endpoint / Service connection using az DevOps](https://learn.microsoft.com/en-us/azure/devops/cli/service-endpoint?view=azure-devops#create-service-endpoint-using-a-configuration-file)
2. [Get the project ID](https://learn.microsoft.com/en-us/rest/api/azure/devops/core/projects/list?view=azure-devops-rest-7.1&tabs=HTTP)
3. [Authenticate with Azure DevOps](https://learn.microsoft.com/en-us/azure/devops/cli/azure-devops-cli-in-yaml?view=azure-devops&tabs=bash#authenticate-with-azure-devops)

## Steps to Automatically Create a Service Connection Using Azure DevOps Pipelines

1. Go to **Project settings** > **Service Connections** > **Security** and add the **"Pipelines Build Service (Your_Organization)"** as an administrator. If not, you will encounter an issue like the following:
   ![image](https://github.com/user-attachments/assets/7feb01a7-1da1-409d-8d2c-9bc42f9a1347)

2. Create a configuration file. In this case, you can use the `Configuration.json` file attached in the repository.

   2.1 To get the project ID, please follow [documentation number 2](https://learn.microsoft.com/en-us/rest/api/azure/devops/core/projects/list?view=azure-devops-rest-7.1&tabs=HTTP).

   2.2 The role: `"8311e382-0749-4cb8-b61a-304f252e45ec"` is the ACR push role that has read and write permissions.

3. Use the YAML pipeline attached in the repository as a guide on how to configure the pipeline. Lines 18 and 19 are not required but help you get the Service Connection ID.
