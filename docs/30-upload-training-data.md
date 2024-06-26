---
hide:
  - toc
---

# Upload training data

This topic describes how to upload your training data to [Document Intelligence Studio](https://learn.microsoft.com/azure/applied-ai-services/form-recognizer/concept-form-recognizer-studio?WT.mc_id=aiml-77396-cxa).

## New patient registration form

In this workshop, you'll create a **custom template model** to recognize the fields in the new patient registration form. There are six forms in the training set, and each form has the same fields, five of these forms have been labeled, the sixth form is partially labeled. As part of this workshop, you'll finish labeling the sixth form.

This workshop includes a **New Patient Registration Form** and matching label data you need to upload to an Azure storage container.

The label data describes the location of the fields on the forms and was created for the workshop using Document Intelligence Studio. The label data is in a JSON file that is named the same as the form file. For example, the label data for the form named **form1.pdf** is in the file named **form1.pdf.json**. The label data is in the same folder as the form files.

<!-- ## Create a storage container

1. Navigate to [create a Storage account](https://portal.azure.com/#create/Microsoft.StorageAccount).
1. On the **Create storage account** page, enter the following values:
    - **Subscription**: Select the subscription that you are using for this lab.
    - **Resource group**: Select **Create new** and enter `new-patient-registration` as the name.
    - **Storage account name**: Enter a unique name for your storage account.
    - **Region**: Select the location that is closest to you.
    - **Performance**: Select **Standard**.
    - **Redundancy**: Select **Locally-redundant storage (LRS)**.
1. Select **Review**.
1. Select **Create**.

## Configure CORS

[CORS (Cross Origin Resource Sharing)](https://docs.microsoft.com/rest/api/storageservices/cross-origin-resource-sharing--cors--support-for-the-azure-storage-services?WT.mc_id=aiml-77396-cxa) needs to be configured on your Azure storage account for it to be accessible from the Document Intelligence Studio. To configure CORS in the Azure portal, you'll need access to the CORS tab of your storage account.

1. Select the CORS tab for the storage account.

   ![Screenshot of the CORS setting menu in the Azure portal.](./img/cors-setting-menu.png)

1. Start by creating a new CORS entry in the Blob service.

1. Set the **Allowed origins** to `https://formrecognizer.appliedai.azure.com`.

   ![Screenshot that shows CORS configuration for a storage account](./img/cors-updated-image.png)

    > You can use the wildcard character '*' rather than a specified domain to allow all origin domains to make requests via CORS.

1. Select all the available 8 options for **Allowed methods**.

1. Approve all **Allowed headers** and **Exposed headers** by entering an * in each field.

1. Set the **Max Age** to 120 seconds or any acceptable value.

1. Select the save button at the top of the page to save the changes.

CORS should now be configured to use the storage account from Document Intelligence Studio. -->

## Upload new patient registration form training data

Upload the **New Patient Registration Form** and matching label data to the storage container that you created in the previous step.

1. Open the Microsoft Edge browser.
1. Navigate to the `https://portal.azure.com` and sign in.
1. From the Azure Portal **burger menu**, select **All services**, then select **Storage accounts** to find your storage account.
1. Select the storage account created in the previous step. The name starts with **storage**.
1. From the **Storage account** page, select **Containers** from the left-hand menu.
1. Select the **trainingdata** container
1. On the **trainingdata** page, select **Upload**.
1. On the **Upload blob** page, select **Browse for files**.
1. From the **file manager** dialog, select **all** the files from the **workshop/assets/training_labeled/english** folder you cloned to your computer.
1. Select **Open**.
1. Select **Upload**.
1. Close the **Upload blob** dialog.
1. Leave the Azure portal open in a browser tab.
