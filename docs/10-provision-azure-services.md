---
hide:
  - toc
---

# Provision Azure services

The following services will be provisioned in the lab Azure subscription:

1. [Azure AI Document Intelligence](https://azure.microsoft.com/products/ai-services/ai-document-intelligence?WT.mc_id=aiml-77396-cxa).
1. [Azure Cosmos DB](https://learn.microsoft.com/azure/cosmos-db/introduction?WT.mc_id=aiml-77396-cxa).
1. [Azure Static Web Apps](https://azure.microsoft.com/services/app-service/static/?WT.mc_id=aiml-77396-cxa).

## Open the workshop with VS Code

1. Start VS Code by selecting the icon from the Windows taskbar.
2. From VS Code, open the **C:\Workshop** folder.

## Create the Azure Patient Registration Services

We're going to run commands to provision Azure services.

1. From the VS Code menu, select **Terminal**, then **New Terminal**.
1. In the new terminal window, run the following command to authenticate to Azure.

    ```Shell
    azd auth login
    ```

1. Switch to the **Resources** tab in the lab environment for the Azure Portal **username** and **password**.
1. Select the **Email, phone, or Skype** option in the Sign in dialog and select the [T] next to the **Username** field in the **Resources** tab.
1. Next, select the **Password** field and select the [T] next to the **Password** field in the **Resources** tab.
1. Switch back to the **Instructions** tab.

1. Initialize your Azure environment.

    You'll be asked to create an environment name. For this workshop, the environment name must be globally unique. Create a unique environment name by appending a random six digital number after **contoso-health-app-NNNNNN**, for example, contoso-health-app-318721. But don't use the example name, use your own.

    Initialize your Azure environment with the following command.

    ```Shell
    azd init
    ```

1. Deploy the Azure services with the following command.

    ```Shell
    azd up
    ```

1. Select the default subscription.
1. Select a region (e.g: **eastus**).

    It will take approximately 5 minutes to deploy the Azure services. So, now is a great time to read the next sections of the workshop documentation while you wait for the services to deploy. **Note, the Storage Account is created early on, so, once that is created you can start uploading the training data while the rest of the services are being provisioned.**

1. The output from the `azd up` command will look like the following.

    ```Text
    Packaging services (azd package)

    (✓) Done: Packaging service api
    - Package Output: /tmp/azddeploy3376479742.zip
    (✓) Done: Packaging service web
    - Package Output: dist

    Provisioning Azure resources (azd provision)
    Provisioning Azure resources can take some time

    (✓) Done: Resource group: rg-contoso-health-app-767678
    (✓) Done: Azure AI Document Intelligence: form-recognizer-r2qoh4og4cf6a
    (✓) Done: Storage account: storager2qoh4og4cf6a
    (✓) Done: Azure Cosmos DB: cosmos-r2qoh4og4cf6a
    (✓) Done: Application Insights: api-r2qoh4og4cf6a
    (✓) Done: App Service plan: api-r2qoh4og4cf6a
    (✓) Done: Static Web App: swa-r2qoh4og4cf6a

    Deploying services (azd deploy)

    (✓) Done: Deploying service api
    - Endpoint: https://api-r2qoh4og4cf6a.azurewebsites.net/

    (✓) Done: Deploying service web
    - Endpoint: https://polite-coast-0a3c12c1e.3.azurestaticapps.net
    ```

1. Make a note of your `Resource group` and `Storage account` names, as you'll need them in the next section of the workshop.

    ```Text
    Resource group: rg-contoso-health-app-NNNNNN
    Storage account: storagexxxxxxxxxxx
    ```

1. Leave VS Code open, as you'll need it in the next section of the workshop.
