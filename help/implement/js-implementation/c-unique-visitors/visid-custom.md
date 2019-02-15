---
description: You can implement a custom method to identify visitors by setting the s.visitorID variable.
keywords: Analytics Implementation
seo-description: You can implement a custom method to identify visitors by setting the s.visitorID variable.
seo-title: Custom Visitor ID
solution: Analytics
title: Custom Visitor ID
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
---

# Custom Visitor ID

You can implement a custom method to identify visitors by setting the s.visitorID variable.

A custom Visitor ID can be used on sites where you have unique way to identify visitors. An example of this is an ID generated when a user logs in to web site using a user name and password.

Should you have the ability to derive and manage the [!UICONTROL visitor IDs] of your users, you can use the following methods to set the ID: 

|  Method  | Description  |
|---|---|
|  [s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) variable  | If JavaScript is used on the browser, or if you are using any other AppMeasurement library, you can set the visitor ID in a data collection variable.  |
|  Query string parameter on the image request  | This lets you pass the [!UICONTROL visitor ID] to Adobe via the [!UICONTROL vid query string] parameter on a hard-coded image request.  |
|  Data Insertion API  | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers.  |
|  URL re-writing and VISTA  | Some deployment architectures provide support for using URL re-writing to maintain session state when a cookie cannot be set. In such cases, Adobe engineering services can implement a [!DNL VISTA] rule that would look for the session value in the URL of the page, then format and place into the [!UICONTROL visid] values.  |
>[!CAUTION]
>**Custom Visitor IDs must be sufficiently granular/unique**: An invalid implementation of custom Visitor IDs can lead to incorrect data and poor reporting performance. If the custom Visitor ID is not unique or granular enough, or is incorrectly set to a common default value such as the string “NULL”, or “0”, the hits from many different visitors will be seen by Adobe Analytics as a single visitor. This situation results in incorrect data, with visitor counts being too low and segments not working correctly for that visitor. An insufficiently granular custom Visitor ID also prevents the data from being properly spread across nodes in the Analytics reporting cluster. In this situation, one node becomes overloaded and cannot process report requests in a timely fashion. Eventually all reporting for the report suite will fail. <br>Poorly implemented custom Visitor IDs might not immediately impact reporting performance because Analytics can often handle several months’ worth of unbalanced data; however, over time a poorly implemented custom Visitor ID value can become problematic to the point of requiring Analytics to disable processing for affected report suites.</br><br>Implementers should follow the guideline that a single custom Visitor ID value should never be credited for more than 1% of your report suite’s traffic. Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
