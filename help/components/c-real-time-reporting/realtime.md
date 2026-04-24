---
description: Displays web page traffic and ranks page views in real time. Provides actionable data to base your business decisions on.
title: Real-time reporting overview
topic-fix: Reports
feature: Real-time
exl-id: 056235bc-42ea-4118-aa54-bc7666044fe3
TQID: https://experienceleague.adobe.com/2QizNDKGlAUqX7IbHANm-nGMicLXDfKSnl7nYGkETxQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: c80b99d6-98b9-4aeb-b5c4-933ef2ef705c
    internal-label: Marketing Channels
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
---
# Real-time reporting overview

Real-time reporting displays web page traffic and ranks page views in real time. Provides actionable data to base your business decisions on.

>[!NOTE]
>
>The Real-Time Report requires no additional implementation or tagging. It leverages your existing implementation of Adobe Analytics. To configure real-time reports, see [Real-Time Reports Configuration](/help/admin/tools/manage-rs/edit-settings/realtime/t-realtime-admin.md).

## Access Real-Time reporting

1. In Analysis Workspace, select the [!UICONTROL **Workspace**] tab.

1. On the left side of the page, under **[!UICONTROL Templates]**, select [!UICONTROL **Adobe templates**].

1. Select [!UICONTROL **Engagement**] > **[!UICONTROL Real-Time]**.

## Understand Real-Time reporting

Real-Time answers the following questions: What is trending on my site, and why? It allows you as a marketer to quickly respond to and actively manage the performance of your marketing content and campaigns. The real-time data reported is less than two minutes latent and auto-updates on a minute-by-minute basis.

![](/help/admin/tools/manage-rs/edit-settings/realtime/assets/report-realtime.png)

The dashboard includes Adobe Analytics high-frequency metrics and site analytics to visually report traffic and page view trending of dynamic news and retail web sites. Real-Time understands trends in your data from minute to minute, within seconds of collection. It collects and streams data into an auto-updating UI, using real-time correlation and tracking of content and some conversion.

Two of the most prevalent usage scenarios include publishers who would like to promote/demote stories as user activity changes, and marketers who would like to track the launch of a new product line.

As an Administrator, you can

* Create up to 3 real-time reports per report suite, using existing dimensions or classifications and metrics. Use the secondary dimensions to correlate with (or break down) the primary one.
* Add 3 dimensions (or classifications) per report (one primary and two secondary), in addition to 1 site-wide metric.
* Use any custom event, shopping cart event, or instance.
* View up to 2 hours of historical real-time data and modify this setting:

    * Last 15 minutes: 1-minute granularity 
    * Last 30 minutes: 1-minute granularity 
    * Last 1 hour: 2-minute granularity 
    * Last 2 hours: 4-minute granularity

* Compare, for example, last week's values to last year's values (as well as to the total of today.)

Keep in mind that eVars (conversion metrics) are not supported, since there is no concept of persistence. While you can select conversion metrics, they only work if they are set on the same page as the dimension(s). For more information, see the warning message captured in [Setting up Real-Time Reports](/help/components/c-real-time-reporting/t-realtime-admin.md).

Setting up and viewing Real-Time reports is restricted to Admins or any user in the "All Report Access" and "Advanced Reporting" permission groups . However, Real-Time does respect permissions. If, for example, you do not have rights to see revenue, you won't be able to view a real-time report that includes revenue data.

## Data Latency as a Result of A4T Configuration {#latency-a4t}

After the A4T integration is enabled in Adobe [!DNL Target], you will experience an additional 5-10 minutes of latency in Adobe Analytics. This latency increase allows data from Analytics and [!DNL Target] to be stored on the same hit, allowing you to break down tests by page and site section.

This increase is reflected in all Adobe Analytics services and tools, including the live stream and real-time reporting, and applies in the following scenarios:

* For live stream, real-time reports and API requests, and current data for traffic variables, only hits with a supplemental data ID are delayed.
* For current data on conversion metrics, finalized data, and data feeds, all hits are delayed an additional 5-7 minutes.

Be aware that the latency increase starts after you implement the Identity Service, even if you have not fully implemented this integration.
