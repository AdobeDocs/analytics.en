---
title: Real-time reports in Adobe Analytics
description: Learn how to pull real-time reports in Adobe Analytics, geared towards users more familiar with Google Analytics.
feature: Third-party Integration
exl-id: 0ca27992-fff8-4bb4-8582-31fd401b23f6
---
# Real-time reports

Real-time reports show what's happening on your site right now. These types of reports are especially valuable to see immediate results of updates you make to your site. For example, a company running a sale on Black Friday can gauge traffic to specific pages and determine which sales to prioritize based on performance in that moment.

![Real-time report](/help/technotes/ga-to-aa/assets/realtime.png)

Real-time reports are one of the few features that have not yet been introduced to Analysis Workspace. Use Reports & Analytics to obtain this data. They require some simple configuration to begin collecting data.

To reach the real-time report configuration page (Admin permissions required):

1. Click [!UICONTROL Reports] in the Adobe Analytics header navigation.
2. In the left menu, Click *[!UICONTROL Site Metrics]* > *[!UICONTROL Real-Time]*.
3. If the report suite does not yet have real-time enabled, a message is displayed with a link to configure the report suite. If the report suite has real-time enabled, click [!UICONTROL Configure] near the real-time report's title.

Adobe allows up to three real-time reports to collect data simultaneously. Each must be configured before they begin collecting data in real-time.

![Real-time report configuration](/help/technotes/ga-to-aa/assets/realtime_config.png)

## Real-time Locations

Real-time locations tells you where visitors reside while visiting your site at the current moment. To configure one of your three real-time reports to show location data:

1. Click [!UICONTROL Configure] near the real-time report's title.
2. Under one of the real-time report slots:
   * Name your real-time report; for example, "Locations".
   * Instances is typically used as the Metric. Users/Unique Visitors are not available in Real-time reports at this time.
   * For Primary Dimension, GeoSegmentation Country is typically used. GeoSegmentation Region, GeoSegmentation US DMA, and GeoSegmentation City are also available.
   * For the two secondary dimensions, use the preferred additional data that you'd like to see for this traffic. Secondary dimensions do not have to be specific to location.
3. Click [!UICONTROL Save and View Report].

## Real-time Traffic Sources

Real-time traffic sources tells you where visitors came from while visiting your site at the current moment. To configure one of your three real-time reports to show traffic sources data:

1. Click 'Configure' near the real-time report's title.
2. Under one of the real-time report slots:
   * Name your real-time report; for example, "Traffic Sources".
   * Instances is typically used as the Metric. Users/Unique Visitors are not available in Real-time reports at this time.
   * For Primary Dimension, Referring Domain is typically used. Search Engine and Search Keyword are also available.
   * For the two secondary dimensions, use the preferred additional data that you'd like to see for this traffic. Secondary dimensions do not have to be specific to traffic sources.
3. Click [!UICONTROL Save and View Report].

## Real-time Content

Real-time content tells you what pages your visitors are currently viewing. To configure one of your three real-time reports to show content data:

1. Click [!UICONTROL Configure] near the real-time report's title.
2. Under one of the real-time report slots:
   * Name your real-time report; for example, "Content".
   * Instances is typically used as the Metric. Users/Unique Visitors are not available in Real-time reports at this time.
   * For Primary Dimension, Page is typically used. Site Section and Server are also available if your implementation defines these variables.
   * For the two secondary dimensions, use the preferred additional data that you'd like to see for this traffic. Secondary dimensions do not have to be specific to content.
3. Click [!UICONTROL Save and View Report].

## Real-time Events

Real-time events tells you which events are happening the most on your site. In Google Analytics, an event captures the number of times a specific action (generally an action that is unrelated to a page view) has occurred. GA events are sent with a Category, Label, and Action. In Adobe Analytics, custom events are metrics that are given friendly names in the admin console and can be analyzed alongside any dimension. If you are looking for a dimension in Adobe Analytics that is similar to Google Analytics events, consider applying the Custom Link dimension, which is often used as a catch-all for collecting data that is unrelated to page views (in addition to Exit Links - for Exits - and Download Links - for Downloads).

>[!NOTE]
>
>When using custom events in real-time reports, the dimension item must be defined in the same hit as the custom event. For example, if viewing a 'Registrations' custom event for the 'Referring Domain' dimension, no data would be returned without additional implementation. Since referring domain only appears on the first hit, and a custom event would typically appear later in the visit, the data cannot be associated in real-time reports. This data is available using Analysis Workspace using standard processing latency, which is typically 30-90 minutes.

## Real-time Conversions

Real-time conversions present data differently between platforms. Goals in Google Analytics are akin to metrics and success events in Adobe Analytics. You can use most metrics in Adobe Analytics (both custom metrics like success events and standard metrics like revenue) in Real Time Reports. Similar to Google Analytics, you can also apply dimensions like product name, tracking code, and campaign performance in real-time reports.

1. Click [!UICONTROL Configure] near the real-time report's title.
2. Under one of the real-time report slots:
   * Name your real-time report; for example, "Conversions".
   * Instances is typically used as the Metric. Users/Unique Visitors are not available in Real-time reports at this time.
   * For Primary Dimension, Tracking Code is typically used. The Products dimension is also available if your implementation uses it.
   * For the two secondary dimensions, use the preferred additional data that you'd like to see for this traffic. Secondary dimensions do not have to be specific to conversions.
3. Click [!UICONTROL Save and View Report].

>[!NOTE]
>
>If using events outside of Instances, such as Orders, ensure that your implementation defines the dimension and event on the same hit. If dimensions and events don't fire on the same hit, that data is available in Analysis Workspace using standard processing latency, which is typically 30-90 minutes.
