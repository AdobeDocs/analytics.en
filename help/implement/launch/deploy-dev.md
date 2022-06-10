---
title: Deploy Adobe Analytics to a dev environment
description: Learn how to use tags to deploy Adobe Analytics to your development environment.
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
---
# Deploy an Analytics implementation to a development environment

Once you have created and configured a tag property, the libraries are ready to be deployed and code implemented on your site.

## Prerequisites

[Create and configure a tag property for Adobe Analytics](create-analytics-property.md): Access the tool and create a space for your Analytics implementation.

## Create adapters and environments

Tags accommodates many organizational workflows in deploying code. Follow these steps to create the minimum necessary components for an Analytics implementation. As a tag admin, you can work within your organization to establish the correct workflow for deploying Adobe solutions.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the tag property that you intend to implement on your site.
3. Click **[!UICONTROL Hosts]**, then click **[!UICONTROL Add Host]**.
4. Name it `"Adobe managed"`, and select **[!UICONTROL Managed by Adobe]** in the type dropdown. Click Save.
5. Navigate to **[!UICONTROL Environments]**, then click **[!UICONTROL Add Environment]**.
6. Select **[!UICONTROL Development]**, name it `"Dev Environment"`, then select the Adobe managed host from the dropdown. Click **[!UICONTROL Save]**.
7. A modal window appears showing Web Install Instructions. We will return to this window at a later time; click **[!UICONTROL Close]** for now.
8. Click **[!UICONTROL Add Environment]**, select **[!UICONTROL Staging]**, name it `"Staging Environment"`, then select the Adobe managed host. Click **[!UICONTROL Create]**, then close the install instructions modal window.
9. Click **[!UICONTROL Add Environment]** again, select **[!UICONTROL Production]**, name it `"Production Environment"`, then select the Adobe managed host. Click **[!UICONTROL Create]**, then close the install instructions modal window.

## Build a dev library

Despite all the changes and configurations made so far, no code has actually been published. Creating a library, roughly translated as a collection of changes, allows the publishing of code to be used on your site.

1. Log in to [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) using your AdobeID credentials.
2. Click the tag property that you intend to implement on your site.
3. Click the **[!UICONTROL Publishing Flow]** tab, then click **[!UICONTROL Add Library]**. See [Publishing overview](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) in the Tags documentation for more information around this page.
4. Name the library `'Initial changes'`, and select your development environment.
5. Click **[!UICONTROL Add All Changed Resources]**, which automatically lists Adobe Analytics, Identity Service, and Core.
6. Click **[!UICONTROL Save]**.
7. Back on the publishing workflow screen, click the dropdown next to your new library, and click **[!UICONTROL Build for Development]**. After a few seconds, the yellow dot on the library turns green, indicating that the build was successful.
8. Navigate to **[!UICONTROL Environments]**, then click the install icon to the right of your development environment. This action brings up the Web Install Instructions modal window again.
9. Copy the code block(s) and provide them to your organization's website owners.

## Install tags on your website's development environment

If you control your website's code, implement each block of code in their respective location:

* The main tag belongs in the `<head>` tag on your site.
* If you choose to load tags synchronously, you must also include a second code block just below the closing `</body>` tag on your site. You can choose to load library tags synchronously by toggling the **[!UICONTROL Load Library Asynchronously]** option in the Web Install Instructions.

Tag code is typically placed in the site's overarching template. A blank page only containing implementation code would look like the following:

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Troubleshooting

**Attempting to build fails.**

A common reason is because elements already exist in other libraries pushed to staging or production. When initially creating libraries, ensure only changed resources are added to the library.

## Next Steps

[Validate your Analytics implementation and publish to production](validate-publish-prod.md): Start getting value out of Adobe Analytics.
