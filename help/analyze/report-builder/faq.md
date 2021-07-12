---
title: Report Builder FAQ
description: Frequently asked questions for Report Builder.
feature: Report Builder
role: User, Admin
exl-id: 86604d39-2965-45a5-98ab-3ee4adcb7f97
---
# Report Builder FAQ

Frequently asked questions around Report Builder.

## Can I use the `TODAY()` or `DATERANGE()` function in workbooks?

The [`TODAY()` function](https://support.microsoft.com/en-us/office/today-function-5eb3078d-a82c-4736-8930-2f51a028fdd9) in Excel returns the current day. The [`DATEVALUE()` function](https://support.microsoft.com/en-us/office/datevalue-function-df8b07d4-7761-4a93-bc33-b7471bbff252) converts a date string into a serial value. While helpful for many features within Excel, Adobe strongly recommends against using these functions as part of Report Builder scheduled requests. Adobe Customer Care does not support troubleshooting requests using either of these functions.

Scheduled reports are processed on servers that likely do not share time zones as the report suite. The `TODAY()` a user expects and the `TODAY()` the processing server uses can often be different. Also, the date used is based on when processing starts. If many reports are run simultaneously, the date can change between the time it is requested and when it starts processing due to delays. This issue is present if the scheduled time is close to midnight.

Scheduled reports are also processed on servers that likely do not share date syntax. For example, `7/1/YYYY` can refer to July 1 or January 7 depending on your country or region. Using the `DATEVALUE()` function on this date would result in differing serial values depending on the computer that executes it.

As an alternative to using these Excel functions, Adobe highly recommends using date ranges within Report Builder requests. On the first page of the request wizard, select **[!UICONTROL Preset Dates]** in the dropdown, then under Commonly Used Dates, select **[!UICONTROL Today]** or another desired date range. This setting takes the time of the report suite at the time it was run, and not the time of the server processing the request.

## How large and complex can I make my workbooks?

Report Builder supports workbooks up to the following limits:

* **1000 requests**: A workbook can contain up to 1000 data requests in a single workbook. If you have reports or projects that require more than 1000 requests, Adobe recommends separating them into multiple workbooks.
* **20K requests per hour per company**: Report Builder uses the Analytics reporting API to retrieve data. Each individual request uses an API call whenever it is created or refreshed. If your organization accumulates more that 20,000 API calls in a given hour, you must wait until the next hour to retrieve data again.
* **4-hour processing time**: Scheduled reports time out after processing past 4 hours. If your workbook contains many complex requests using large data sets, the scheduled report can fail.
