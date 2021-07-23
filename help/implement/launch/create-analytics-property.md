---
title: Create an Analytics property in tags
description: Create a space to customize how data is collected, using tags.
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
---
# Create an Adobe Analytics tag property

Tags in Adobe Experience Platform lets you integrate Experience Cloud solutions on your website (including Analytics). This page outlines specifically how a tag admin can get a basic Adobe Analytics implementation configured correctly.

>[!NOTE]
>Adobe Experience Platform Launch has been rebranded as a suite of data collection technologies in Experience Platform. Several terminology changes have rolled out across the product documentation as a result. Please refer to the following [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) for a consolidated reference of the terminology changes.

## Prerequisites

[Create a report suite](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md): Create a silo for Analytics data to be collected.

## Create a tag property and install vital extensions

Properties are overarching containers you use to manage tags. Extensions let you install product-specific tags and configure them.

1. Go to [experience.adobe.com](https://experience.adobe.com) and log in when prompted.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Click **[!UICONTROL Go to Launch / Data Collection]**, then select **[!UICONTROL Tags]**.
1. Click **[!UICONTROL New Property]**.
1. Give your Property a name, such as the title of your website, and enter the domain you intend to implement Analytics on. Click **[!UICONTROL Save]**.
1. Click your newly created tag property to enter its settings.
1. Click the **[!UICONTROL Extensions]** tab, then click **[!UICONTROL Catalog]**.
1. Locate Identity Service, then click **[!UICONTROL Install]**.
1. All settings, including Experience Cloud Organization ID, should be already filled out. Click **[!UICONTROL Save]**.
1. Back in the extensions catalog, locate Adobe Analytics and click **[!UICONTROL Install]**.

## Create data elements for Adobe Analytics

Data elements are references to specific parts of your site to collect variable values.

1. Go to [experience.adobe.com](https://experience.adobe.com) and log in when prompted.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Click **[!UICONTROL Go to Launch / Data Collection]**, then select **[!UICONTROL Tags]**.
1. Click the tag property that you intend to implement on your site.
1. Click the **[!UICONTROL Data Elements]** tab, then click **[!UICONTROL Create New Data Element]**.
1. Give the data element the following settings:

   * Name: Page Name
   * Extension: Core
   * Data Element Type: JavaScript Variable
   * Path to variable: `window.document.title`

     >[!NOTE]
     >
     >This is an example value to help get started. If your organization defines a better value for page name, such as a data layer value, you can enter it here.
   * Clean text checked
   * Duration: Pageview
1. Click **[!UICONTROL Save]**.

## Create rules for Adobe Analytics

Rules map data elements to Analytics variable values, and determine when those values are sent to Adobe's servers.

1. Go to [experience.adobe.com](https://experience.adobe.com) and log in when prompted.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Click **[!UICONTROL Go to Launch / Data Collection]**, then select **[!UICONTROL Tags]**.
1. Click the tag property that you intend to implement on your site.
1. Click **[!UICONTROL Create New Rule]** and name it `Global Rule`.
1. Click **[!UICONTROL Add]** next to events, and enter the following settings:
   * Extension: Core
   * Event Type: Library Loaded (Page Top)
   * Name: Core - Library Loaded (Page Top)
   * Order: 50
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

## Documentation and additional resources

* [Adobe Analytics extension documentation](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en): Full documentation specific to the Adobe Analytics extension in tags.
* [Getting Started with tags](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en): Full documentation for tags, including a more in-depth getting started guide
* [Adobe Experience Platform Launch channel](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform): Learn how to use tags through videos

## Next steps

[Deploy your Analytics implementation to your dev environment](deploy-dev.md): Get Analytics code working in a test environment.
