# Deploy Logic App with Secured storage account having Private Endpoints


At present, we don't have an option to use the Azure portal to deploy Standard Logic App with secured storage account. However, we can work with ARM templates which let us to use the Storage account behind firewall for Logic App standard resource deployment.

 [![Deploy to Azure](https://aka.ms/deploytoazurebutton)](https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2FVeeraMS%2FLogicApp-deployment-with-Secure-Storage%2Fmain%2Ftemplates%2FDeployResources.json)

You can refer to the templates available in the templates folder. You can use deploy custom template option in the Azure Portal or Powershell to deploy the ARM templates.

The template creates the below resources:
1. Creates Storage account which denies the public traffic
2. Creates VNET and Subnets
3. Creates Private DNS Zones and Private Endpoints for blob, file, queue and table services
4. Creates File Share (LogicApp App settings refer to this which create Logic App host runtime directories and files)
5. Creates App Service Plan (Workflow standard -WS1) to host Standard Logic App resources
6. Creates the Standard Logic App and sets network config with the VNET integration (to connect to storage account on private endpoints)

This template has been created from the sample Function App template available here https://github.com/Azure/azure-quickstart-templates/tree/master/quickstarts/microsoft.web/function-app-storage-private-endpoints

**Disclaimer**: The templates provided are samples, you may verify and make changes as per your requiremenrts. Any concerns or queries feel free to let me know.

