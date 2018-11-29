---
description: Success events are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.
keywords: event
seo-description: Success events are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.
seo-title: Success events overview
solution: Analytics
title: Success events overview
topic: Admin tools
uuid: 410eee44-8960-462c-a9c3-07b44d0b1df0
index: y
internal: n
snippet: y
---

# Success events overview

Success events are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.

There are many kinds of success events, depending on your web site type. Several examples include:

* **Retail**: Product view, checkout, purchase 
* **Media**: Subscription, contest sign-up, page view, video view 
* **Finance**: Application submission, login, self-service tools usage 
* **Travel**: Booking (purchase), internal campaign (click-through), search (pricing itinerary) 
* **Telecommunications**: Purchase, leads, self-service tools usage 
* **High Tech**: White-paper download, RFP, form completion, support requests 
* **Automotive**: Lead submission, request a quote, brochure download

The [s.events](https://marketing.adobe.com/resources/help/en_US/sc/implement/events.html) variable defines a success event.

## Success Events Page - Descriptions {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**

The Success Events page lets you configure the Event variables used on your site. You can add up to 1,000 success events. Events 81-1,000 only work if on H22 code or higher. 

<table id="table_526E62D58C3346B28826D4838D4F79E2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> The original name of the event. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Name </td> 
   <td colname="col2"> Give meaningful names to success events used on your site. For example, if event1 is used to track registrations, change the name here so that event1 will be represented as the "Registrations" metric in all Conversion reports. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Type </td> 
   <td colname="col2"> <p>The selected <span class="wintitle"> Type</span> determines whether the event is a counter (standard), numeric, or currency event. Numeric and currency events allow you to increment metrics by more than one. </p> <p>Counter events are used to record an event in time, whereas currency events record a decimal number, like tax or shipping. The value passed into currency events is converted from the page currency to the report suite's base currency upon receipt. For details on using currency events, contact an Adobe representative. </p> <p>Numeric events are used to report on non-currency numbers, such as the number of coupons used in an order. Currency events are used to track tax and shipping charges. Events used in the Standard type of Data Sources must be numeric or currency events. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Polarity </td> 
   <td colname="col2"> <p>Metric polarity allows you to indicate whether Adobe Analytics should consider it good or bad if a given custom event (metric) goes up. It will allow Adobe Analytics to show directional indicators (arrows) for various metrics to add context (for example, week over week comparisons. </p> <p>Examples: if "Bugs Submitted" goes up week over week, should Adobe Analytics consider that good, or bad? An increase in Email Registrations is probably good. But an increase in Form Submission Errors is probably bad. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Description </td> 
   <td colname="col2"> A brief description of the event's purpose and usage. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Unique Event Recording </td> 
   <td colname="col2">See <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/event_serialization_impl.html" format="https" scope="external"> Event Serialization</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Participation </td> 
   <td colname="col2">See [Metrics Participation](/help/components/c-variables/c-metrics/metrics-participation.md) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Warning (currency event) </td> 
   <td colname="col2"> <p>When changing event types to or from a currency event, a message is displayed stating that historical data is not available in reporting. </p> <p>Different event types use separate data tables, and cannot be used simultaneously. Some historical data can be restored if the user reverts the event type. However, any data collected after the initial change is not available. Use caution when changing an event type. </p> </td> 
  </tr> 
 </tbody> 
</table>
