---
description: Lists the standard metrics in Adobe Analytics.
seo-description: Lists the standard metrics in Adobe Analytics.
seo-title: Metrics quick reference
solution: Analytics
title: Metrics quick reference
topic: Metrics
uuid: 34160c96-7cb3-4e2f-9956-9ffa9d9a359e
---

# Metrics quick reference

Lists the standard metrics in Adobe Analytics.

>[!NOTE]
>
>Any metric (event) not listed below is a [custom metric](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) (custom event).

>[!IMPORTANT]
>
>Analysis Workspace no longer distinguished between Traffic and Conversion metrics. Hence, the metric type is only relevant to tools such as Reports & Analytics, Web Services 1.4, and Report Builder.) 

| Metric Name | Description | Type|
|--- |--- |---|
|Average Page Depth|Displays on average how far within a visit each value was fired. This metric is valuable in determining how far within a visit your audience reaches a given page or prop value. Average Page Depth is available on any variable with pathing enabled.|Traffic|
|Average Time Spent on Page|Represents the average time spent on a page within a visit.|Traffic|
|Average Time Spent on Site|Represents the average time spent on a site within a visit.|Traffic|
|Bounce rate|Shows the percentage of visits that contain a single hit. Bounce rate uses the Bounces metric and is calculated as: Bounces divided by Entries.|Conversion|
|Bounces|A visit that consists of a single server call. For example, a single page visit is a bounce if a visitor does not interact with the page in a way that sends data to Adobe, such as clicking a link or a video start. If more than a single hit is received in a visit, a Bounce is not counted.|Conversion|
|Campaign Click-throughs|Click-throughs represent the number of times that a tracking code for a given campaign was passed into reporting. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in s.campaign. That data is sent into reporting and a click-through is recorded.|Conversion|
|Cart Additions|The number of times an item was added to a shopping cart. This value comes from the scAdd event.|Conversion|
|Cart Open|The number of times a customer opened a shopping cart by adding the first item. Occurs the first time an item is added to the shopping cart. This value comes from the scOpen event.|Conversion|
|Cart Removals|The number of times an item was removed from a shopping cart. This value comes from the scRemove event.|Conversion|
|Carts|The number of times a new shopping cart was opened or initialized.|Conversion|
|Cart Views|The number of times the contents of the shopping cart are viewed by the customer.|Conversion|
|Checkouts|An event that occurs when customers arrive at the checkout stage of a purchase. The checkout stage usually occurs just before a purchase is finalized, and usually involves the customer entering personal information (such as their shipping and billing information). You have control over the events on your site that qualify as checkouts. This value comes from the scCheckout event.|Conversion|
|Click-throughs|Click-throughs represent the number of times that a tracking code for a given campaign was passed into reporting. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in  s.campaign. That data is sent into reporting and a click-through is recorded.|Conversion|
|Customer (New, Return, Loyal)|Categories of the Customer Loyalty report: New Customer: Customer with 0 purchases.  Return Customer: Customer with 1 purchase.  Loyal Customer: Customer with more than 1 purchase.|Traffic|
|Daily Return Visits|Displays the number of visitors to your website more than once on a given day. A day is defined as the last 24-hour period.|Traffic|
|Entries|Entries represents the number of times a given value is captured as the first value in a visit. Entries can occur only once per visit. However, it is not necessarily the first hit if the variable is not defined.|Traffic|
|Exits|The number of times a given value is captured as the last value in a visit. Exits can occur only once per visit.|Traffic|
|Instances|The number of times that a value was set for a variable. Instances are counted for all hit types, but are not counted when a value is recorded for a variable on a subsequent hit due to persistence.|Conversion|
|Mobile Views|The number of times a page is viewed or a dimension is set when accessed via a mobile device. Ad hoc analysis only. Instead of using the mobile views metric, we recommend applying the "Visits from Mobile Devices" segment.|Conversion|
|New Engagements|New Engagements is a Marketing Channel reporting metric that counts new visitors that come as a result of a channel. This metric also counts visitors who have not been to your site in the last 30 days. A New Engagement is an eVar set at the beginning of each visit (original allocation). First-touch channels can also be New Engagements, depending on visitor engagement expiration setting.|Conversion|
|Occurrences|The number of times a specific value is captured, plus the number of page views for which the given value persisted. In other words, Occurrences are the sum of page views and page events. Occurrences are available only in ad hoc analysis.|Not available in Reports & Analytics, Web Services 1.4, or Report Builder|
|Orders|The number of orders made on your website during the selected time period. You can break down individual time periods by other metrics to show the items (such as products or campaigns) that contributed to the most orders during that time frame.|Conversion|
|Page Depth|The average number of clicks it takes users to get to a certain page in the website.|Traffic|
|Page Events|Page events consist of image request data from non-standard image requests. Sources of non-standard image requests are download links, exit links, and custom link tracking.|Traffic|
|Page Views|A Page View is counted for each server call that is sent. This metric represents total instances of Page View. TrackLink calls are not counted as page views and do not increment the Page Views metric.|Conversion|
|Path Views|The Path Views metric is based on pathing data, which is tracked for all users who accept persistent cookies.  The term Path View is used to indicate the number of times a page was viewed, given the constraints of the displayed path(s). This metric reports the number of page views for the given page that occurred within the selected path. This metric is available on the Paths report. Path Views shows you how many times a particular sequence of pages were viewed.|Traffic|
|Product Views|Instance of the Product View being set. Occurs when the product detail page is viewed. This value comes from the prodView event.|Conversion|
|Reloads|Counted when the same page name is loaded twice in a row. This typically indicates that the page was refreshed. Note that visiting the same page twice in the same visit does not count as a reload unless both visits occurred in-a-row.|Traffic|
|Return Visits|Shows the number of visits where visit number is greater than 1. Return Visits includes non-cookied visitors.|Conversion|
|Revenue|Revenue is captured on the purchase event, and is defined as the total dollar amount for the sum of the order for each product. This value comes from the purchase event.|Conversion|
|Searches|Searches is not a default metric - it is always a custom metric.  It's the recommended default metric for search engines and keywords. This metric represents instances of a click-through, and shows the page that is associated with a specific engine or keyword. Searches metric data can be reported retroactively to the beginning of the data set.|Conversion|
|Single Access|Single Access is defined by the number of visits to your site that contained a single unique Page Name value. If a user comes to your site and clicks a tracked link, triggers an event (such as a video view), or reloads the page, the visit is still considered a Single Access visit. As long as value for the pageName variable does not change, any number of requests can be sent and the visit is still considered a Single Access.|Traffic|
|Time Spent|Metrics that report on the amount of time visitors spend on a page, site, or per visit.|Traffic|
|Total|Total metrics report the value of all report line items for a reported period. If a filter is currently selected, the total might represent the filtered total instead of the report suite total. If no filter is selected total represents the report suite total.|The Total version of a metric follows the type of the base metric. E.g., `totalpageviews` would be Traffic because `pageviews` is Traffic.|
|Unique Customer|(Hourly, Daily, Weekly, Monthly, Quarterly, Yearly)  A Unique Customer is counted once for that time frame but cannot be counted again, no matter how many times the visitor returns to make a purchase. A Unique Visitor is counted once for the first visit in a specified period and not counted again until the period expires. After the period expires, the Unique Visitor is counted again. Unique Customers are always counted as Unique Visitors because they must visit the site in order to make the purchase.|Conversion|
|Unique Visitors|Shows the total number of unique visitors for the reporting period (can be configured to daily, weekly, monthly, quarterly, yearly).|Conversion|
|Units|The total units that were ordered for the selected time period. Because you have many units purchased per order, Units is a vital metric that reveals general inventory movement.|Conversion|
|Visitors|The number of unique visitors to your site for a selected hour, day, week, month, quarter, or year.|Conversion|
|Visits|A sequence of page views in a sitting. The visits metric is commonly used in reports that display the number of user sessions within the selected time period.  The visit metric is always associated with a time period, so you know whether to count a new visit if the same visitor returns to your site.|Conversion|

