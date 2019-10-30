---
description: Provides comprehensive, accurate, and detailed analysis of customer activity. Metrics such as campaign management, sales cycle, customer fallout, and customer conversion let you measure e-commerce transactions, sources of sales, advertising effectiveness, customer loyalty, and more.
seo-description: Provides comprehensive, accurate, and detailed analysis of customer activity. Metrics such as campaign management, sales cycle, customer fallout, and customer conversion let you measure e-commerce transactions, sources of sales, advertising effectiveness, customer loyalty, and more.
seo-title: Conversion
solution: Analytics
title: Conversion
topic: Reports
uuid: 457d3033-6562-4fba-8c2e-0e7a9be44bfd
---

# Conversion

Provides comprehensive, accurate, and detailed analysis of customer activity. Metrics such as campaign management, sales cycle, customer fallout, and customer conversion let you measure e-commerce transactions, sources of sales, advertising effectiveness, customer loyalty, and more.

For example, if you want to see what type of internal campaigns on your home page might result in purchases, you first must capture the internal tracking codes and set persistence to a period of one visit for the *`s.eVar`* that captures internal campaigns. When a success event is completed (like purchase), the credit for that success is given to any Conversion Variables that are persistent on the visitor, such as Internal Campaign ID. By running the [!UICONTROL Internal Campaign Report], you can see which campaign generated the most onsite conversion.

Some out-of-the-box reports contain both Traffic and Conversion metrics (such as the [!UICONTROL Search Engine] reports). However, [!UICONTROL Traffic] and [!UICONTROL Conversion] reports are unique to your organization and are displayed in the **[!UICONTROL Traffic]** and **[!UICONTROL Conversion]** menus.

**Report Properties**

* [!UICONTROL Custom Conversion] reports are based on eVars (conversion variables).
* Conversion variables can persist beyond the page view and be associated with metrics within its specified expiration.
* The reports' default metrics are revenue. To change default metrics, see [Selecting Default Report Metrics](https://marketing.adobe.com/resources/help/en_US/sc/user/t_metrics_set_default.html).
* View these reports in both trended and ranked formats.
* You can use Classifications in these reports, to rename and consolidate line items.
* These reports can be broken down by the following if basic subrelations are enabled:

    * Campaigns and Products, with all related classifications 
    * Customer Loyalty 
    * All fully-subrelated eVars

* Additional reports are available to break down when full subrelations are enabled:

    * Time Spent per Visit 
    * Pages and Site Sections, with all related classifications 
    * Entry Pages 
    * Almost all Traffic Sources reports 
    * Visit Number 
    * Many Visitor Profile and Technology reports 
    * All other eVars 
    * Marketing Channels First and Last Touch

* The following events can be used as metrics:

    * Instances, the number of times the eVar was defined 
    * All standard eCommerce metrics: Revenue, Orders, Units, Carts, Cart Views, Checkouts, Cart Additions, Cart Removals.
    * All custom events: Events 1-80, and Events 81-100 if on H22 code or higher 
    * Visits and Visitors: Available depending on organization and report suite. Contact your Account Manager for additional details

* The location of each [!UICONTROL Custom Conversion] report varies depending on the eVar's numeric assigned value. Generally, they can be found under the [!UICONTROL Custom Conversion] folder (provided the menu is not customized).

