---
title: Implement Adobe Analytics
description: Implement Adobe Analytics on your site, property, or application.
---

# Implement Adobe Analytics

![Banner](../../assets/doc_banner_implement.png)

Adobe requires code on your site or app to send data to Adobe's data collection servers. The following steps indicate how a typical implementation works.

1. When a visitor comes to your site, a request is made to your web server.

   ![Data collection 1](assets/how-data-is-collected-1.png)

2. Your site's web server sends the page code information, and the page displays in the browser.

   ![Data collection 2](assets/how-data-is-collected-2.png)

3. The page loads, and the Analytics JavaScript code runs.

   ![Data collection 3](assets/how-data-is-collected-3.png)

   The JavaScript code sends an image request Adobe data collection servers. Page data that you defined in your implementation are sent as part of a query string in this image request.

4. Adobe returns a transparent pixel image.

   ![Data collection 4](assets/how-data-is-collected-4.png)

5. Adobe servers store collected data in a *report suite*.

   ![Data collection 5](assets/how-data-is-collected-5.png)

6. Report suite data populates the reports that you can access in a web browser.

   ![Data collection 6](assets/how-data-is-collected-6.png)

   **Example report:**

   ![Summary project](assets/two-months-summary-project.png)

   The JavaScript code execution occurs quickly and does not noticeably affect page load times. This approach allows you to count pages that were displayed when a visitor clicked **[!UICONTROL Reload]** or **[!UICONTROL Back]** to reach a page, because the JavaScript runs even when the page is retrieved from cache.

Adobe Analytics requires code within your website, mobile app, or other application to send data to data collection servers. There are several methods to implement this code, depending on platform and your organization's needs.

* **Adobe Experience Platform Launch**: The standardized and recommended method to implement Adobe Analytics. Place a loader tag on each page, and use Launch's interface to determine how each variable is defined.
* **Dynamic Tag Management**: The predecessor to Launch. DTM uses a similar interface to implement Analytics, but is no longer updated and is not as flexible. Adobe recommends using Launch for implementing Adobe Analytics.
* **Legacy JavaScript**: The historical manual method to implement Adobe Analytics. Outlines variables and settings used in an implementation, which can be useful for Launch implementations using rules with custom code.
* **Mobile SDK**: Dedicated libraries to easily send data to Adobe from within your mobile app.

## Key Analytics Implementation articles

* [Adobe Debugger](validate/debugger.md)
* [Create a property in Experience Platform Launch](launch/create-analytics-property.md)
* [Choose an implementation method](c-implementation-methods/choose-implementation-method.md)
* [AppMeasurement library release notes](appmeasurement-release-notes/c-release-notes-mjs.md)

## More Analytics user guides

[Analytics User Guides](/help/landing/home.md)

## Key Analytics resources

* [Contact Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html)
* [Analytics Forum](https://forums.adobe.com/community/experience-cloud/analytics-cloud/analytics)
* [Adobe Analytics Resources](https://forums.adobe.com/message/10660755)
* [Experience League](https://landing.adobe.com/experience-league/)
