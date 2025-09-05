---
description: Success events are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.
keywords: event
title: Success events overview
feature: Metrics
role: Admin
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
---
# Success events

Success events (also known as conversion events or custom events) are actions that can be tracked. You determine what a success event is. For example, if a visitor purchases an item, the purchase event could be considered the success event.

For a video overview of success events, see [Introduction to conversion events](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/analysis-workspace/metrics/introduction-to-conversion-events) in the Analytics tutorials guide. 

## Success event examples

There are many kinds of success events, depending on your web site type. Several examples include:

* **Retail**: Product view, checkout, purchase
* **Media**: Subscription, contest sign-up, page view, video view
* **Finance**: Application submission, login, self-service tools usage
* **Travel**: Booking (purchase), internal campaign (click-through), search (pricing itinerary)
* **Telecommunications**: Purchase, leads, self-service tools usage
* **High Tech**: White-paper download, RFP, form completion, support requests
* **Automotive**: Lead submission, request a quote, brochure download

The [s.events](/help/implement/vars/page-vars/events/event-serialization.md) variable defines a success event.

## Configure success events

You can configure the Event variables used on your site. You can add up to 1,000 success events. Events 81-1,000 work only if you are on H22 code or higher.

To configure success events:

1. In Adobe Analytics, select **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]**.
1. Select the report suite where you want to configure success events.
1. Select **[!UICONTROL Edit Settings]** > **[!UICONTROL Conversion]** > **[!UICONTROL Success Events]**.

   ![Step Result](/help/admin/tools/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/assets/success_event_page.png)

1. In the [!UICONTROL **Event**] column, identify the name of the event that you want to use as a success event.

1. In the **[!UICONTROL Name]** column, select the checkbox next to the item to enable editing, then specify the desired name.

   Give meaningful names to success events used on your site. For example, if event1 is used to track registrations, change the name here so that event1 will be represented as the "Registrations" metric in all Conversion reports.

1. In the **[!UICONTROL Type]** column, select the checkbox next to the item to enable the drop-down list, then select the desired type.

   >[!IMPORTANT]
   >
   >Consider the following when changing the event type:<ul><li>You can change the event type between counter and numeric without losing access to previously captured data.</li><li>When changing event types to or from a currency event, a message is displayed stating that historical data is not available in reporting. Different event types use separate data tables, and cannot be used simultaneously. Some historical data can be restored if the user reverts the event type. However, any data collected after the initial change is not available.</li></ul>

   The type that you select determines whether the event is a counter (standard), numeric, or currency event. <p>Counter events are used to record an event in time.</p><p>Numeric events are used to report on non-currency numbers, such as the number of coupons used in an order.</p> <p>Currency events record a decimal number, like tax or shipping. The value passed into currency events is converted from the page currency to the report suite's base currency upon receipt. Currency events are used to track tax and shipping charges. For details on using currency events, contact an Adobe representative.<p>Numeric and currency events allow you to increment metrics by more than one.</p><p>Events used in the Standard type of Data Sources must be numeric or currency events.</p>

1. In the **[!UICONTROL Polarity]** column, select the checkbox, then choose from the drop-down menu whether an upward trend for this metric is good or bad.

   this allows you to indicate whether Adobe Analytics should consider it good or bad if a given custom event (metric) goes up. It activates directional indicators (arrows) for various metrics to add context (for example, week over week comparisons).  Examples: if "Bugs Submitted" goes up week over week, should Adobe Analytics consider that good, or bad? An increase in Email Registrations is probably good. But an increase in Form Submission Errors is probably bad.  In Analysis Workspace, polarity is applied to: Freeform Table conditional formatting, Summary Change visualizations, and the Map visualization's Positive/Negative color scheme.

1. In the **[!UICONTROL Visibility]** column, select the checkbox, then choose from the drop-down menu whether to hide standard (built-in) metrics, custom events, and built-in events in the Menu, Metric Selectors, Calculated Metrics Builder, and the Segment Builder.

   This setting does not impact the data collection for that metric or event; it affects only its visibility in the user interface, as follows:

   The following settings are available:

   |Setting | Visible in | Not visible in |
   |---------|----------|---------|
   | [!UICONTROL **Visible everywhere**] | <ul><li>Analysis Workspace</li><li>Segment Builder</li><li>Calculated Metric Builder</li></ul> | N/A |
   | [!UICONTROL **Builders**] | <ul><li>Segment Builder</li><li>Calculated Metric Builder</li><li>Analysis Workspace</li></ul> |
   | [!UICONTROL **Hidden everywhere**] | N/A | <ul><li>Analysis Workspace</li><li>Segment Builder</li><li>Calculated Metric Builder</li></ul> | 

1. In the [!UICONTROL **Description**] column, select the checkbox, then provide a description.
1. In the [!UICONTROL **Unique Event Recording**] column, select the checkbox, then choose from the drop-down menu whether to always record the event.

   The following options are available:
  
   | Option | Function | 
   |---------|----------|
   | [!UICONTROL **Record Once Per Visit**] | Ties the given event to the visitor's session. Subsequent counts to a given event in the same visit are ignored. This type of event serialization does not require any implementation changes. |
   | [!UICONTROL **Use Event ID**] | Ties the given event to a custom ID. Subsequent counts to a given event with the same event ID are ignored. This type of event serialization requires a custom ID in hits to deduplicate values. See [Event ID serialization](/help/implement/vars/page-vars/events/event-serialization.md) in the Implement user guide. |

1. In the [!UICONTROL **Participation**] column, select the checkbox, then choose whether to enable or disable participation. When enabled, it gives full attribution credit to all dimension items in the visit.

   >[!NOTE]
   >
   >You can enable participation for up to 100 custom events. Beyond that, you can create participation metrics in the [Calculated Metrics](/help/components/c-calcmetrics/c-workflow/cm-workflow/c-build-metrics/participation-metric.md) builder.

1. Select **[!UICONTROL Save]**.
