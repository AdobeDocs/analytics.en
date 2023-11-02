---
description: Explains the steps the Analytics Admin needs to complete to enable Activity Map link collection and user download.
title: Enable Activity Map
feature: Activity Map
role: Admin
exl-id: 0b2b9f3d-0c75-4eb8-9235-c9c98eb035d3
mini-toc-levels: 3
---

# Activate and Enable Activity Map

Explains the steps the Analytics Admin needs to complete to enable Activity Map link collection and user download.

## Step 1. Activate Activity Map {#update_code}

The Activity Map module is part of the AppMeasurement.js, Adobe Experience Platform tags, and the Web SDK (alloy.js). Activity Map data cannot be collected unless you update to **Adobe Analytics tags extension v1.90** or higher, **AppMeasurement version 1.6** or higher or **Web SDK version 2.15.0** or higher. 

### Adobe Experience Platform tags {#tags}

In Adobe Experience Platform tags, navigate to the property for which you are implementing Analytics. In the [!UICONTROL Install Extension] dialog, select **[!UICONTROL Use Activity Map]**.

![](assets/aa_extension.png)

### Web SDK code {#web_sdk}

In Adobe Experience Platform tags, navigate to the property for which you are implementing Analytics. Under [!UICONTROL Extensions] -> [!UICONTROL Adobe Experience Platform Web SDK], select **[!UICONTROL Enable click data collection]** as highlighted below. Then build the Library with the changes, and publish the Library to production.

![](assets/web_sdk.png)

See [Track links](https://experienceleague.adobe.com/docs/experience-platform/edge/data-collection/track-links.html) for information on how to implement link tracking and how to enable Activity Mapping by capturing the `region` of the clicked HTML element.

>[!NOTE]
>
>Enabling link tracking with Web SDK currently sends link events when a customer navigates from one page to the next. This is different from how AppMeasurement works and can potentially result in extra billable hits sent to Adobe.

### AppMeasurement {#appmeasurement}

Download the latest Javascript library depending whether you are using AppMeasurement or Web SDK.
Go to **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL All admin]** > **[!UICONTROL Code manager]** and [implement it](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html).

## Step 2. Enable Activity Map reports {#enable}

First, you need to enable Activity Map reports at the report-suite level.

1. Log in to Adobe Analytics and navigate to  **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > Select report suite > **[!UICONTROL Edit Settings]** > **[!UICONTROL Activity Map]** > **[!UICONTROL Activity Map Reporting]** .

1. Activity Map collects the link data in Activity Map reports. For the activation to happen, you must first activate the variables by clicking **[!UICONTROL Enable Activity Map Reports]**.

   This step adds all the Analytics dimensions that you need to collect data.

   ![](assets/enable.png)

1. After about an hour, check the [Activity Map Page report](/help/analyze/activity-map/activitymap-reporting-analytics.md), which shows all the pages where users clicked on a link.

## Step 3. Add users to [!UICONTROL Activity Map Access] product profile {#add_users}

1. Click **[!UICONTROL Add Users to Group]**.

   This will take you to the product profile page in the [Adobe Admin Console](https://adminconsole.adobe.com/E2F05B3B52F54D2E0A490D44@AdobeOrg/overview).

1. If you have not created an [!UICONTROL Activity Map Access] product profile, do so now. The permission items required for this profile are [!UICONTROL Analytics Tools] > [!UICONTROL Activity Map] and [!UICONTROL Analytics Tools] > [!UICONTROL Segment Publishing].

1. Add users to that product profile. This allows your users to download Activity Map from  **[!UICONTROL Adobe Analytics]** > **[!UICONTROL Tools]** > **[!UICONTROL ActivityMap]** .

