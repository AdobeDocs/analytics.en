---
description: Success events are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.
keywords: event
title: Success events overview
feature: Event
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
---
# Success events overview

Success events (also known as conversion events or custom events) are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.

Here is a video overview:

>[!VIDEO](https://video.tv.adobe.com/v/28764/?quality=12)

Access the Success Events page in report suite settings:

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your AdobeID credentials.
2. Click the 9-grid button at the top, then click [!UICONTROL Analytics].
3. Navigate to [!UICONTROL Admin] > [!UICONTROL Report Suites]
4. Select the desired report suite, then navigate to [!UICONTROL Edit Settings] > [!UICONTROL Conversion] > [!UICONTROL Success Events].
5. Locate the desired event, and modify [!UICONTROL Unique Event Recording] dropdown to [!UICONTROL Record Once Per Visit] or [!UICONTROL Use Event ID].

There are many kinds of success events, depending on your web site type. Several examples include:

* **Retail**: Product view, checkout, purchase 
* **Media**: Subscription, contest sign-up, page view, video view 
* **Finance**: Application submission, login, self-service tools usage 
* **Travel**: Booking (purchase), internal campaign (click-through), search (pricing itinerary) 
* **Telecommunications**: Purchase, leads, self-service tools usage 
* **High Tech**: White-paper download, RFP, form completion, support requests 
* **Automotive**: Lead submission, request a quote, brochure download

The [s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html) variable defines a success event.

## Success Events Page - Descriptions {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**

The Success Events page lets you configure the Event variables used on your site. You can add up to 1,000 success events. Events 81-1,000 only work if on H22 code or higher.

| Element | Description |
|--- |--- |
|Event|The original name of the event.|
|Name|Give meaningful names to success events used on your site. For example, if event1 is used to track registrations, change the name here so that event1 will be represented as the "Registrations" metric in all Conversion reports.|
|Type|The selected  Type determines whether the event is a counter (standard), numeric, or currency event. Numeric and currency events allow you to increment metrics by more than one.  Counter events are used to record an event in time, whereas currency events record a decimal number, like tax or shipping. The value passed into currency events is converted from the page currency to the report suite's base currency upon receipt. For details on using currency events, contact an Adobe representative. Numeric events are used to report on non-currency numbers, such as the number of coupons used in an order. Currency events are used to track tax and shipping charges. Events used in the Standard type of Data Sources must be numeric or currency events.|
|Polarity|Metric polarity allows you to indicate whether Adobe Analytics should consider it good or bad if a given custom event (metric) goes up. It will allow Adobe Analytics to show directional indicators (arrows) for various metrics to add context (for example, week over week comparisons.  Examples: if "Bugs Submitted" goes up week over week, should Adobe Analytics consider that good, or bad? An increase in Email Registrations is probably good. But an increase in Form Submission Errors is probably bad.  In Analysis Workspace, polarity is applied to: Freeform Table conditional formatting, Summary Change visualizations, and the Map visualization's Positive/Negative color scheme.|
|Description|A brief description of the event's purpose and usage.|
|Unique Event Recording|**Record Once Per Visit**: Ties the given event to the visitor's session. Subsequent counts to a given event in the same visit are ignored. This type of event serialization does not require any implementation changes.<br>**Use Event ID**: Ties the given event to a custom ID. Subsequent counts to a given event with the same event ID are ignored. This type of event serialization requires a custom ID in hits to deduplicate values. See [Event ID serialization](../../../implement/vars/page-vars/events/event-serialization.md) in the Implement user guide.|
|Participation|Gives full attribution credit to all dimension items in the visit.|
|Warning (currency event)|When changing event types to or from a currency event, a message is displayed stating that historical data is not available in reporting.  Different event types use separate data tables, and cannot be used simultaneously. Some historical data can be restored if the user reverts the event type. However, any data collected after the initial change is not available. Use caution when changing an event type.|
