---
title: Implement Adobe Analytics
description: Implement Adobe Analytics on your site, property, or application.
feature: Implementation Basics
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
role: Admin, Developer, Leader, User
---
# Implement Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe requires code on your site or app to send data to Adobe's data collection servers. The following steps indicate how a typical implementation works.

1. When a visitor comes to your site, a request is made to your web server.
2. Your site's web server sends the page code information, and the page displays in the browser.
3. The page loads, and the Analytics JavaScript code runs.
   The JavaScript code sends an image request to Adobe data collection servers. Page data that you defined in your implementation are sent as part of a query string in this image request.

4. Adobe returns a transparent pixel image.
5. Adobe servers store collected data in one or more *report suites*.
6. Report suite data populates the reports that you can access in a web browser.

The JavaScript code execution occurs quickly and does not noticeably affect page load times. This approach allows you to count pages that were displayed when a visitor clicked **[!UICONTROL Reload]** or **[!UICONTROL Back]** to reach a page, because the JavaScript runs even when the page is retrieved from cache.

Adobe Analytics requires code within your website, mobile app, or other application to send data to data collection servers. There are several methods to implement this code, depending on platform and your organization's needs.

## Website implementation methods

For your **website**, the following implementation methods are available:

* **Web SDK extension**: The standardized and recommended method to implement Adobe Analytics for new customers. Add the **Adobe Experience Platform Web SDK extension** in Adobe Experience Platform Data Collection **Tags**, then place a loader tag on each page. The tag sends data to the Adobe Experience Platform **Edge Network**, which forwards that data to Adobe Analytics.
![Web SDK extension](./assets/websdk-extension-implementation.png)
See [How to implement Adobe Analytics using the Adobe Experience Platform Web SDK extension.](./aep-edge/overview.md) for more information.

* **Web SDK**: You can manually load the Web SDK libraries on your site if you do not want to use Adobe Experience Platform Data Collection. Reference the Web SDK library (`alloy.js`) on each page, and send the desired tracking calls to the Adobe Experience Platform **Edge Network** in a format convenient to your organization. The Edge Network forwards that data to Adobe Analytics.
![Web SDK](./assets/websdk-implementation.png)
See [How to implement Adobe Analytics using the Adobe Experience Platform Web SDK](./aep-edge/overview.md) for more information.

* **Analytics extension**: Add the **Adobe Analytics extension** in Adobe Experience Platform Data Collection **Tags**, then place a loader tag on each page. The tag sends data directly to Adobe Analytics. Use this implementation method if you want the convenience of Tags, but do not want to use the Edge Network infrastructure.
![Adobe Analytics extension](./assets/analytics-extension-implementation.png)
See [How to implement Adobe Analytics using the Analytics extension](launch/overview.md) for more information.

* **Legacy JavaScript**: The historical manual method to implement Adobe Analytics. Reference the AppMeasurement library (`AppMeasurement.js`) on each page, then set variables and settings in JavaScript. 
![How to implement Adobe Analytics using Legacy JavaScript](./assets/appmeasurement-implementation.png)
This implementation method can be useful for implementations using custom code and is ideal for implementation types not offered elsewhere, such as for [AMP pages](other/amp.md).

The following decision flow can help you select an implementation method:

![A decision tree for selecting an implementation method, as described in this section.](./assets/decision-tree.png)


>[!TIP]
>
>Contact your Adobe Account Team for advice and best practices on which implementation to choose based on your current situation.

## Mobile app implementation methods

For your **mobile app**, the following implementation methods are available:

* **Mobile SDK extension**: The standardized and recommended method to implement Adobe Analytics in your mobile app. Use dedicated libraries to easily send data to Adobe from within your mobile app. Add the **Adobe Experience Platform Mobile SDK extension** in Adobe Experience Platform Data Collection **Tags**, then implement the Mobile SDK library in your app. You can use the SDK to import libraries, register extensions, and load the tag configuration. Send data to the Adobe Experience Platform **Edge Network**; Edge then forwards that data to Adobe Analytics.
![Mobile SDK extension](./assets/mobilesdk-extension.png)

    See [Implement Adobe Analytics using the Adobe Experience Platform Mobile SDK](../implement/aep-edge/mobile-sdk/overview.md) for more information.

* **Analytics extension**: Add the **Adobe Analytics extension** in Adobe Experience Platform Data Collection **Tags**, and implement the Mobile SDK library in your app. You can use the SDK to import libraries, register extensions, and load the tag configuration. This implementation method sends data directly to Adobe Analytics. It is recommended if you want the convenience of Adobe Experience Platform Data Collection, but do not want to use Adobe's Experience Platform Edge network infrastructure.
![Analytics extension](./assets/mobilesdk-analytics-extension.png)

    See [Implement Adobe Analytics using the Analytics extension](../implement/aep-edge/mobile-sdk/overview.md) for more information.


>[!CAUTION]
>
>Support for Version 4 Mobile SDKs ended on August 31, 2021. See [Version 4 Mobile SDKs end-of-support FAQ](https://developer.adobe.com/client-sdks/resources/upgrade-platform-sdks/v4-faq/) for more information.

## Key Analytics Implementation articles

* [Take charge of an existing Adobe Analytics implementation](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Create a tag property in Experience Platform](launch/create-analytics-property.md)
* [AppMeasurement updates](appmeasurement-updates.md)

## More Analytics user guides

[Analytics User Guides](https://experienceleague.adobe.com/docs/analytics.html)

## Key Analytics resources

* [Contact Customer Care](https://experienceleague.adobe.com/?support-solution=Analytics#support)
* [Analytics Forum](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics/ct-p/adobe-analytics-community)
* [Adobe Analytics Resources](https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/adobe-analytics-resources/m-p/276666)
