---
title: Transaction ID data sources
description: Learn the general workflow of using transaction ID data sources.
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
---
# Transaction ID data sources

Transaction ID data sources are a variation on summary data sources that allow you to tie online and offline data together. It requires the use of the [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable in your Analytics implementation.

* If a row in a data sources file includes a transaction ID that matches a transaction ID already collected by AppMeasurement, the dimensions and metrics are appended to the online hit.
* If a row in a data sources file includes a transaction ID that does not contain a match, the row is treated similarly to summary data sources.

>[!NOTE]
>
>Before using transaction ID data sources, you must first enable it in [General Account Settings](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) for the desired report suite.

When you send an online hit that contains a [`transactionID`](/help/implement/vars/page-vars/transactionid.md) value, Adobe takes a "snapshot" of all variables set or persisted then. If a matching transaction ID uploaded through data sources is found, the offline and online data is tied together.

Transaction ID data sources have the following properties:

* The online data must be collected and processed first. If a transaction ID data source is uploaded before a report suite processes a hit matching that transaction ID, the data is not linked.
* Transaction ID's collected through AppMeasurement expire after approximately 90 days. If your organization requires a longer transaction ID window, contact Adobe Customer Care.
* Data sources uploaded with an expired transaction ID are treated similarly to data uploaded without a transaction ID.
* If the same variable is included in both the online hit and the transaction ID data source, the value from the transaction ID data source is used.
* If a variable is included in an online hit but not in a matching transaction ID data source hit, the online hit variable is preserved.
* If you set the same transaction ID on multiple online hits, only the first occurrence is altered with data from a matching transaction ID data source.
* If you set the same transaction ID on multiple data source rows for the same dimensions, the latest dimension item is used.

For example:

1. You send in a page view from AppMeasurement where:
   * `eVar1` equals `blue`
   * `eVar2` equals `water`
   * `events` equals `event1`
   * `transactionID` equals `1256`
2. After the hit is collected and processed, you upload a transaction ID data source where:
   * `eVar1` equals `yellow`
   * `eVar3` equals `bird`
   * `events` equals `event2`
   * `transactionID` equals `1256`
3. Once the data sources hit is processed, you view a report in workspace. The data would show the following:
   * `eVar1` equals `yellow`
   * `eVar2` equals `water`
   * `eVar3` equals `bird`
   * `events` equals `event2`

The eVar1 value `blue` and the `event1` metric are not present in reporting, since the transaction ID hit overwrote those respective values.
