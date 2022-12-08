---
title: Create an Analytics property in tags
description: Create a space to customize how data is collected, using tags.
feature: Launch Implementation
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
---
# Create an Adobe Analytics tag property

Tags in Adobe Experience Platform lets you integrate Experience Cloud solutions on your website (including Analytics). This page outlines specifically how a tag admin can get a basic Adobe Analytics implementation configured correctly.

## Prerequisites

[Create a report suite](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Create a silo for Analytics data to be collected.

## Create a tag property and install vital extensions

Properties are overarching containers you use to manage tags. Extensions let you install product-specific tags and configure them.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click **[!UICONTROL New Property]**.
1. Give your Property a name, such as the title of your website, and enter the domain you intend to implement Analytics on. Click **[!UICONTROL Save]**.
1. Click your newly created tag property to enter its settings.
1. Click the **[!UICONTROL Extensions]** tab, then click **[!UICONTROL Catalog]**.
1. Locate 'Experience Cloud ID Service', then click **[!UICONTROL Install]**.
1. All settings, including Experience Cloud Organization ID, should be already filled out. Click **[!UICONTROL Save]**.
1. Back in the extensions catalog, locate Adobe Analytics and click **[!UICONTROL Install]**.

See the full documentation for the [Adobe Analytics extension](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html) for more detailed information.

## Create data elements for Adobe Analytics

Data elements are references to specific parts of your site to collect variable values.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the tag property that you intend to implement on your site.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Add Data Element]**.
1. Give the data element the following settings:

   * Name: Page Name
   * Extension: Core
   * Data Element Type: JavaScript Variable
   * JavaScript variable name: `window.document.title`

     >[!NOTE]
     >
     >This value serves as an example to help get started. If your organization defines a better value for page name, such as a data layer value, you can enter it here.
   * Clean text checked
   * Storage Duration: None
1. Click **[!UICONTROL Save]**.

## Create rules for Adobe Analytics

Rules map data elements to Analytics variable values, and determine when those values are sent to Adobe's servers.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
1. Click the tag property that you intend to implement on your site.
1. Click the **[!UICONTROL Rules]** tab, then click **[!UICONTROL Add Rule]**. Name it `Global Rule`.
1. Click **[!UICONTROL Add]** next to events, and enter the following settings:
   * Extension: Core
   * Event Type: Library Loaded (Page Top)
   * Name: Core - Library Loaded (Page Top)
1. Click **[!UICONTROL Keep Changes]**.
1. Under **[!UICONTROL Actions]**, click **[!UICONTROL Add]**, and enter the following settings:
   * Extension: Adobe Analytics
   * Action Type: Set Variables
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. Click **[!UICONTROL Keep Changes]**.
1. Click the Plus sign next to actions to add another action, and enter the following settings:
   * Extension: Adobe Analytics
   * Action Type: Send Beacon
   * Name: Adobe Analytics - Send Beacon
   * Tracking: s.t()
1. Click **[!UICONTROL Keep Changes]**.
1. Verify that you have the event and two actions set, then click **[!UICONTROL Save]**.

## Next steps

[Deploy your Analytics implementation to your dev environment](deploy-dev.md): Get Analytics code working in a test environment.
