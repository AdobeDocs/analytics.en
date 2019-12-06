---
description: To begin using Analytics, data must be sent to a report suite to display in reporting.
keywords: Analytics Implementation;javascript;javascript implementation;appmeasurement;download appmeasurement;Identity Service;visitorapi.js;caching;appmeasurement compression
title: JavaScript implementation overview
topic: Developer and implementation
uuid: bb661d8c-faf9-4454-ac3c-0c1a4c0a9336
---

# JavaScript implementation overview

To begin using Analytics, data must be sent to a report suite to display in reporting.

The easiest and recommended way to send data to [!DNL Analytics] is by using [Launch](/help/implement/implement-with-launch/create-analytics-property.md). However, in some cases, you might want to implement Analytics using the older JavaScript method.

> [!NOTE] This section describes the legacy method of implementing Analytics. All Analytics customers have access to [Launch](/help/implement/implement-with-launch/create-analytics-property.md), which is the standard method to deploy Experience Cloud tags.

## Implementation Steps {#section_73961BAD5BB4430A95E073DE5C026277}

To successfully implement a page with code to collect data, you must have access to your hosting servers to upload new content to your website. It is also useful to have an existing site to implement code.

The following steps walk you through a basic Analytics implementation.

| Task | Description |
|--- |--- |
|1. Download AppMeasurement for JavaScript and the ID service.|Log in to Analytics via the Experience Cloud. The download file is available at Analytics > Admin > Code Manager.  This download zip contains several files.  AppMeasurement.js  and  VisitorAPI.js  are the relevant files when implementing Analytics.|
|2. Set up the Identity Service. (Formerly Visitor ID service)| See [Set up the Identity Service for Analytics](https://docs.adobe.com/content/help/en/id-service/using/home.html)|
|3. Update `AppMeasurement.js`.|Copy the [example AppMeasurement.js code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_4351543F2D6049218E18B48769D471E2) and paste it at the beginning of your `AppMeasurement.js` file. At a minimum, update the following variables:<ul><li>s.account="INSERT-RSID-HERE"</li><li>s.trackingServer="INSERT-TRACKING-SERVER-HERE"</li><li>s.visitorNamespace = "INSERT-NAMESPACE-HERE"</li><li>s.visitor = Visitor.getInstance("INSERT-MCORG-ID-HERE")</li></ul><br>See [Correctly populate the trackingServer and trackingServerSecure variable](https://helpx.adobe.com/analytics/kb/determining-data-center.html) or contact Client Care if you are unsure about any of these values. If they are not set correctly, data will not be collected by your implementation.</br>|
|4. Host `AppMeasurement.js` and `VisitorAPI.js`.|These core JavaScript files must be hosted on a web server that is accessible to all pages on your site. You need the path to these files in the next step.|
|5. Reference `AppMeasurement.js` and `VisitorAPI.js`  on all site pages.|<ul><li>Include the Visitor ID Service by adding the following line of code in the `head` or `body` tag on each page. (`VisitorAPI.js` must be included before `AppMeasurement.js`).<br>`script language="JavaScript" type="text/javascript" src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/VisitorAPI.js"`</br></li><li>Include AppMeasurement for JavaScript by adding the following line of code in the `head` or `body` tag on each page:<br>`script language="JavaScript" type="text/javascript"  src="https://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/AppMeasurement.js"`</br></li></ul>|
|6. Update and deploy page code.|Copy the [Example Page Code](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasure-mjs-pagecode.html#section_042412C29CC249E298F19B2BC2F43CE7) and paste it just after the opening `body` tag on each page you want to track. At a minimum, update the following variables:<ul><li>var s=s_gi("INSERT-RSID-HERE")</li><li>s.pageName="INSERT-NAME-HERE" (for example, s.pageName=document.title)</li></ul>|
|7. Use the Experience Cloud Debugger to verify that data is being sent.|Install the [Experience Cloud Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html#concept_B26FFE005EDD4E0FACB3117AE3E95AA2). After it is installed, load a page where you have deployed page code and then open the debugger. The debugger displays details about the collection data that was sent.|

## Caching {#section_4E2D1D962DF046418134C43CFC49AD4A}

The JavaScript file is cached in the visitor's browser after it is initially loaded, and is typically downloaded no more than once per session. The file is not downloaded on each page, even though it is used by every page on the site. On most websites, users average more than a few page views per session, so transferring JavaScript that is used multiple times into this file can result in less overall downloaded data.

## JavaScript for AppMeasurement Compression {#section_C10BBC84C81C414088F97363D29E021B}

If you are concerned about page weight (size) of H Code (AppMeasurement for JavaScript 1.0 is pre-compressed), Adobe recommends that you consider compressing the file using GZIP. GZIP is supported by all major browsers and offers better performance than JavaScript compression to compress and decompress the core [!DNL s_code.js] JavaScript file.

The following links help explain how you can use GZIP functionality on your site to handle compression of the [!DNL s_code.js] JavaScript code:

[Apache Module mod_deflate](https://httpd.apache.org/docs/2.0/mod/mod_deflate.html)

[Enabling gzip compression with Tomcat and Flex](https://www.cubicleman.com/2007/04/06/enabling-gzip-compression-with-tomcat-and-flex/) 
