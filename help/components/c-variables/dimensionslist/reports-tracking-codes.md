---
description: Measures how various advertising tracking codes affect different conversion events on your site. This report can be used to measure what specific campaigns are performing better for different success events, or to see how campaigns are helping or hindering your site's initiatives, such as which campaigns are generating the most revenue.
solution: Analytics
title: Tracking Codes
topic: Reports
uuid: c893d592-10fd-4b40-84b3-8c8949a67b25
---

# Tracking Codes

Measures how various advertising tracking codes affect different conversion events on your site. This report can be used to measure what specific campaigns are performing better for different success events, or to see how campaigns are helping or hindering your site's initiatives, such as which campaigns are generating the most revenue.

 **General Properties**

* This report references data directly from the [s.campaign](/help/implement/js-implementation/c-variables/page-variables.md) variable implemented on your website.
* The variable this report is based on is a [conversion variable](/help/admin/admin/conversion-var-admin/conversion-var-admin.md). Meaning, it can persist beyond the page view and associate itself with metrics within its specified expiration.
* The report's default metric is Revenue. You can change this default value in the [!UICONTROL Report Suite Manager] in [!UICONTROL Admin Tools]. ( **[!UICONTROL Edit Settings]** > **[!UICONTROL Individual Report Settings]** > **[!UICONTROL Default Metrics]**.) 

* This report can be viewed in both trended and ranked formats.
* This report can use a search filter to locate specific line items.
* The [!UICONTROL Campaigns] and [!UICONTROL Creative Elements] reports are classifications based on this report, and are automatically created with each report suite.

* SAINT Classifications can be used in this report, allowing you to rename and consolidate line items.
* You can break down this report by the following reports (depending on organization and report suite settings):

    * Time Spent per Visit 
    * Pages and Site Sections reports, with all related classifications 
    * Page Depth, Entry Pages and Original Entry Pages 
    * Most traffic sources reports 
    * Visit Number and Customer Loyalty 
    * Many Visitor Profile and Technology reports, excluding GeoSegmentation 
    * All custom conversion variables

* The following metrics can be utilized in this report (depending on organization and report suite settings):

    * Click-throughs: the number of times the *`s.campaign`* variable is defined 
    * All standard eCommerce metrics: Revenue, Orders, Units, Carts, Cart Views, Checkouts, Cart Additions, Cart Removals.
    * All custom events: Events 1-80, and Events 81-100 if on H22 code or higher 
    * Visits and Visitors: availability is dependent on organization and report suite. Contact your Account Manager for additional information.

**Reports & Analytics Properties**

* Click **[!UICONTROL Conversion]** > **[!UICONTROL Campaigns]** > **[!UICONTROL Tracking Code]** to locate this report, unless the menu is customized.

* This report can also be broken down by all [List Variables](https://marketing.adobe.com/resources/help/en_US/sc/implement/list_var.html).
* Page Views, Visits, and Unique Visitors are available as metrics.
* This report can make use of segments.

**Ad Hoc Analysis Properties**

* In addition to most out-of-the-box conversion variables, you can break down the Tracking Code report by all other reports within the reporting interface.
* In addition to eCommerce and custom events, you can use all conversion and traffic metrics, as well as use different allocation for all conversion metrics.
* This report can use advanced segments.

