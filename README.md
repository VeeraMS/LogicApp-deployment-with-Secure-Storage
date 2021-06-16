# Deploy Logic App with Secured storage account having Private Endpoints

At present, we don't have an option to use the Azure portal to deploy Standard Logic App with secured storage account. However, we can work with ARM templates which let us to use the Storage account behind firewall for Logic App standard resource deployment.

You can refer to the templates available in the templates folder.

The template creates the below resources:
1. Creates Storage account denies the public traffic
2. Creates Private Endpoints for blob, file, queue and table services
3. Creates File Share (LogicApp App settings refer to this which create Logic App host runtime directories and files)
4. Creates App Service Plan (Workflow standard -WS1) to host Standard Logic App resources
5. Creates the Standard Logic App and sets network config with the VNET integration (to connect to storage account on private endpoints)

This template has been created from the sample Function App template available here https://github.com/Azure/azure-quickstart-templates/tree/master/quickstarts/microsoft.web/function-app-storage-private-endpoints

**Disclaimer**: The templates provided are samples, you may verify and make changes as per your requiremenrts. Any concerns or queries feel free to let me know.
