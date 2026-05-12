---
title: Exclude data in Adobe Analytics
description: Learn various methods around how to exclude data both before and after data collection.
exl-id: dee5bf3b-8bb3-48eb-908d-b4a981f17bfb
feature: Data Configuration and Collection
role: Admin
TQID: https://experienceleague.adobe.com/EVXvZGgeAPTcUUd035DgBAyU38hKNh8xU7nX3g7aY7o
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
---
# Exclude data in Adobe Analytics

Excluding data is commonly used to prevent your organization's testing efforts from populating production data, or to prevent unwanted data from falsely inflating reports. Use any of the following methods to exclude data from Adobe Analytics depending on your use case.

## Exclude data post-data collection

The following methods are ways to exclude data in Analytics reporting after Adobe data collection servers receive image requests. Data excluded using these methods still count toward billable server calls.

* **Exclude by IP**: Adobe Analytics provides basic functionality to exclude data for IP addresses or ranges in a report suite. See [Exclude by IP](/help/admin/tools/exclude-ip.md) in the Admin user guide.
* **Bot rules**: Bot rules take traffic from known bot user agent strings and exclude them from Analytics reports. Data excluded via bot rules are placed in the Bots report. Custom bot rules can be created to exclude additional data. See [Bot Rules](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md) in the Admin user guide.
* **VISTA rules**: Depending on your organization's needs, hits that match your requirements are sent to another report suite dedicated to receiving excluded data. VISTA rules are commonly used against IP addresses, but are not limited to them. You can use any dimension to include or exclude data in report suites. VISTA rules are subject to additional costs; contact your Adobe Account Team for details.
* **Opt-out cookies**: All visitors to your site can voluntarily opt out of being tracked in Adobe Analytics by visiting a page specific to your tracking server. See [Implement opt-out links](/help/implement/js/opt-out.md) in the Implement user guide.

>[!TIP]
>
>Processing rules cannot exclude data or send data to another report suite. However, certain variables can be conditionally set, and a segment can be used to exclude that data from reporting.

## Exclude data pre-data collection

If you want to prevent certain hits from reaching Analytics data collection servers, use the [`abort`](/help/implement/vars/config-vars/abort.md) variable. This flag prevents the image request from being sent. Billable server calls are not incremented for aborted image requests, since they don't reach Adobe data collection servers.
