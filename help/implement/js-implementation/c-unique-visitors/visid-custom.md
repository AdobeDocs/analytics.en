---
description: You can implement a custom method to identify visitors by setting the s.visitorID variable.
keywords: Analytics Implementation
seo-description: You can implement a custom method to identify visitors by setting the s.visitorID variable.
seo-title: Custom Visitor ID
solution: Analytics
title: Custom Visitor ID
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
index: y
internal: n
snippet: y
---

# Custom Visitor ID

You can implement a custom method to identify visitors by setting the s.visitorID variable.

A custom Visitor ID can be used on sites where you have unique way to identify visitors. An example of this is an ID generated when a user logs in to web site using a user name and password.

Should you have the ability to derive and manage the [!UICONTROL visitor IDs] of your users, you can use the following methods to set the ID: 

|  Method  | Description  |
|---|---|
|  [s.visitorID](visitorID.md#concept_CD273CC915CC4ABD8F52E4209FF9557E) variable  | If JavaScript is used on the browser, or if you are using any other AppMeasurement library, you can set the visitor ID in a data collection variable.  |
|  Query string parameter on the image request  | This lets you pass the [!UICONTROL visitor ID] to Adobe via the [!UICONTROL vid query string] parameter on a hard-coded image request.  |
|  Data Insertion API  | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the <visitorid/> XML element to Adobe collection servers from your servers.  |
|  URL re-writing and VISTA  | Some deployment architectures provide support for using URL re-writing to maintain session state when a cookie cannot be set. In such cases, Adobe engineering services can implement a [!DNL VISTA] rule that would look for the session value in the URL of the page, then format and place into the [!UICONTROL visid] values.  |

