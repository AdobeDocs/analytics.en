---
title: Validate a development implementation and publish to production
description: Learn how to use Adobe Experience Platform tags to deploy Adobe Analytics to your production environment.
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
---
# Validate a development implementation and publish to production

Once your tag library is pushed to production, your organization can begin to use Adobe Analytics to pull basic reports.

>[!NOTE]
>Adobe Experience Platform Launch has been rebranded as a suite of data collection technologies in Experience Platform. Several terminology changes have rolled out across the product documentation as a result. Please refer to the following [document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en) for a consolidated reference of the terminology changes.

## Prerequisites

[Deploy your Analytics implementation to your dev environment](deploy-dev.md): An Analytics implementation must be published to your development environment in order to follow this page.

## Validate your dev implementation using the Experience Cloud debugger

The Experience Cloud debugger is a Chrome plug-in that shows all Experience Cloud tags present on a page.

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. Navigate to your development website that you have implemented tags on.
3. Click on the Adobe Experience Cloud debugger icon in the upper right of Chrome
4. If everything is properly implemented, you should see content inside Adobe Analytics, tags, and the Adobe Experience Cloud Visitor ID service:

![debugger][assets/debugger.png]

## Deploy your dev implementation to staging/prod

Once you've validated you're seeing data, you can push your implementation to the live version of your site.

1. Go to [experience.adobe.com](https://experience.adobe.com) and log in when prompted.
1. Select **[!UICONTROL Launch / Data Collection]**.
1. Click **[!UICONTROL Go to Launch / Data Collection]**, then select **[!UICONTROL Tags]**.
1. Click the tag property that you intend to implement on your site.
1. Click the **[!UICONTROL Publishing]** tab and locate your library in the development column.
1. Click the dropdown on the library, then select **[!UICONTROL Submit for Approval]**. Click **[!UICONTROL Submit]** on the modal window.
1. Click the library's dropdown again (now in the Submitted column), and select **[!UICONTROL Build for Staging]**.
1. After a few moments, the yellow colored light on the library turns green, indicating a successful build.
1. Click the library's dropdown again, and select **[!UICONTROL Approve for Publishing]**.
1. Click the library's dropdown again (now in the [!UICONTROL Approved] column), and select **[!UICONTROL Build and Publish to Production]**.
1. Go to the Environments tab, the click **[!UICONTROL Production Environment]**.
1. Copy the production header + footer code, and provide it to your website owners. Request that they implement this code on your site's production environment.

## Validate your production implementation

Confirm that you're seeing data on the live version of your site, and begin official data collection for Adobe Analytics.

1. Once you have confirmed from your website owners that they have pushed the tag code to production, navigate to your website's homepage in Chrome and open the [!UICONTROL Adobe Experience Cloud debugger].
2. If everything is working, you should see similar data to your tests in your dev environment. At this point, you are now collecting data on your site and can now start using Adobe Analytics for reporting.

## Troubleshooting

**No data appears in the debugger.**

While on your site, open the browser's developer console (typically F12). Look at the source code of the page and make sure the following are met:

* There are no JavaScript errors in the console. Work with your organization's website owners to make sure all JS errors are resolved.
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* AppMeasurement library exists: Navigate directly to the JS source to make sure the JS file contains code. If it does not, make sure each environment is created, and that the library is published to its respective environment.
* Interfering plug-ins: Some Chrome plug-ins can prevent image requests from firing. Disable any plug-ins that might stop data from being sent to Adobe's servers.

## Next Steps

Now that a basic implementation is set up, your role within your organization can influence which path you want to learn more about:

* [Create a solution design document](../prepare/solution-design.md): Make a plan for how you want to use custom variables, then include them in your implementation
* [Get started using Analysis Workspace](/help/analyze/analysis-workspace/home.md): Dive right into Adobe Analytics using the tool's flagship capability.
