---
description: Learn how visits to your web site become a report in Adobe Analytics.
keywords: Analytics Implementation;data collection
seo-description: Learn how visits to your web site become a report in Adobe Analytics.
seo-title: Data Collection
solution: Analytics
title: Data Collection
topic: Developer and implementation
uuid: d0d6098d-113e-4cf5-bb89-e435f7b6b1af
index: y
internal: n
snippet: y
---

# Data Collection

Learn how visits to your web site become a report in Adobe Analytics.

 Adobe has created multiple ways to send data into Analytics. These methods include tracking information in real-time from:

* Applications that can access the Internet 
* Campaigns 
* Client-server applications 
* Emails 
* Mobile devices 
* Web-based kiosks 
* Web sites

<!-- 

<p>Need to reconcile with Data Collection topics in the user guide, in this guide, and in reference. </p>

 -->

1. When a visitor comes to your site, a request is made to your web server.

   ![](assets/how-data-is-collected-1.png)

1. Your site's web server sends the page code information, and the page displays in the browser.

   ![](assets/how-data-is-collected-2.png)

1. The page loads, and the Analytics JavaScript code runs.

   ![](assets/how-data-is-collected-3.png)

   The JavaScript code sends an image request to the Adobe server, passing the variables, metrics, and page data that you defined in your implementation.

   **Example JavaScript Code:** The JavaScript code is placed within the body tags of a web page:

   ![](assets/code-example-geometrixx.png)

   **Example Image Request:** A snippet of an image request with the page name outlined:

   ![](assets/image-request-snippet.png)

   >[!NOTE]
   >
   >Each image request contains a random number string to prevent browser caching and ensure that subsequent image requests are made by the browser.

1. Adobe returns a transparent pixel image.

   ![](assets/how-data-is-collected-4.png)

   The code automatically collects additional details (such as operating system, browser type, browser height and width, IP address, and browser language). 

1. Adobe servers store web analysis data in *`report suites`* (your data repository).

   ![](assets/how-data-is-collected-5.png)

   A [report suite](https://marketing.adobe.com/resources/help/en_US/reference/?f=report_suites_admin) defines the complete, independent reporting on a chosen website, set of websites, or subset of web pages. 

1. Report suite data populates the reports that you can access in a web browser.

   ![](assets/how-data-is-collected-6.png)

   **Example report:**

   ![](assets/two-months-summary-project.png)

   The JavaScript code execution occurs quickly and does not noticeably affect page load times. This approach allows you to count pages that were displayed when a visitor clicked **[!UICONTROL Reload]** or **[!UICONTROL Back]** to reach a page, because the JavaScript runs even when the page is retrieved from cache. 

For more details, see:

* [Data Collection](../../implement/js-implementation/data-collection/query-parameters.md)
* [Create a Data Element](../../implement/c-implement-with-dtm/t-data-element.md#task_962EF08CE2AE49B3B739295F6E4792C2)
* [Data Warehouse](https://marketing.adobe.com/resources/help/en_US/reference/data_warehouse.html)
* [Ad Hoc Analysis](https://marketing.adobe.com/resources/help/en_US/dsc/c_getting_started.html)
* [Data Sources](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_datasources.html)
* [Data Connectors](https://marketing.adobe.com/resources/help/en_US/whitepapers/ftp/ftp_genesis.html) 
* [Analytics Data Feed](/help/export/analytics-data-feed/c-getstarted/data-feed-overview.md)
  
>[!MORE_LIKE_THIS]
>       
>* [Experience Cloud Debugger](/help/implement/impl-testing/debugger.md)  