---
description: Displays quantitative information about your website, such as how many times visitors looked at certain pages, numbers of overall purchases made from specific pages, when they came, and similar quantitative data. Each of these reports is a metric that you can place in other item-based reports.
seo-description: Displays quantitative information about your website, such as how many times visitors looked at certain pages, numbers of overall purchases made from specific pages, when they came, and similar quantitative data. Each of these reports is a metric that you can place in other item-based reports.
seo-title: Site Metrics reports
solution: Analytics
title: Site Metrics reports
topic: Ad hoc analysis
uuid: 68906079-5c05-4725-b637-0d15315b8c81
index: y
internal: n
snippet: y
---

# Site Metrics reports

Displays quantitative information about your website, such as how many times visitors looked at certain pages, numbers of overall purchases made from specific pages, when they came, and similar quantitative data. Each of these reports is a metric that you can place in other item-based reports.

## Site Metrics reports {#concept_0639CA16551749A693F49ADED4842CCE}

Displays quantitative information about your website, such as how many times visitors looked at certain pages, numbers of overall purchases made from specific pages, when they came, and similar quantitative data. Each of these reports is a metric that you can place in other item-based reports. 

Metric reports are trended over time. You can apply time and day-of-week granularity to these reports. Alternatively, you can analyze the time spent on your site, purchases, revenue, and similar metrics.

The following Site Metrics reports are available in the [!UICONTROL Site Metrics] menu. 

## Page Views Report {#concept_5331AFB6948547F7B8DF367B49360E6B}

<!-- 

c_reports_pageviews.xml

 -->

A trended report that displays the number of times your website pages were viewed for the selected time period (hour, day, week, month, quarter, or year). A [!UICONTROL Page View] is a request for a full page document, rather than an element of a page, such as an image or video. For example, if a single visitor views 15 pages during a visit, 15 page views are counted. If a visitor views the same page three times during a visit, three page views are counted. This report allows you to track page views for each page on your site, as well as an aggregate of page views for your entire site. 

## Visits Report {#concept_50CA55CF2A41430CBC754AEEEE6023A9}

Displays the number of visits made to your entire website during a specified time period. A *visit* is a sequence of page views. A visit begins when a visitor loads a page, and the visit ends after 30 minutes of inactivity. A visit can last several hours, as long as the visitor loads at least one page before the timeout. A visit does not necessarily coincide with a browser session. For example, if a visitor closes the browser, reopens the browser, and comes to your site five minutes later, it is recognized as a continuation of the same visit. This also means that if a visitor stares at one page for 35 minutes, the visit will have closed and processed, and a new visit will start if they click through to another page. Visits are tracked by cookies. A visit is terminated after 12 hours of continuous activity.

<!-- 

c_reports_visits.xml

 -->

In marketing reports and analytics, you can run a [!UICONTROL Visits Report] on a selected page. In ad hoc analysis, you can segment the data to view specific pages. 

## Unique Visitors Report {#concept_39097C54E46C496CBAD537329DB3C84A}

A trended report that shows you the number of unique visitors who accessed your site. Each visitor is counted once regardless of how many times the person visits your website. Adobe uses a patent-pending cookie-handshake technology to distinguish a unique visitor from a return visitor. The cookie handshake overcomes limitations in Internet browser cookie technology.

<!-- 

c_reports_unique_visitors.xml

 -->

You can use this report to:

* See the number of different people that viewed your website during any given time period. 
* View recent traffic patterns and learn how promotions are bringing unique visitors to your site. 
* Compare the number of your unique visitors to the number of page views.

## Visitors Report {#concept_7371DAB5DA474D03A2D1448F151E011B}

Shows the number of unique visitors to your site for a selected hour, day, week, month, quarter, or year. A unique visitor is counted only one time for the selected time frame. Visitors that return to your site are not counted as unique users again until the time frame has passed.

<!-- 

c_reports_visitors.xml

 -->

The total value displayed at the bottom of the table is the sum all of the visits for the specified time period and does not always reflect the number of unique visitors. For example, if you run a [!UICONTROL Daily Unique Visitors Report] with a time frame of several days, the total can include repeat visitors, because the same visitor might return on the next day and be counted again. However, if you run a [!UICONTROL Monthly Unique Visitors Report], the value in the Totals column accurately reflects how many unique visitors came during the month. 

## Time Spent per Visit Report {#concept_5CDB759F9C9B4002A786A71F2BDBB292}

Shows the length of time visitors spend viewing your site during each visit. It also has an Average Time Spent on Site statistic that shows the average time that visitors spent viewing your site.

<!-- 

c_reports_time_spent_per_visit.xml

 -->

Use this report to:

* Identify how long visitors stay on your site. 
* Identify site content and promotions that trigger visitor interest. 
* Find out why you have high traffic but visitors immediately leave.

## Purchases Report {#concept_E3B9AF43CCD24F25A85D05DFB51C4740}

Displays summary data for Revenue, Orders, and Units. You can also view the [!DNL Purchase Conversion Funnel] report.

<!-- 

c_reports_purchases.xml

 -->

* **Revenue**: Lets you view gross profits for selected time periods. Examples could include revenue during the month of March, purchases made last week, or revenue for today. 
* **Orders**: Shows the number of orders made on your website during the specified time period. Orders can have multiple products in them. 
* **Units**: Shows the total units that were ordered for the specified time period. 
* ** Purchase Conversion Funnel**: Ideal for showing conversion events on your site if they occur in a specific order, such as in a retail setting. A funnel report shows you the conversion metrics for each step of the conversion process as well as Orders, Revue, and Units.

## Shopping Cart Report {#concept_6AEC5A6C707B46B790C1A79E72F9A339}

Displays the number of shopping carts that are opened during the specified time period. You can run reports to analyze cart views, additions, removals, and checkouts. A shopping cart is usually opened when a customer selects an item for purchase, but can occur without an item as well.

<!-- 

c_reports_shopping_cart.xml

 -->

You can use the [!UICONTROL Carts Report] to:

* Determine patterns, highs, or lows in the number of carts opened on your site. 
* Examine specific time periods learn more information about the metrics that specifically contributed to the opening of the cart.

## Custom Events Report {#concept_9337B2FB8A3F417BA8689FE7FD64629F}

The conversion actions on your site that you want visitors to complete. These actions might be a registration, a subscription, a lead form completion, a chat initiation, a purchase, a booking, or a finished survey.

<!-- 

c_reports_custom_events.xml

 -->

Because each analytics report suite differs, this set of reports is used differently for each client. A [!UICONTROL Custom Event] report can be used as a counter that shows the number of times an event occurs. For example, if **[!UICONTROL event1]** is set to count the number of times a document is downloaded, then the [!UICONTROL Custom Event] report for Event 1 shows the total number of times the event (or download) occurs. You can have multiple custom event reports. 

## Conversion Reports {#concept_BDD3DD8A46F043BB916C7E346E7C314F}

Shows revenue gained from different aspects of your website. You can see reports that show revenue from ad campaigns, revenue from loyal customers compared to revenue from new customers, a breakdown of revenue by product, and many other revenue reports. Conversion reports can also show other success events such as ad clicks, downloads, or other events.

<!-- 

c_reports_conversion.xml

 -->

Conversion reporting includes real-time statistics on all important customer activity, including:

* Customer purchase patterns 
* Shopping cart metrics, including fallout 
* Customer conversion rates 
* Advertising and channel partner effectiveness 
* Online and offline marketing campaign performance 
* Customer loyalty metrics 
* Insight into sales cycles

## Marketing Channel Reports {#concept_81FFA8C15A9B4914BFED37488ADD17FD}

Marketing Channel reports display the first and last-touch channel allocation, with critical, standard metrics like revenue, orders, and cost, letting you know how much revenue each channel generates. You configure channel definition rules in the [!DNL Admin Console], and APIs specific for the channel reports are available.

<!-- 

c_reports_marketing_channel.xml

 -->

** [!UICONTROL First or Last Touch Channel Report] **: Displays metrics showing data about a specific first-touch or last-touch channel. In these reports, you can break down a channel and show the details of each channel. If you have AdLens enabled, you will see classifications in your marketing reports and analytics channel reports.

** [!UICONTROL First or Last Touch Channel Detail Reports] **: Displays details such as page names and referrers, which is taken from the channel values you set up in the [!UICONTROL Set the channel's value to] option when configuring rules. Channel detail reports let you closely examine the channel detail values from the overview report.

For more in-depth information about configuring the Marketing Channel in marketing reports and analytics, see the [Marketing Channel Help](http://marketing.adobe.com/resources/help/en_US/mchannel/index.html) system. 
