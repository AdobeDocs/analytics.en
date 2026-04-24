---
description: Learn about Report Builder frequently asked questions.
title: Report Builder FAQs
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
TQID: https://experienceleague.adobe.com/vFQWGX3ojl070mQIg7GXhY87kxC-7d0dlYl-0rFU9Uk
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
    internal-label: Dashboards
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
    internal-label: Report Builder
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
---
# Report Builder FAQ

{{legacy-arb}}

Frequently asked questions around Report Builder.

## Can I use the `TODAY()` or `DATERANGE()` function in workbooks? {#today}

The [`TODAY()` function](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) in Excel returns the current day. The [`DATEVALUE()` function](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converts a date string into a serial value. While helpful for many features within Excel, Adobe strongly recommends against using these functions as part of Report Builder scheduled requests. Adobe Customer Care does not support troubleshooting requests using either of these functions.

Scheduled reports are processed on servers that likely do not share time zones as the report suite. The `TODAY()` a user expects and the `TODAY()` the processing server uses can often be different. Also, the date used is based on when processing starts. If many reports are run simultaneously, the date can change between the time it is requested and when it starts processing due to delays. This issue is present if the scheduled time is close to midnight.

Scheduled reports are also processed on servers that likely do not share date syntax. For example, `7/1/YYYY` can refer to July 1 or January 7 depending on your country or region. Using the `DATEVALUE()` function on this date would result in differing serial values depending on the computer that executes it.

As an alternative to using these Excel functions, Adobe highly recommends using date ranges within Report Builder requests. On the first page of the request wizard, select **[!UICONTROL Preset Dates]** in the drop-down, then under Commonly Used Dates, select **[!UICONTROL Today]** or another desired date range. This setting takes the time of the report suite at the time it was run, and not the time of the server processing the request.

## How large and complex can I make my workbooks? {#complexity}

Report Builder supports workbooks up to the following limits:

* **1000 requests**: A single workbook can contain up to 1000 data requests. If you have reports or projects that require more than 1000 requests, Adobe recommends separating them into multiple workbooks.
* **20K requests per hour per company**: Report Builder uses the Analytics reporting API to retrieve data. Each individual request uses an API call whenever it is created or refreshed. If your organization accumulates more that 20,000 API calls in a given hour, you must wait until the next hour to retrieve data again.
* **4-hour processing time**: Scheduled reports time out after processing for more than 4 hours. If your workbook contains many complex requests using large data sets, the scheduled report can fail.

## How do I know whether I have access to Report Builder? {#access}

You need to be granted Report Builder access by your Adobe Analytics Admin. The Admin sets up product profiles in the [Adobe Admin Console](/help/admin/admin-console/home.md). Ask your Admin to grant you access.
