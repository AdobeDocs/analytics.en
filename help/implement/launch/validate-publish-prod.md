---
title: Deploy Adobe Analytics to a dev environment
description: Learn how to use Adobe Experience Platform Launch to deploy Adobe Analytics to your development environment.
---

# Validate a development implementation and publish to production

Once your Adobe Experience Platform Launch library is pushed to production, your organization can begin to use Adobe Analytics to pull basic reports.

## Prerequisites

[Deploy your Analytics implementation to your dev environment](deploy-dev.md): An Analytics implementation must be published to your development environment in order to follow this page.

## Validate your dev implementation using the Experience Cloud debugger

The Experience Cloud debugger is a Chrome plug-in that shows all Experience Cloud tags present on a page.

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. Navigate to your development website that you have implemented Launch on.
3. Click on the Adobe Experience Cloud debugger icon in the upper right of Chrome
4. If everything is properly implemented, you should see content inside Adobe Analytics, Adobe Experience Platform Launch, and the Adobe Experience Cloud Visitor ID service:

![debugger][assets/debugger.png]

## Deploy your dev implementation to staging/prod

Once you've validated you're seeing data, you can push your implementation to the live version of your site.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Click the Launch property that you intend to implement on your site.
3. Click the Publishing tab and locate your library in the development column.
4. Click the dropdown on the library, then select Submit for Approval. Click Submit on the modal window.
5. Click the library's dropdown again (now in the Submitted column), and select Build for Staging.
6. After a few moments, the yellow colored light on the library turns green, indicating a successful build.
7. Click the library's dropdown again, and select Approve for Publishing.
8. Click the library's dropdown again (now in the Approved column), and select Build and Publish to Production.
9. Go to the Environments tab, the click Production Environment.
10. Copy the production header + footer code, and provide it to your website owners. Request that they implement this code on your site's production environment.

## Validate your production implementation

Confirm that you're seeing data on the live version of your site, and begin official data collection for Adobe Analytics.

1. Once you have confirmed from your website owners that they have pushed the Launch code to production, navigate to your website's homepage in Chrome and open the Adobe Experience Cloud debugger.
2. If everything is working, you should see similar data to your tests in your dev environment. At this point, you are now collecting data on your site and can now start using Adobe Analytics for reporting.

## Troubleshooting

**No data appears in the debugger.**

While on your site, open the browser's developer console (typically F12). Look at the source code of the page and make sure the following are met:

* There are no JavaScript errors in the console. Work with your organization's website owners to make sure all JS errors are resolved.
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* AppMeasurement library exists: Navigate directly to the JS source to make sure the JS file contains code. If it does not, make sure each environment is created, and that the library is published to its respective environment.
* Interfering plug-ins: Some Chrome plug-ins can prevent image requests from firing. Disable any plug-ins that might stop data from being sent to Adobe's servers.

## Next Steps

Now that a basic implementation has been set up, your role within your organization can influence which path you want to learn more about:

* [Create a solution design document](../prepare/solution-design.md): Make a plan for how you want to use custom variables, then include them in your implementation
* [Get started using Analysis Workspace](/help/analyze/analysis-workspace/home.md): Dive right into Adobe Analytics using the tool's flagship capability.
