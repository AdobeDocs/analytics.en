---
description: Measures the amount of income generated through all of your products over a specific time period.
solution: Analytics
title: Revenue
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
---

# Revenue

Measures the amount of income generated through all of your products over a specific time period.

Use Revenue to view the general success and trend of your site. You can also use it to single out periods where your site was particularly successful, to find the source, and use that for future campaigns.

## General Properties of Report {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* There are requirements that must be met in order for this report to successfully collect data. The following must occur within the same image request:

    * A [!UICONTROL purchase] event must fire in the `s.events` variable.
    
    * The `products` variable must be defined with a number in the price field.
    * For example, this would pass $35.99 into the revenue report:     
    
      ```js    
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js    
       s.events="purchase"
      ```

* When more than one product is present in the [!UICONTROL s.products] variable, all count towards the revenue report. For example, [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] would pass $9 in revenue to reporting.

  >[!NOTE]
  >
  >Revenue is not multiplied if quantity is increased in a single product. For example, [!DNL s.products="Womens;Socks;5;4.50"] does not pass $22.50 into reporting, it passes $4.50. Make sure your implementation passes the total revenue for the quantity listed ( [!DNL s.products="Womens;Socks;5;22.50"]).

* [!UICONTROL Revenue] rounds the total amount for a time period to the nearest currency value. It does not round each individual product or hit.
* Because Analytics round each day to the nearest whole currency, comparing the sum of each day to the monthly total is off by a very small amount. This is because the monthly total is not the sum of each rounded day, it is the absolute sum rounded to the nearest whole currency.
* You can create a report that does not round revenue to the nearest whole currency by using a [calculated metric](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/).
* Unless using the `purchaseID` variable, users refreshing the page may inflate revenue as it sends this data to Adobe multiple times.
* Hourly breakdowns are based on the report suite's time zone.
* This report does not contain line items. It can only be viewed in trended format.
* Granularity of hour, day, week, month, quarter, and year can be applied. These granularities are available depending on the reporting date range.
* This report can be broken down by the following reports (depending on organization and report suite settings):

    * [!UICONTROL Time Spent per Visit] report.
    * [!UICONTROL Pages and Site Sections] report.
    * [!UICONTROL Videos] report.
    * [!UICONTROL Page Depth and Entry Pages] report.
    * Most [!UICONTROL Traffic Sources]reports, including [!UICONTROL Search Keywords], [!UICONTROL Search Engines], and [!UICONTROL Referring Domains] reports.
    
    * [!UICONTROL Tracking Code] report and all associated classifications reports.
    * [!UICONTROL Products variable] report and all associated classifications reports. Also [!UICONTROL Categories] reports.
    
    * Almost all [!UICONTROL Visitor Profile] reports, excluding [!UICONTROL GeoSegmentation] reports.
    
    * All [!UICONTROL Custom Conversion] variables reports with basic subrelations.

* Breakdowns are not available by hour.

## Product-Specific Properties {#section_ED87FFD020634453AABE86B0248BE69B}

* This report can be accessed by going to **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] breakdowns can be found under [!UICONTROL Finding Methods].

* This report can be accessed by going to **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to all previously listed breakdowns, [!UICONTROL First and Last Touch Marketing Channel] breakdowns are available.

* This report can also be accessed by going to **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* This report can utilize segments.

* You can break down each item in this report by all other reports and variables, allowing you to see breakdowns by any granularity that you'd like.
* You can use all [!UICONTROL conversion] and [!UICONTROL traffic] metrics alongside [!UICONTROL Revenue]. You can use different allocation for all [!UICONTROL conversion] metrics.

* This report can utilize multiple highly advanced segments.

If this report is not available in the specified location, check with your administrator. They may have changed the default name or menu structure to better serve your organization's unique needs.
