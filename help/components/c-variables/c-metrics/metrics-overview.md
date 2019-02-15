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
>Any metric (event) not listed below is a [custom metric](../../../components/c-variables/c-metrics/metrics-custom.md#concept_F44638FC95A44B06AEBA3A6F9D008D27) (event).

<table id="table_CF4480B640BD4C81B4B32121FED5C96A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Metric Name </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Average Page Depth </td> 
   <td colname="col2"> Displays on average how far within a visit each value was fired. This metric is valuable in determining how far within a visit your audience reaches a given page or prop value. Average Page Depth is available on any variable with pathing enabled. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Average Time Spent on Page </td> 
   <td colname="col2"> Represents the average time spent on a page within a visit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Average Time Spent on Site </td> 
   <td colname="col2"> Represents the average time spent on a site within a visit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bounce rate </td> 
   <td colname="col2"> Shows the percentage of visits that contain a single hit. Bounce rate uses the Bounces metric and is calculated as: Bounces divided by Entries. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Bounces </td> 
   <td colname="col2"> A visit that consists of a single server call. For example, a single page visit is a bounce if a visitor does not interact with the page in a way that sends data to Adobe, such as clicking a link or a video start. If more than a single hit is received in a visit, a Bounce is not counted. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Campaign Click-throughs </td> 
   <td colname="col2"> Click-throughs represent the number of times that a tracking code for a given campaign was passed into reporting. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in s.campaign. That data is sent into reporting and a click-through is recorded. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cart Additions </td> 
   <td colname="col2"> The number of times an item was added to a shopping cart. This value comes from the scAdd event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cart Open </td> 
   <td colname="col2"> The number of times a customer opened a shopping cart by adding the first item. Occurs the first time an item is added to the shopping cart. This value comes from the scOpen event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cart Removals </td> 
   <td colname="col2"> The number of times an item was removed from a shopping cart. This value comes from the scRemove event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Carts </td> 
   <td colname="col2"> The number of times a new shopping cart was opened or initialized. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Cart Views </td> 
   <td colname="col2"> The number of times the contents of the shopping cart are viewed by the customer. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Checkouts </td> 
   <td colname="col2"> An event that occurs when customers arrive at the checkout stage of a purchase. The checkout stage usually occurs just before a purchase is finalized, and usually involves the customer entering personal information (such as their shipping and billing information). You have control over the events on your site that qualify as checkouts. This value comes from the scCheckout event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Click-throughs </td> 
   <td colname="col2">Click-throughs represent the number of times that a tracking code for a given campaign was passed into reporting. When a visitor clicks on an affiliate link that has been tagged with one of these tracking codes, the visitor is taken to your landing page and the tracking code is captured in <span class="varname"> s.campaign</span>. That data is sent into reporting and a click-through is recorded. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Customer (New, Return, Loyal) </td> 
   <td colname="col2">Categories of the Customer Loyalty report: <p>New Customer: Customer with 0 purchases. </p> <p>Return Customer: Customer with 1 purchase. </p> <p>Loyal Customer: Customer with more than 1 purchase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Daily Return Visits </td> 
   <td colname="col2"> Displays the number of visitors to your website more than once on a given day. A day is defined as the last 24-hour period. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Entries </td> 
   <td colname="col2"> Entries represents the number of times a given value is captured as the first value in a visit. Entries can occur only once per visit. However, it is not necessarily the first hit if the variable is not defined. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Exits </td> 
   <td colname="col2"> The number of times a given value is captured as the last value in a visit. Exits can occur only once per visit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Instances </td> 
   <td colname="col2"> The number of times that a value was set for a variable. Instances are counted for all hit types, but are not counted when a value is recorded for a variable on a subsequent hit due to persistence. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Lifetime </td> 
   <td colname="col2"> The total amount of a given success metric for a single user. For example, the total number of lifetime visits for a user. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Mobile Views </td> 
   <td colname="col2"> The number of times a page is viewed or a dimension is set when accessed via a mobile device. Ad hoc analysis only. Instead of using the mobile views metric, we recommend applying the "Visits from Mobile Devices" segment. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> New Engagements </td> 
   <td colname="col2"> New Engagements is a Marketing Channel reporting metric that counts new visitors that come as a result of a channel. This metric also counts visitors who have not been to your site in the last 30 days. A New Engagement is an eVar set at the beginning of each visit (original allocation). First-touch channels can also be New Engagements, depending on visitor engagement expiration setting. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Occurrences </td> 
   <td colname="col2"> The number of times a specific value is captured, plus the number of page views for which the given value persisted. In other words, Occurrences are the sum of page views and page events. Occurrences are available only in ad hoc analysis. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Orders </td> 
   <td colname="col2"> The number of orders made on your website during the selected time period. You can break down individual time periods by other metrics to show the items (such as products or campaigns) that contributed to the most orders during that time frame. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Depth </td> 
   <td colname="col2"> The average number of clicks it takes users to get to a certain page in the website. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Events </td> 
   <td colname="col2"> Page events consist of image request data from non-standard image requests. Sources of non-standard image requests are download links, exit links, and custom link tracking. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Page Views </td> 
   <td colname="col2"> A Page View is counted for each server call that is sent. This metric represents total instances of Page View. TrackLink calls are not counted as page views and do not increment the Page Views metric. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Path Views </td> 
   <td colname="col2"> <p>The Path Views metric is based on pathing data, which is tracked for all users who accept persistent cookies. </p> <p>The term Path View is used to indicate the number of times a page was viewed, given the constraints of the displayed path(s). This metric reports the number of page views for the given page that occurred within the selected path. This metric is available on the Paths report. Path Views shows you how many times a particular sequence of pages were viewed. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Product Views </td> 
   <td colname="col2"> Instance of the Product View being set. Occurs when the product detail page is viewed. This value comes from the prodView event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Reloads </td> 
   <td colname="col2"> Counted when the same page name is loaded twice in a row. This typically indicates that the page was refreshed. Note that visiting the same page twice in the same visit does not count as a reload unless both visits occurred in-a-row. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Return Visits </td> 
   <td colname="col2"> Shows the number of visits where visit number is greater than 1. Return Visits includes non-cookied visitors. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Revenue </td> 
   <td colname="col2"> Revenue is captured on the purchase event, and is defined as the total dollar amount for the sum of the order for each product. This value comes from the purchase event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Searches </td> 
   <td colname="col2"> <p>Searches is not a default metric - it is always a custom metric. </p> <p>It's the recommended default metric for search engines and keywords. This metric represents instances of a click-through, and shows the page that is associated with a specific engine or keyword. Searches metric data can be reported retroactively to the beginning of the data set. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Single Access </td> 
   <td colname="col2"> Single Access is defined by the number of visits to your site that contained a single unique Page Name value. If a user comes to your site and clicks a tracked link, triggers an event (such as a video view), or reloads the page, the visit is still considered a Single Access visit. As long as value for the pageName variable does not change, any number of requests can be sent and the visit is still considered a Single Access. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Time Spent </td> 
   <td colname="col2"> Metrics that report on the amount of time visitors spend on a page, site, or per visit. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Total </td> 
   <td colname="col2"> Total metrics report the value of all report line items for a reported period. If a filter is currently selected, the total might represent the filtered total instead of the report suite total. If no filter is selected total represents the report suite total. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unique Customer </td> 
   <td colname="col2"> <p>(Hourly, Daily, Weekly, Monthly, Quarterly, Yearly) </p> <p>A Unique Customer is counted once for that time frame but cannot be counted again, no matter how many times the visitor returns to make a purchase. A Unique Visitor is counted once for the first visit in a specified period and not counted again until the period expires. After the period expires, the Unique Visitor is counted again. Unique Customers are always counted as Unique Visitors because they must visit the site in order to make the purchase. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unique Visitors </td> 
   <td colname="col2"> Shows the total number of unique visitors for the reporting period (can be configured to daily, weekly, monthly, quarterly, yearly). </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Units </td> 
   <td colname="col2"> The total units that were ordered for the selected time period. Because you have many units purchased per order, Units is a vital metric that reveals general inventory movement. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visitors </td> 
   <td colname="col2"> The number of unique visitors to your site for a selected hour, day, week, month, quarter, or year. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Visits </td> 
   <td colname="col2"> <p>A sequence of page views in a sitting. The visits metric is commonly used in reports that display the number of user sessions within the selected time period. </p> <p>The visit metric is always associated with a time period, so you know whether to count a new visit if the same visitor returns to your site. </p> </td> 
  </tr> 
 </tbody> 
</table>

