---
title: H Code JavaScript implementation overview
description: Learn the workflow to implement H Code on your site.
exl-id: cf83d8fe-a3b1-4e65-a86a-7eeaf555651b
---
# H Code JavaScript implementation overview

>[!IMPORTANT]
>
>This version of data collection is no longer supported. Upgrade to either [tags in Adobe Experience Platform](../../launch/overview.md) or [AppMeasurement for JavaScript](../overview.md).

You must have access to your hosting servers to successfully implement a page with code to collect data. The following steps walk you through a basic Analytics H Code implementation.

>[!NOTE]
>
>You must already have an existing copy of `s_code.js` to follow these instructions. Adobe no longer offers an option to download H Code in the Code Manager.

1. **Update core JS file variables**: Edit the `s_code.js` file and make sure the following variables are updated:
   * `s_account` contains the report suite ID that you want to send data to. See
   * `s.trackingServer` contains the location cookies are stored. See [trackingServer](../../vars/config-vars/trackingserver.md).
1. **Host the `s_code.js` file on your site**: This file typically resides with other scripts on your web server.
1. **Reference `s_code.js` on all pages**: Make sure all individual pages call the core JavaScript file, and do so within the HTML `<body>` tag (not the `<head>` tag).

   >[!TIP]
   >
   >H Code requires that the `s_code.js` script is called within the `<body>` tag. This is different from other implementation methods, most of which require script references be in the `<head>` tag.
1. **Define page-specific variables on each page**: Each page should have individual variables defined, such as page name or eVars. Individual variables are typically defined with an inline `<script>` tag on each page.
1. **Use the debugger to verify data collection**: Download and install the [Experience Cloud debugger](../../validate/debugger.md) to make sure data is sent to Adobe, and that page variables are correctly defined.

## Caching

The JavaScript file is cached in the visitor's browser after it is initially loaded, and is typically downloaded no more than once per session. The file is not downloaded on each page, even though it is used by every page on the site. On most websites, users average more than a few page views per session, so transferring JavaScript that is used multiple times into this file can result in less overall downloaded data.

## H Code compression

If you are concerned about the download size of the `s_code.js` file, Adobe recommends compressing the `s_code.js` file using GZIP. GZIP is supported by all major browsers and offers better performance than JavaScript compression. See [Apache Module mod_deflate](https://httpd.apache.org/docs/current/mod/mod_deflate.html) in the Apache documentation.
