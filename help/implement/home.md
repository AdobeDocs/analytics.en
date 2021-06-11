---
title: Implement Adobe Analytics
description: Implement Adobe Analytics on your site, property, or application.
exl-id: 2b629369-2d69-4dc6-861a-ff21a46d39e0
---
# Implement Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe requires code on your site or app to send data to Adobe's data collection servers. The following steps indicate how a typical implementation works.

1. When a visitor comes to your site, a request is made to your web server.
2. Your site's web server sends the page code information, and the page displays in the browser.
3. The page loads, and the Analytics JavaScript code runs.
   The JavaScript code sends an image request Adobe data collection servers. Page data that you defined in your implementation are sent as part of a query string in this image request.

4. Adobe returns a transparent pixel image.
5. Adobe servers store collected data in one or more *report suites*.
6. Report suite data populates the reports that you can access in a web browser.

   The JavaScript code execution occurs quickly and does not noticeably affect page load times. This approach allows you to count pages that were displayed when a visitor clicked **[!UICONTROL Reload]** or **[!UICONTROL Back]** to reach a page, because the JavaScript runs even when the page is retrieved from cache.

Adobe Analytics requires code within your website, mobile app, or other application to send data to data collection servers. There are several methods to implement this code, depending on platform and your organization's needs.

* **Adobe Experience Platform Launch**: The standardized and recommended method to implement Adobe Analytics. Place a loader tag on each page, and use Launch's interface to determine how each variable is defined.
* **Dynamic Tag Management**: Dynamic Tag Management has been end-of-lifed.
* **Legacy JavaScript**: The historical manual method to implement Adobe Analytics. Outlines variables and settings used in an implementation, which can be useful for Launch implementations using rules with custom code.
* **Mobile SDK**: Dedicated libraries to easily send data to Adobe from within your mobile app.

## Key Analytics Implementation articles

* [Take charge of an existing Adobe Analytics implementation](/help/implement/prepare/existing-implementation.md)
* [Adobe Debugger](validate/debugger.md)
* [Create a property in Experience Platform Launch](launch/create-analytics-property.md)
* [AppMeasurement updates](appmeasurement-updates.md)

## More Analytics user guides

[Analytics User Guides](/help/landing/home.md)

## Key Analytics resources

* [Contact Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Analytics Forum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics Resources](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
