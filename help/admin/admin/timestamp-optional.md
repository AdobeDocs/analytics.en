---
description: Combine both timestamped and non-timestamped data into a single report suite.
seo-description: Combine both timestamped and non-timestamped data into a single report suite.
seo-title: Timestamps optional
solution: Analytics
title: Timestamps optional
topic: Admin tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
index: y
internal: n
snippet: y
---

# Timestamps optional

Combine both timestamped and non-timestamped data into a single report suite.

Timestamps Optional lets you:

* Mix timestamped and non-timestamped data in the same global report suite. 
* Send timestamped data from a mobile app to a global report suite. 
* Upgrade apps to use offline tracking without having to create a new report suite.

See [Using Timestamps Optional](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=timestamps-overview) for best practices when using timestamps in your report suite.

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) on data that is already timestamped. This can lead to out-of-order data and negatively impact time calculations (such as time spent values), attribution (eVar persistence), visit number/visit counts, and pathing reports.

>[!NOTE]
>
>Timestamp-enabled session data is kept for up to 92 days.

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

