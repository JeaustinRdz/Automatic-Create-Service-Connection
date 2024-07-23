# Automatic-Create-Service-Connection
This repository have the step by step to automatic create service connection using Azure Pipelines

For this example we will use the following documentation:
1- Create a service endpoint / Service connection using az DevOps: https://learn.microsoft.com/en-us/azure/devops/cli/service-endpoint?view=azure-devops#create-service-endpoint-using-a-configuration-file

2- Get the project ID: https://learn.microsoft.com/en-us/rest/api/azure/devops/core/projects/list?view=azure-devops-rest-7.1&tabs=HTTP

3- Authenticate with Azure DevOps: https://learn.microsoft.com/en-us/azure/devops/cli/azure-devops-cli-in-yaml?view=azure-devops&tabs=bash#authenticate-with-azure-devops


Steps to create automatically a service connection using Azure DevOps pipelines

1- Go to Project settings < Service Connections < Security < and add the "Pipelines Build Service (Your_Organization)" as administrator if not you will get an issue like the following:
![image](https://github.com/user-attachments/assets/7feb01a7-1da1-409d-8d2c-9bc42f9a1347)

2- Create a config file, in this case you can use the Configuration.json file attached in the repository
  2.1 to get the project ID please follow the documentation number 2 that is in the top of the document
  2.2 The role: "8311e382-0749-4cb8-b61a-304f252e45ec" is the acr push role that have the permissions to read and write

3- Use the yaml pipeline attached in the repository as a guide of how configure the pipeline, the line 18 and 19 is not required but help you to get the Service Connection ID
