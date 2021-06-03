---
title: Deploy Adobe Analytics to a dev environment
description: Learn how to use Adobe Experience Platform Launch to deploy Adobe Analytics to your development environment.
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
---
# Deploy an Analytics implementation to a development environment

Once a property has been created and configured in Launch, the libraries are ready to be deployed and code implemented on your site.

## Prerequisites

[Create and configure a property for Adobe Analytics in Launch](create-analytics-property.md): Access the tool and create a space for your Analytics implementation.

## Create adapters and environments

Launch accommodates many organizational workflows in deploying code. Follow these steps to create the minimum necessary components for an Analytics implementation. As a Launch admin, you can work within your organization to establish the correct workflow for deploying Adobe solutions.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Click the Launch property that you intend to implement on your site.
3. Click the Adapters tab, then click Add Adapter.
4. Name it "Akamai", and select Akamai in the type dropdown. Click Save.
5. Go to the Environments tab, then click Create New Environment.
6. Select Development, name it "Dev Environment", then select the Akamai adapter from the dropdown. Click Create, then click Close.
7. Click Add Environment, select Staging, name it "Staging Environment", then select the Akamai adapter. Click Create, then click Close.
8. Click Add Environment again, select Production, name it "Production Environment", then select the Akamai adapter. Click Create, then click Close.

## Build a dev library

Despite all the changes and configurations made so far, no code has actually been published. Creating a library, roughly translated as a collection of changes, allows the publishing of code to be used on your site.

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. Click the Launch property that you intend to implement on your site.
3. Click the Publishing tab, then click Add New Library.
4. Name the library 'Initial changes', and select your development environment.
5. Click Add All Changed Resources, which automatically lists Adobe Analytics, Identity Service, and Core.
6. Click Save.
7. Back on the publishing workflow screen, click the dropdown next to your new library, and click Build for Development. After a few seconds, the yellow dot on the library turns green, indicating the build was successful.
8. Go to the Environments tab, then click on your development environment.
9. Under 'Install Launch', copy the code blocks and provide them to your organization's website owners.

## Install Launch on your website's development environment

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. This code is commonly placed in the site's overarching template. A blank page only containing implementation code would look like the following:

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
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## Troubleshooting

**Attempting to build fails.**

A common reason is because elements already exist in other libraries pushed to staging or production. When initially creating libraries, ensure only changed resources are added to the library.

## Documentation and additional resources

- [Getting Started with Launch](https://experienceleague.adobe.com/docs/launch/using/intro/get-started/quick-start.html): Learn the basic workflow of Launch
- [Launch Publishing](https://experienceleague.adobe.com/docs/launch/using/reference/publish/overview.html): Learn more about publishing and environments

## Next Steps

[Validate your Analytics implementation and publish to production](validate-publish-prod.md): Start getting value out of Adobe Analytics.
