---
title: Processing and architecture differences between Analytics platforms
description: Learn how some data is collected and displayed differently between platforms such as Adobe Analytics and Google Analytics.
feature: Third-party Integration
exl-id: 3e457915-3c2d-49f7-9b77-df18c04d49cd
TQID: 'https://experienceleague.adobe.com/pL36oKany2sKuJrEn4-oIja3O91PZ47YQGoNvhdt6y8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
    internal-label: Integrations
subfeature_v2:
  - id: a60fda7a-bb0b-4eb6-b9fe-77558cbee1fa
    internal-label: Third party integrations
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
---
# Processing and architecture differences between Analytics platforms

Although Adobe Analytics and Google Analytics are both Analytics tools, the way data is collected and processed between platforms is very different. Use this page to understand some of the key differences in how certain dimensions and metrics are collected, and why they might display different numbers in similar reports.

## [!UICONTROL Bounce Rate]

[!UICONTROL Bounce Rate] is a common KPI that is used to help measure the effectiveness and the relevance of landing pages in most analytics tools. This is commonly defined as visits that enter the website but do not include a click to another page.

* In Adobe Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Bounces divided by Entries**.
* In Google Analytics, [!UICONTROL Bounce Rate] is calculated using the formula **Single-page sessions divided by Sessions**.

On both platforms, if multiple hits are sent in the same visit or session, it is not considered a bounce. In Adobe Analytics, custom links are available and fairly common which can prevent a visit from counting as a bounce. Google Analytics does not typically send more than one data request on the same page.

To achieve better parity between reporting tools, use the [!UICONTROL Single Page Visits] metric in Adobe Analytics instead of [!UICONTROL Bounces] as part of a calculated metric. The [!UICONTROL Single Page Visits] metric includes the total number of visits that only included one-page view, or visits that enter the website but do not include a click to another page.

See the [Bounce Rate](/help/components/metrics/bounce-rate.md) metric in the Components user guide for more information.

## [!UICONTROL Visits] and Sessions

[!UICONTROL Visits] (known as sessions in Google Analytics) are a group of page views made by the same user in a short amount of time. [!UICONTROL Visits] on both platforms typically expire after 30 minutes of inactivity. Both platforms allow customization on when a [!UICONTROL Visit] expires. There are several scenarios that can cause differences on each platform.

* **End of day:** All sessions in Google Analytics expire after 11:59 PM on a given day. If the user is still active on your site after 12 AM, a new session is created. Adobe Analytics continue visits into the following day as part of the same visit.
* **Different campaigns:** A new session in Google Analytics starts if a user's campaign source changes. If a new [!UICONTROL Tracking Code] value is seen in Adobe Analytics, it is considered part of the same visit.
* **Manual session override:** A new session in Google Analytics starts if you use `sessionControl` to manually start or end a session. [!UICONTROL Visits] cannot be manually ended in Adobe Analytics.
* **Outlier visit detection in Adobe Analytics:** A new [!UICONTROL Visit] in Adobe Analytics automatically starts if a user reaches 12 hours of continuous activity, 2500 hits, or 100 hits within 100 seconds. Each of these detection criteria are typically triggered by bot activity.

See the [Visits](/help/components/metrics/visits.md) metric in the Components user guide for more information.
