---
description: null
seo-description: null
seo-title: Data retention policy
title: Data retention policy
uuid: 9988ef5c-d657-4521-8601-e508756d7d07
index: y
internal: n
snippet: y
---

# Data retention policy

Data collected by Adobe Analytics Data Retention Policy Adobe customers is retained for a specific period of time. This period is referred to as the default data retention period. An option is provided to extend the default data retention period for an additional fee.

This policy applies to data that is available in the Adobe Analytics reporting interfaces, including but not limited to Reports & Analytics, Ad Hoc Analysis, Data Warehouse, Report Builder, and the Web services APIs.

## Data Retention Window {#section_621DBEE806EB4540A50008E6B4B15AF1}

The data retention policy defines a rolling data retention window in which complete data can be viewed and reported. The data retention window is determined as follows:

start date = current date - data retention period

end date = current date

Data is included in the data retention window if the timestamp of the data is between the start date and end date. The timestamp is defined as the date of the transaction represented by the data, which may or may not match the date that the data was received by Adobe.

## Default Data Retention Period {#section_1D2CC01FA88944E3B2501B95538BE7C7}

By default, data is retained for 25 months after the timestamp of the data.

## Reducing or Extending the Default Data Retention Period {#section_8A05F1D859EC4A2EAFFC49AD23EEA94C}

A customer can reduce or extend the default data retention period by contacting his or her account manager. While there is no charge for reducing the default data retention period, extending data retention beyond the default retention period of 25 months requires the purchase of extensions (available as an additional SKU). Extensions are available in increments of 1 (one) additional year, up to a maximum of 8 (eight) years.

Each extension increases the amount of full historical data that is retained by 12 months beyond the default data retention period. A one-year extension provides 37 months of full historical data, an additional one-year extension provides 49 months, and so on, for a maximum total retention period of 10 years 1 month (25 months plus up to 8 years extension).

Extensions need to be purchased only to retain data that is older than the default data retention period. For example, if you are targeting 4 years of data retention, you would purchase a one-year extension 25 months after the oldest data was collected, then an additional one-year extension of 37 months after the oldest data was collected.

## Data Retention Period {#section_E6C9934FBEBD450EAD07535A0C898006}

The data retention period is the default data retention period plus any extensions. For example, if you have purchased a single one-year extension, your data retention period is 37 months (25 months provided by the default data retention period + 12 months extension).

## Data Deletion {#section_C3A942ECF22D4C1281062D92BE48C5EC}

Adobe retains the right to delete data for dates beyond the data retention period as defined in this document with no option for recovery.

## Reporting functionality beyond the data retention period {#section_C2F16CAB28EA444B957125BE2E688988}

No reporting functionality is available beyond the data retention period. You must ensure that all data that you want to retain is part of the default retention period, or is included as a result of an extension. 
