---
description: Combine both timestamped and non-timestamped data into a single report suite.
title: Timestamps optional
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
---
# Timestamps optional

Combine both timestamped and non-timestamped data into a single report suite.

Timestamps Optional lets you:

* Mix timestamped and non-timestamped data in the same global report suite.
* Send timestamped data from a mobile app to a global report suite.
* Upgrade apps to use offline tracking without having to create a new report suite.

>[!WARNING]
>
>If you use Timestamps Optional, do not set [s.visitorID](/help/implement/vars/config-vars/visitorid.md) on data that is already timestamped. This can lead to out-of-order data and negatively impact time calculations (such as time spent values), attribution (eVar persistence), visit number/visit counts, and pathing reports.

>[!NOTE]
>
>Timestamp-enabled session data is kept for up to 92 days. This means that a visit/session will be "held open" for 92 days while any additional hit - that isn't 30 minutes after the previous hit (in hit time) - can still be included in the same visit/session. Any "old" hits that are received out of order will produce "unknown" results, since a number of factors (segmentation, allocation, expiration, etc.) influence whether these hits will be included in reporting or not.

## New Report Suites {#section_095A7CFBD280494593B9BEC1592B73A6}

* If created from a template, a new report suite defaults to Timestamps Optional.

  (You can create a new report suite from a template at **Admin > Report Suites > Create New > Report Suite**.)
* If copied from an existing report suite, then the new report suite inherits the timestamp setting from the original, including:

  * **Timestamps not allowed** (setting s.visitorID supported)
  * **Timestamps required** (setting s.visitorID not supported)
  * **Timestamps optional** (setting s.visitorID supported but not on timestamped hits)

## To change existing report suites to Timestamps Optional {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Go to **Admin > Report Suites > Edit Settings > General > Timestamp Configuration**.
1. Select the **Convert selected report suites to Timestamps Optional** box.

   This will change your report suite to Timestamps Optional.

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.
