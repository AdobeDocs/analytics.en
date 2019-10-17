---
description: Custom traffic variables, also called props (s.prop) or property variables, are counters that count the number of times each value is sent into Analytics.
keywords: Analytics Implementation;Traffic prop;prop;conversion;evar;s.prop;custom conversion insight;traffic variable
seo-description: Custom traffic variables, also called props (s.prop) or property variables, are counters that count the number of times each value is sent into Analytics.
seo-title: Overview of props and eVars
solution: Analytics
title: Overview of props and eVars
topic: Developer and implementation
uuid: 522cab2b-1ef8-4f10-b216-c82b21431487
---

# Overview of props and eVars

Custom traffic variables, also called props (s.prop) or property variables, are counters that count the number of times each value is sent into Analytics.

When determining which variables are assigned where, it is important to understand the differences between Prop and eVar functionality. Understanding these differences allows your organization to decide which type of variable is best to use. For detailed information, see [Comparing Props and eVars](/help/implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md).

Props also let you correlate custom data with specific traffic-related events. These variables are embedded in the [!DNL Analytics] code on each page of your website. Through [!UICONTROL s.prop] variables, [!DNL Analytics] lets you create custom reports, unique to your organization, industry, and business objectives.

For example, if you are an automobile manufacturer, you may be interested in seeing "Most Popular Car Model" to complement your "Pages" report. You can accomplish this by allocating one of your traffic properties to represent car model. Then implement your code to pass in car model on the appropriate pages.

>[!NOTE]
>
>[!DNL Analytics] supports up to 75 [!UICONTROL s.prop] variables.

Props are used in pathing reports or in correlation reports. For example, [!UICONTROL property] variables can be used to show content type, sub-section, or template name. The resulting [!UICONTROL Custom Traffic] reports show which content type, sub-section, or template is viewed most often.

There are endless business questions that can be answered through the custom traffic variables, depending on what you are capturing from your website. The following list contains a few common goals and objectives:

* Understanding user navigation through the website 
* Understanding internal user search behavior 
* Segmenting traffic by navigation or category 
* Segmenting visitor behavior by demographics

eVars (or [!UICONTROL Custom Conversion Insight] variables) are used to identify how well specific attributes or actions contribute to success events on your site. For example, for a media site, eVars may be used to identify how well internal promotions bring visitors to register. When a visitor clicks on the internal promotion, an eVar can be used to store a unique identifier for that promotion. When the same visitor completes registration and a custom success event is fired, the original unique identifier receives credit for the registration event.

In a conversion site, eVars may be used to track how logged-in visitors compare to non-logged in visitors in completing a purchase. When a visitor logs in, an eVar is set to "logged in." When that visitor reaches the checkout page, the checkout event is attributed to the "logged in" value. When a visitor reaches the Thank You page after purchasing, the products and purchase amounts are attributed to the "logged in" value. The resulting [!UICONTROL Custom eVar] report shows the total number of checkouts and orders for "logged in" and "non-logged in" visitors.

For additional information, see [Traffic Variable](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html) in the Analytics Help and Reference.

For information about setting up properties in Digital Tag Management, see [Create Web Property](/help/implement/c-implement-with-dtm/t-create-web-property.md). 
