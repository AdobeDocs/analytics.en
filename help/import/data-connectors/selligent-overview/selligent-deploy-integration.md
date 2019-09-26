---
description: Deploying this integration is a simple 3-step process.
seo-description: Deploying this integration is a simple 3-step process.
seo-title: Deploying the Integration
solution: Analytics
title: Deploying the Integration
uuid: c578bf26-34c2-44ea-8e60-2990273f8659
index: y
internal: n
snippet: y
---

# Deploying the Integration{#deploying-the-integration}

Deploying this integration is a simple 3-step process.

## Completing the Integration Wizard{#completing-the-integration-wizard}

To activate the integration you must complete the Selligent integration wizard within the Data Connectors interface.

1. Navigate to the Data Connectors area within the Adobe Experience Cloud.

   ![](assets/selligent-data_connectors.png)

1. Under **[!UICONTROL Add Integrations]**, drag and drop the Selligent plugin into Adobe Experience Cloud.

   ![](assets/selligent-add_integration.png)

   This will open up the Selligent Data Connector Integration. 

1. **Integration Settings**: Choose the desired Report Suite and provide a name for the integration under **[!UICONTROL Integration Settings]**.

1. Under **[!UICONTROL Custom Values]**, fill in all your Selligent account-related information.

   ![](assets/selligent-general_settings.png)

1. **Variable mapping**: Choose the appropriate reserved eVars and events from the drop down menus:

   ![](assets/selligent-variables.png)

1. **Data Settings**: You may choose your own segments under **[!UICONTROL Your Segments]** apart from the 3 automated **[!UICONTROL Partner]** segments. 

1. This integration may require downloading a few data point to your Selligent account. You may choose to give access for the same under **[!UICONTROL Access Request]**. 
1. Under **[!UICONTROL Data Collection]**, choose an automated or manual solution (JavaScript Plug-in) to collect query string parameters from the landing page URL. If you choose an automated solution, enter your query string parameter for Message ID and Recipient ID which is MID and RID respectively. For JavaScript Plug-in, contact your Adobe Consultant. 
1. **Report Settings**: Under **[!UICONTROL Dashboard Generation]**, check the box to have the Selligent dashboard automatically generated for you.

   ![](assets/selligent-report_settings.png)

1. Review the integration summary and click **[!UICONTROL Activate]**.

## Configuration within Selligent{#configuration-within-selligent}

As soon as the Integration is enabled inside Adobe Analytics, an automatic configuration is enabled on the Selligent side.

A tracker has been created which will track every e-mail. In case you want to limit it to a certain domain, please update the tracker configuration.

We highly recommended that you move the tracking parameter for Adobe Analytics in the URL to the front. This will ensure that the Adobe Processing rules pick up the parameters from the landing page URL. Enable the tracking by checking the checkbox as shown below.

![](assets/selligent-tracker.png)

## Verifying the Integration{#verifying-the-integration}

Once all deployment steps have been completed you can validate that the integration is successfully transferring data.

It will take a few days for the data exchange to begin. Please make sure you contact Selligent after you activate the integration.

### Integration Activity Log {#section-927e270495db479fba9578915d9ae9c9}

Navigate to your Selligent Integration within Data Connectors. Under the **[!UICONTROL Support]** tab, you should see events like Metric Data imported and/or Classification Data imported successfully :

![](assets/selligent-verifying.png)

### Reporting Data {#section-ebd481a162324e66bd6dc8cb4b8d2424}

View your Selligent Message reports with appropriate metrics.

1. Go to Report & Analytics under Adobe Experience Cloud. 
1. Select the appropriate Report Suite. 
1. Under **[!UICONTROL Custom Conversion]**, select the **[!UICONTROL Message ID Reports]** and choose **[!UICONTROL Message ID/Message Name]**.
